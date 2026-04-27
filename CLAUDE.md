# Uni — Claude Instructions

## What This Is

Uni is a design studio. The site will eventually cover portfolio, e-commerce, and video. Right now we are building the holding page; the full site comes after.

## Design Direction

Apple-level simplicity and sophistication. Clean, friendly animations — nothing flashy or excessive. Intuitive layouts, subtle details, no flair. When in doubt, do less.

## Current State

Holding page is live at uni.nyc. It currently just says "Test" — the real holding page design is next.

## What's Next (in order)

1. **Design and build the holding page** — still vanilla HTML/CSS, no framework needed yet
2. **Set up a dev workflow** — a way to work on the full site and see it online before flipping the switch (likely a `dev` branch or subdomain like dev.uni.nyc, TBD)
3. **Build the full site** — portfolio, e-commerce, video; stack TBD when scope is clearer

## Stack

Currently: vanilla HTML/CSS, no build step.

When moving to the full site: scaffold React + Vite, update `deploy.yml` to add `npm ci` + `npm run build`, point rsync source to `dist/`. See `~/.claude/CLAUDE.md` for the deploy template.

## Deployment

Push to `main` → GitHub Actions → rsync to server → Cloudflare cache purge.

**Deploy target**: `/home/uni.nyc/public_html/`

Secrets live in the GitHub repo (SSH_PRIVATE_KEY, SERVER_IP, SERVER_USER, CF_ZONE_ID, CF_API_TOKEN). Full workflow template and new-project checklist is in `~/.claude/CLAUDE.md`.
