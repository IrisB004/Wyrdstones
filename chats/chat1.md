# Nordic Mahjong tile designs

_Started 2026-07-07 20:38 UTC_

---

## User

designing tiles for a Nordic Mahjong game for use as an app. Please get sizing accurate and use these designs for influence on the style. Include all things Nordic such as Ravens, Wolves, Odin's hammer, Runes, etc

## Assistant

Beautiful references. Before I build the tile set, a few questions:

_[tool: questions_v2]_

## User

Questions answered:
- deliverable: A few sample tiles in different styles to pick from
- art_style: Have it be cohesive but mixed. All Nordic style. Some can be simple and some more elaborate. There needs to be differences as in all Mahjong games. Please reference the most popular Mahjong games for reference. The difference is this will be Nordic themed.
- suits: All of the above mentioned. In a 144-tile Mahjong game, there are exactly 36 unique types of tiles, and each type has 4 identical matching tiles making up the set
- tile_shape: Classic mahjong 3:4 portrait
- palette: Decide for me
- use_images: Decide for me
- variations: Decide for me
- target: Decide for me

## Assistant

_[tool: read_skill_prompt]_

_[tool: image_metadata]_

Building the sample-tile options now — three cohesive directions plus a true-scale check.

_[tool: dc_write]_

_[tool: ready_for_verification]_

Four sample directions are up, all classic 3:4 tiles:

- **1a Bone & Rune** — ivory tiles, engraved slate/rust glyphs; max readability, closest to classic mahjong apps
- **1b Slate & Silver** — dark tiles matching your references, with your raven/wolf art as bonus tiles
- **1c Hybrid** — ivory frames with art inlays; simple suits, elaborate honors
- **1d True-scale check** — 46×61pt tiles on a 390pt phone width, all above the 44pt hit target

Suit mapping covers all 36 types: Runes/Ravens/Fangs 1–9, Winds→Gods, Dragons→Mjölnir/Yggdrasil/Valknut, Flowers/Seasons→Realms+Seasons. Tell me which direction (or mix) to expand into the full 36-tile sheet.

## User

Found issues — fixing…

## Assistant

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: ready_for_verification]_

Fixed — the Raven 3 ring pips are now smaller with tighter diagonal offsets, fully inside the tile face and clear of the corner index in both 1a and 1b. Pick a direction (or mix) and I'll build the full 36-tile sheet.

## User

let's start Slate & Silver. the symbols need to fill more of the tile. I would also like some of the Bone & Rune for some as there will be different levels and different backgrounds to keep the app interesting

## Assistant

Expanding into the full Slate & Silver set with bigger symbols, plus the ivory level-theme variant — new turn on top.

_[tool: dc_js_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: ready_for_verification]_

Turn 2 is up top:

- **2a — full Slate & Silver sheet**: all 42 faces. Runes 1–9 with 96px glyphs, Raven/Fang pips that scale up on low counts to fill the tile, Gods (Odin/Thor/Freya/Loki), Relics (Mjölnir/Yggdrasil/Valknut), Realms with your art (Vanaheim needs a 4th artwork — flagged as a drop-in slot), and four Seasons.
- **2b — Bone & Rune shell**: same face system on ivory for alternate levels; only palette and shell swap, so faces stay consistent across themes.

Next I can put 2a on a real stacked board layout, or expand the ivory sheet fully.

## User

Midgard should be this: The Jörmungandr Ouroboros: A serpent biting its own tail in a perfect circle. In mythology, the giant Midgard Serpent completely surrounds the realm of humanity to hold the world's oceans in place.

## Assistant

_[tool: dc_html_str_replace]_

_[tool: show_html]_

_[tool: ready_for_verification]_

Midgard is now a Jörmungandr ouroboros — a silver serpent circling with head biting toward its tail, with a subtle dotted inner ring for the world's oceans, engraved in the same style as the other relic glyphs. The pixel-wolf art it replaced is still available if you want it on Vanaheim.

## User

for Vanaheim the symbol should incorporate  some of these elements: The Boar or Stag: In Norse myth, the Vanir god Freyr rides Gullinbursti, a golden boar. In modern representations of the Nine Realms, a boar head or stylized antlers are frequently used as a shorthand icon for Vanaheim to emphasize its wild, natural connection.Lush, Overlapping Vines or Leaves: Pop culture interpretations—such as the representation of Vanaheim in games like God of War—rely heavily on botanical geometry, using leaf patterns or growing vines arranged in circular, balanced knots to highlight the realm's status as a wild, magical cradle of life. Animal TotemWild Boar or FalconGullinbursti (Freyr's boar) or Freyja’s falcon cloak.

## Assistant

_[tool: dc_html_str_replace]_

_[tool: ready_for_verification]_

Vanaheim now shows stylized stag antlers rising inside a circular vine knot ringed with leaves — wild-growth shorthand in the same engraved silver stroke style as Yggdrasil and Midgard. If you'd rather lead with Gullinbursti, I can swap the antlers for a boar-head mark or commission-style art slot instead.

