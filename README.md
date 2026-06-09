# savagepvp-assets

Public image assets for the **SavagePvP** Discord bot's tribe-log feed. This repo
exists because the bot repo is private, and Discord's embed proxy can only render
images from **public** `raw.githubusercontent.com` URLs.

## Layout
- `dinos/` — creature renders (sourced from Dododex), one `<slug>.png` per species.
  The bot maps an in-game creature name → slug via `src/utils/dinoImages.js`; any
  species not mirrored here falls back to the live Dododex CDN.
- `structures/` — ARK structure icons (sourced from ark.wiki.gg), one per feed
  category (turret, vault, generator, …).
- `manifest.json` — what resolved / what 404'd during extraction (see the bot's
  `scripts/extract-assets.js`).

## Regenerating
Run `node scripts/extract-assets.js --force` in the bot repo, then commit the
updated `dinos/` + `structures/` here and regenerate `src/data/dinoAssets.json`
in the bot from the mirrored filenames.
