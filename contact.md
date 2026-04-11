---
layout: default
title: Contact
---

<div class="contact-page">
  <h1>Contact.</h1>
  <p class="contact-desc">Have a tip, a lead, a CVE you want analyzed, or want to collaborate? Drop a message.</p>

  <form action="https://formspree.io/f/mjgpnydo" method="POST">
    <div class="form-group">
      <label class="form-label">Name</label>
      <input type="text" name="name" class="form-control" placeholder="Your name or handle" required />
    </div>
    <div class="form-group">
      <label class="form-label">Email</label>
      <input type="email" name="email" class="form-control" placeholder="your@email.com" required />
    </div>
    <div class="form-group">
      <label class="form-label">Subject</label>
      <input type="text" name="subject" class="form-control" placeholder="e.g. Tip, CVE Report, Collaboration" />
    </div>
    <div class="form-group">
      <label class="form-label">Message</label>
      <textarea name="message" class="form-control" rows="6" placeholder="Your message..." required></textarea>
    </div>
    <button type="submit" class="btn-primary">Send Message →</button>
  </form>
</div>
