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
- Two modes: **Saga** (9 realms × 5 boards, sequential unlock, progress in
  `wyrd2-saga`) and **Daily Rune** (date-seeded deal via `mulberry32`, so the
  same board is dealt worldwide each day; trophies in `wyrd2-daily`). Layouts
  come from `sagaLayers(g)`, which generates pyramid stacks in half-tile
  units; **tile counts must stay even** or the dealer breaks.
- `generateBoard(layers, rnd)` guarantees solvable deals by simulating a
  legal clearing sequence and assigning matched types along it. Don't replace
  it with random assignment, and keep every random choice inside it drawn
  from the passed `rnd` — that's what makes the Daily Rune deterministic.
- Sounds are Web Audio synthesis in the `sfx` object; no audio files.
- Functional model (journey progression, daily challenge + trophies, large
  tiles) follows Vita Mahjong; all art, names, and code are original.

## Verifying changes

Playwright + Chromium are preinstalled in cloud sessions. Load the page
headless from `file://`, check for `pageerror` events, confirm tile counts
per level, and click a free matching pair to confirm removal works.
`require('/opt/node22/lib/node_modules/playwright')` and launch with
`executablePath: '/opt/pw-browsers/chromium'`. A cert error fetching Google
Fonts is expected in the sandbox and harmless.
