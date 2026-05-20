# laurene-content

Weekly content delivery for Laurène Châtelain. Static site served from
Cloudflare Pages.

Each week lives under a token-suffixed directory:

```
W21-7f3a9b/
W22-2c4ef0/
W23-...
```

URLs are unguessable random per-week tokens (6 hex chars). Anyone with
the URL can view; URLs are not auto-discoverable.

## How it's built

`weekly-publisher.py` in the `hermes` repo
(`hermes/scripts/laurene-pipeline/weekly-publisher.py`) reads each
week's rendered carousel PNGs from
`Obsidian/LaureneMarketing/50-Outputs/W<NN>-YYYY-MM-DD/` and writes
the static site here, then commits + pushes.

This repo is intentionally a thin presentation layer — all generation
logic lives in `hermes/`.

## Deploy

Cloudflare Pages auto-builds on every push to `main`. No build command
or framework — pure static HTML/CSS/PNG.

## Versioning

Old weeks are kept forever. Cloudflare Pages free-tier bandwidth is
unmetered.
