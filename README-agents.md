# Ramadas.net — agent briefing

Personal landing page: a single static `index.html` (all CSS/JS inline, Geist fonts) plus `favicon.svg`/`favicon.png`, served as Cloudflare Workers static assets on `ramadas.net` and `www.ramadas.net`.

## Stack

- No build step, no `package.json`, no tests — edit `index.html` directly
- `wrangler.jsonc`: `assets.directory: "."`, `workers_dev: false`, custom-domain routes only

## Commands

- deploy: push to `master` → `.github/workflows/deploy.yml` runs `cloudflare/wrangler-action` (wrangler 4.152.0); manual deploy: `bunx wrangler deploy`
- local preview: `bunx wrangler dev` (serves the assets dir)

## Conventions

- Every file at the repo root becomes a public asset except paths listed in `.assetsignore` — update it before adding dotfiles, notes or configs that shouldn't be published

## Pointers

- `AGENTS.md` + `.agents/` — shared rules (the Nuxt/TypeScript sections don't apply to this repo) · `REVIEW.md` — PR review-bot instructions
