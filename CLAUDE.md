# Uni — Claude Instructions

## Project Overview

Static site for uni.nyc. Currently a holding page; will grow into a full site.

## Stack

Vanilla HTML/CSS (no build step). When the full site is ready, the plan is to scaffold React + Vite and update the deploy workflow to add a build step.

## Deployment

Push to `main` → GitHub Actions → rsync to server → Cloudflare cache purge.

See `.github/workflows/deploy.yml`. The global `~/.claude/CLAUDE.md` has the full deployment workflow template and required secrets.

**Deploy target**: `/home/uni.nyc/public_html/`

## Growing to a full site

When it's time to build out the site:
1. Scaffold React + Vite (`npm create vite@latest . -- --template react`)
2. Update `deploy.yml`: add `setup-node`, `npm ci`, `npm run build` steps; change rsync source to `dist/`
3. Update `.claude/settings.local.json` to allow `npm` commands
