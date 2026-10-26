# Obsidian Vault Template

A reusable scaffold for bootstrapping a new Obsidian vault on a fresh machine.
Contains the `.obsidian/` configuration (settings, plugins, themes, snippets)
and an empty folder structure — no notes.

## What's inside

- `.obsidian/` — settings, installed plugins, themes, CSS snippets
- `1. Templates/` — note templates (tracked)
- `2. Diary/`, `3. InTags/`, `4. Main/`, `5. Drafts/`, `_Attachements/` —
  empty placeholders kept by `.gitkeep`. Daily-note year/month subfolders
  under `2. Diary/` are created automatically by the daily-notes plugin.

## Bootstrap a new machine

1. Clone the repo to wherever you keep your vault:
   ```sh
   git clone <repo-url> MyVault
   cd MyVault
   ```
2. Open Obsidian, choose **Open folder as vault**, and pick the cloned
   directory.
3. Trust the vault when prompted so community plugins can load.
4. Work through the **Setup todos** below.

## Setup todos

These don't ship in the repo — install / configure manually on each new
machine to fully reproduce the original vault experience.

### External binaries

- [ ] **pngquant** — used by the `image-converter` plugin for PNG
  optimization. Plugin will silently skip optimization if missing.
  - macOS: `brew install pngquant` (lands at `/opt/homebrew/bin/pngquant`)
  - Linux: `apt install pngquant` or distro equivalent
  - Windows: download from <https://pngquant.org/>
  - After install, open Obsidian → Settings → Image Converter → set
    `pngquant executable path` to the install location if it differs from
    `/opt/homebrew/bin/pngquant`.

- [ ] **ffmpeg** *(optional)* — `image-converter` can use it for video
  thumbnails. The current config leaves the path blank, so set it only
  if you want that feature.
  - macOS: `brew install ffmpeg`

### Obsidian-side

- [ ] On first open, **trust the vault** so community plugins activate.
- [ ] If you sync this vault across machines via Git, remember `.DS_Store`
  and `workspace*.json` are ignored — pane layout won't follow you, and
  that's intentional.

## What is *not* tracked

The following are gitignored because they're machine-specific:

- `.obsidian/workspace*.json` — pane layout (rebuilds itself on first open)
- `.obsidian/cache` — search index

Plugin `data.json` files **are** tracked — they hold most of your
customization (themes, presets, calendar sources, etc.), and the current
set was inspected and contains no secrets. If you later install a plugin
that authenticates (Readwise, sync plugins, anything with API tokens),
review its `data.json` before committing and add a targeted ignore line
for that one plugin if it carries credentials.

## Adding notes

Notes (`*.md`) are gitignored on purpose so this template stays a clean
scaffold. The exceptions are `README.md` and anything inside
`1. Templates/` — those are tracked. If you want to track a one-off
note elsewhere, add it explicitly with `git add -f`.
