# Wyrdstones — A Norse Rune Solitaire

A mahjong-solitaire game with a Norse theme: clear stacked rune stones from the
board by matching free pairs. Built as a **single self-contained HTML file** —
no build step, no dependencies, no assets. Open `index.html` in any browser and
play.

## Play

Open `index.html`, or serve the repo root with any static file server
(the game also works when hosted on GitHub Pages).

- Click a **free** stone (nothing on top, open on the left or right side),
  then click its match — same rune or emblem — to remove the pair.
- Clear all stones to win the realm.
- **Seer's Sight** reveals a valid pair; **Reshuffle Stones** re-deals the
  remaining stones in place.

## Game modes

**Saga** — journey through the Nine Realms (Midgard, Vanaheim, Alfheim,
Nidavellir, Jotunheim, Niflheim, Muspelheim, Helheim, Asgard), five boards
per realm, 45 in all. Boards grow from ~50 to ~130 stones and unlock
sequentially; realms alternate between the Slate & Silver and Bone & Rune
tile shells from the Claude Design sheets (see `design/`). Progress and best
times are stored in `localStorage`.

**Daily Rune** — one seeded board per calendar day: everyone in the world
gets the same deal. Clearing it earns a trophy; the bar tracks total
trophies and current streak, and the calendar shows the month at a glance.

**Large Tiles** — accessibility toggle: the board never shrinks to fit the
window; it pans instead, keeping stones full-size and readable.

## The tiles

- **24 Elder Futhark runes** (real Unicode Runic-block characters), 4 copies
  each style-permitting per deal
- **5 Norse emblems** drawn as inline SVG: raven, wolf, Mjölnir, longship,
  and Yggdrasil

Every deal is **guaranteed solvable**: the board builder simulates a legal
clearing sequence in reverse, assigning matching types as it goes.

Sound is synthesized live with the Web Audio API (stone clacks, a lur-horn
win call) — no audio files.

## Design provenance

The tile look comes from a Claude Design project, **"Nordic Mahjong tile
designs"**, preserved in full under `design/`:

- `design/project/Nordic Mahjong Tiles.dc.html` — the tile sheets
  (Slate & Silver = sheet 2a, Bone & Rune = sheet 2b)
- `design/chats/chat1.md` — the design conversation and decisions
- `design/project/uploads/` — commissioned raven/wolf tile art (not yet
  embedded in the game)
