# CLAUDE.md

Project context for Claude Code working in this repository.

## What this is
Personal profile website for **Jaspal Singh** — a clean, modern static site
(technology leadership / portfolio & delivery). Plain HTML + CSS + vanilla JS,
no build step. Articles are flat HTML files (no CMS); new ones are made by
copying `articles/_template.html`.

## Important facts to remember
- **Contact email `email@jaspalsingh.consulting` is Jaspal's REAL address — not a
  placeholder.** Do not flag it as a placeholder or change it.
- **LinkedIn:** https://www.linkedin.com/in/jaspalsinghau
- **Custom domain:** `jaspalsingh.consulting` (apex), set via the `CNAME` file and
  hosted at Namecheap. Leave `CNAME` in place on every deploy.
- The GitHub repository is named `profile` (it was renamed from `personal_site`).

## Deployment
- Single pipeline: `.github/workflows/deploy.yml` deploys to GitHub Pages on every
  push to `main` (and via manual `workflow_dispatch`). It auto-enables Pages
  (`enablement: true`) and publishes the repo root.
- Do not add a second Pages workflow — duplicates race and fail.

## Theme
Black / white / grey with an amber-gold accent (`--accent: #f5a623`). Restrained,
accessible animation that honours `prefers-reduced-motion`. Keep the "built
entirely with Claude Code" messaging prominent.

## Local preview
`python3 -m http.server 8000` then open http://localhost:8000
