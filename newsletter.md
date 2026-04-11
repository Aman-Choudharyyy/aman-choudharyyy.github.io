---
layout: default
title: Newsletter
---

<div class="newsletter-hero">
  <div class="nl-label">Newsletter</div>
  <h1>Threat Intel &amp; Deep Dives</h1>
  <p>Subscribe to get weekly zero-day breakdowns, malware analysis, breach post-mortems, and the latest in cyber threat intelligence — straight to your inbox.</p>
  <form class="nl-form" action="#" method="post">
    <input type="email" name="email" placeholder="Enter your email" required />
    <button type="submit">Subscribe</button>
  </form>
  <p class="nl-privacy">No spam. Unsubscribe anytime. We care about your data.</p>
</div>

<div class="container" style="padding-top:0;">
  <hr class="divider" />
  <p class="section-label">All blog posts</p>
  <div class="posts-grid">
    {% for p in site.posts %}
    <div class="post-card">
      <div class="post-thumb">
        <div style="width:100%;height:160px;background:var(--surface);display:flex;align-items:center;justify-content:center;color:var(--accent);font-size:1.8rem;">
          {% assign icons = "⚠,🔍,🛡,💀,🔐,🧬" | split: "," %}
          {% assign idx = forloop.index0 | modulo: 6 %}
          {{ icons[idx] }}
        </div>
      </div>
      <div>
        <div class="post-date">{{ p.date | date: "%A, %d %b %Y" }}</div>
        <div class="post-title">
          <a href="{{ p.url | relative_url }}">{{ p.title }}</a>
          <span class="arrow-icon">↗</span>
        </div>
        <p class="post-excerpt">{{ p.excerpt | strip_html | truncatewords: 18 }}</p>
        <div class="post-tags">
          {% for tag in p.tags limit:3 %}
            <span class="post-tag tag-{{ tag | downcase | replace: ' ','-' }}">{{ tag }}</span>
          {% endfor %}
        </div>
      </div>
    </div>
    {% endfor %}
  </div>
</div>
