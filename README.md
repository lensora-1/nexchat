# NEXCHAT

NEXCHAT is a Cloudflare Worker application for private document and file exchange.

## Hosting and data

- Runtime: Cloudflare Workers
- Database: Cloudflare D1 (`nexchat-main-db`)
- Private object storage: Cloudflare R2 (`nexchat-media`)
- Worker URL: https://nexchat.m7njordan.workers.dev

The D1 database and R2 bucket are existing production resources. Do not delete, recreate, or migrate them without an approved migration plan.

## Deploy locally

Install Wrangler, authenticate with Cloudflare, then run:

```bash
npx wrangler deploy
```

## Automatic deployment from GitHub

The workflow in `.github/workflows/deploy.yml` deploys on pushes to `main`.
Add a repository Actions secret named `CLOUDFLARE_API_TOKEN` with permission to edit Workers and access the configured D1/R2 resources. The Cloudflare account ID is configured in `wrangler.toml`.

Never commit API tokens, passwords, session secrets, or user data.
