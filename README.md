# Jaspal Singh — Personal Profile Site

A clean, modern personal profile site for **Jaspal Singh** — technology leadership,
portfolio & delivery. Black / white / grey theme with an amber-gold accent.

🔗 **Live:** https://jaspalsingh.consulting

> **Built entirely with [Claude Code](https://claude.com/claude-code)** by Jaspal Singh —
> backed by this GitHub repository, an automated GitHub Actions pipeline, and GitHub Pages.

## Stack

Plain, dependency-free **static HTML + CSS + vanilla JavaScript** — no framework, no build
step. That keeps it fast, easy to host on GitHub Pages, and simple to extend (articles are
just flat HTML files — no CMS needed).

## Structure

```
.
├── index.html                 # Single-page profile (skills, values, behaviours)
├── articles.html              # Article index / listing
├── contact.html               # How to get in touch (email + LinkedIn)
├── 404.html                   # Branded not-found page
├── articles/
│   ├── _template.html         # Copy this to create a new article
│   └── scaling-a-fintech-team.html
├── assets/
│   ├── css/styles.css         # Design system + all styles
│   ├── js/main.js             # Scroll reveal, stat counters, mobile nav
│   └── favicon.svg
├── CNAME                      # Custom domain (jaspalsingh.consulting)
├── .nojekyll                  # Serve files as-is (no Jekyll processing)
└── .github/workflows/deploy.yml   # CI/CD: deploy to GitHub Pages
```

## Local preview

No build step — just serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Adding a new article

1. Copy the template:
   ```bash
   cp articles/_template.html articles/my-new-article.html
   ```
2. Edit the `<title>`, meta description, header (category, title, date) and body
   (use `<h2>`, `<h3>`, `<p>`, `<ul>`, `<blockquote>`, `<a>`).
3. Add a card linking to it near the top of the list in **`articles.html`**
   (newest first) — copy an existing `<article class="article-card">` block.
4. Commit and push to `main` — the pipeline deploys automatically.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which publishes the static
files to GitHub Pages.

### One-time setup

1. **Repo → Settings → Pages → Build and deployment → Source: GitHub Actions.**
2. **Custom domain DNS** for `jaspalsingh.consulting` (apex) — add A records pointing to
   GitHub Pages:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
   (Optionally add the AAAA records for IPv6.) Then enable **Enforce HTTPS** in
   Settings → Pages once the certificate is issued.

The `CNAME` file in this repo keeps the custom domain configured across deployments.
