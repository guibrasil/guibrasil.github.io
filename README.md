# Personal website (Home, About, Blog)

Jekyll site for GitHub Pages. Three sections: **Home**, **About**, **Blog**.

## Run locally

1. Install Ruby if needed (macOS often has it: `ruby -v`).
2. Install dependencies and run the site:

   ```bash
   cd personal-website
   bundle install
   bundle exec jekyll serve
   ```

3. Open **http://localhost:4000** in your browser.

## Add a blog post

Create a new file in `_posts/` with the name format:

**`YYYY-MM-DD-your-title.md`**

Example: `_posts/2025-03-01-swiftui-tips.md`

Start the file with front matter, then write in Markdown:

```yaml
---
layout: post
title: "Your post title"
date: 2025-03-01 12:00:00 +0000
---

Your content here...
```

## Deploy to GitHub Pages

### Option 1: Site at `username.github.io`

1. Create a **new repository** on GitHub named exactly: **`yourusername.github.io`** (replace with your GitHub username).
2. In this folder, init git and push:

   ```bash
   cd personal-website
   git init
   git add .
   git commit -m "Initial Jekyll site"
   git branch -M main
   git remote add origin https://github.com/yourusername/yourusername.github.io.git
   git push -u origin main
   ```

3. GitHub will build and publish the site. In a few minutes it will be at **https://yourusername.github.io**.

### Option 2: Custom domain (e.g. Hostinger)

1. Deploy as above so the site works at `username.github.io`.
2. In the repo: **Settings → Pages → Custom domain** → enter your domain (e.g. `yourdomain.com`) → Save.
3. In Hostinger (or wherever your domain DNS is): add a **CNAME** record:
   - **Name:** `www` (or `@` if you want the root domain)
   - **Target:** `yourusername.github.io`
4. Wait for DNS to update (up to 48 hours, often minutes). GitHub will show a green “DNS check successful” when it’s ready.

## Customize

- **Site title, email, description:** edit `_config.yml`.
- **Home page:** edit `index.md`.
- **About page:** edit `about.md`.
- **Navigation:** links are in the header via `header_pages` in `_config.yml`.
