# Obsidian Vault Template

A reusable scaffold for bootstrapping a new Obsidian vault on a fresh machine.
Contains the `.obsidian/` configuration (settings, plugins, themes, snippets)
and an empty folder structure — no notes.

## What's inside

- `.obsidian/` — settings, installed plugins, themes, CSS snippets
- Top-level folders (`1. Templates`, `2. Diary`, `3. InTags`, `4. Main`,
  `5. Drafts`, `_Attachements`) — empty placeholders kept by `.gitkeep`

## Bootstrap a new machine

1. Clone the repo to wherever you keep your vault:
   ```sh
   git clone <repo-url> MyVault
   cd MyVault
   ```
2. Open Obsidian, choose **Open folder as vault**, and pick the cloned
   directory.
3. Trust the vault when prompted so community plugins can load.

## What is *not* tracked

The following are gitignored because they're machine-specific or may contain
local paths / tokens:

- `.obsidian/workspace*.json` — pane layout (rebuilds itself on first open)
- `.obsidian/cache` — search index
- `.obsidian/plugins/*/data.json` — per-plugin runtime state

After cloning, some plugins (calendars, sync-style plugins, anything that
authenticates) may need to be reconfigured or re-logged-in because their
`data.json` is intentionally not shipped.

## Adding notes

Notes (`*.md`) are gitignored on purpose so this template stays a clean
scaffold. If you want to track a specific note here (e.g. this README),
add it explicitly with `git add -f`.
