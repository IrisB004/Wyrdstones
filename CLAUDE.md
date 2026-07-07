# Wyrdstones

Norse-themed mahjong-solitaire game. The entire game is `index.html` — one
self-contained file with inline CSS, JS, and SVG. Keep it that way: no build
step, no external assets, no frameworks. Google Fonts is the only network
dependency (the game degrades gracefully without it).

## Layout

- `index.html` — the whole game (styles, markup, logic in one file)
- `design/` — the exported Claude Design bundle this project's tile art is
  based on. Treat it as a read-only reference; don't edit it.
  - `design/project/Nordic Mahjong Tiles.dc.html` — tile sheets. Sheet `2a`
    is the Slate & Silver shell, sheet `2b` is Bone & Rune. Exact colors,
    gradients, and shadows in the game were lifted from these.
  - `design/chats/chat1.md` — design intent and decisions.

## Architecture notes (index.html)

- Tile shells are driven by CSS custom properties on `.board-outer`;
  `.theme-bone` overrides them for the ivory shell. Add new themes the same
  way rather than duplicating tile rules.
- `LEVELS` defines the realms. Layer grids are in half-tile units; **every
  layout's tile count must be divisible by 4** or the dealer breaks.
- `generateBoard()` guarantees solvable deals by simulating a legal clearing
  sequence and assigning matched types along it. Don't replace it with
  random assignment.
- Sounds are Web Audio synthesis in the `sfx` object; no audio files.

## Verifying changes

Playwright + Chromium are preinstalled in cloud sessions. Load the page
headless from `file://`, check for `pageerror` events, confirm tile counts
per level, and click a free matching pair to confirm removal works.
`require('/opt/node22/lib/node_modules/playwright')` and launch with
`executablePath: '/opt/pw-browsers/chromium'`. A cert error fetching Google
Fonts is expected in the sandbox and harmless.
