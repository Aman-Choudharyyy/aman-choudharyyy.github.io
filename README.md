# Point-0 — Cybersecurity Blog by Aman

A minimal, dark cybersecurity blog built with Jekyll and hosted on GitHub Pages.

---

## 🚀 Setup in 5 Minutes

### 1. Install Ruby & Jekyll
```bash
# macOS
brew install ruby
gem install jekyll bundler

# Ubuntu/Debian
sudo apt install ruby-full build-essential
gem install jekyll bundler
```

### 2. Install dependencies
```bash
cd point0
bundle install
```

### 3. Run locally
```bash
bundle exec jekyll serve
# Visit http://localhost:4000
```

---

## 📝 Writing a New Post

Create a file in `_posts/` with this naming format:
```
_posts/YYYY-MM-DD-your-post-title.md
```

Start every post with this front matter:
```yaml
---
layout: post
title: "Your Post Title"
date: 2024-01-15
tags: [Malware, Analysis]   # Choose from: Malware, Zero-Day, APT, Forensics, Ransomware, Intel, Critical
excerpt: "A short summary shown on the homepage."
---

Your content here in Markdown...
```

That's it. Save the file, Jekyll rebuilds automatically.

---

## 🌐 Deploy to GitHub Pages (Free)

### First time setup:
1. Create a GitHub repo named `yourusername.github.io`
2. Push this folder to that repo:
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```
3. Go to repo Settings → Pages → Source: `main` branch
4. Your site is live at `https://yourusername.github.io` in ~2 minutes!

### Publishing a new post:
```bash
git add .
git commit -m "New post: your post title"
git push
```
GitHub Pages rebuilds automatically. Live in ~30 seconds.

---

## 📬 Enable Contact Form (Free)

1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form and copy your form ID
3. In `contact.md`, replace `YOUR_FORM_ID` in the form action URL

---

## 🗂️ File Structure

```
point0/
├── _config.yml          # Site settings
├── _layouts/
│   ├── default.html     # Main layout (header + footer)
│   └── post.html        # Blog post layout
├── _posts/              # Your blog posts go here
│   └── YYYY-MM-DD-title.md
├── assets/
│   └── css/main.css     # All styles
├── index.html           # Homepage
├── about.md             # About page
├── newsletter.md        # Newsletter page
└── contact.md           # Contact page
```

---

## ✏️ Customization

Edit `_config.yml` to change your name, tagline, and description.
Edit `assets/css/main.css` to tweak colors, fonts, or layout.

---

Built with ❤️ for Point-0 by Aman.
