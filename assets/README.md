# Wild Worlds assets

`wild_worlds.html` already draws every picture and synthesises every sound itself, so these folders can stay empty and the game still works.

Any file you add here **with the exact name below** replaces the built-in version the next time the page loads. Nothing in the HTML needs editing. Images are `.png`, audio is `.mp3` (change `ASSET_IMG_EXT` / `ASSET_AUDIO_EXT` at the top of the script to use other formats).

```text
assets/
├── images/
│   ├── animals/       one picture per animal
│   ├── food/          one picture per food card
│   ├── backgrounds/   menu + one picture per habitat zone
│   └── ui/            logo
├── fonts/             brand fonts (Cranberry, Handy Casual)
└── audio/
    ├── music/         looping background tracks
    └── sfx/           short sound effects
```

## images/animals/ (square, transparent background, about 450 × 450)

| World  | Files |
|--------|-------|
| Safari | `giraffe` `elephant` `lion` `zebra` `rhino` `panda` `panther` `monkey` `wombat` `kangaroo` `koala` |
| Aviary | `kookaburra` `cockatoo` `lorikeet` `swan` `ibis` `emu` `galah` `penguin` `seaeagle` |
| Ocean  | `clownfish` `seahorse` `octopus` `turtle` `stingray` `whale` `dolphin` `shark` `crab` `starfish` |

Example: `assets/images/animals/wombat.png`

## images/food/ (square, transparent background, about 220 × 220)

`grass` `leaves` `bamboo` `meat` `fruit` `gumleaves` `fish` `bugs` `lizard` `nectar` `seeds` `waterplants` `krill` `seagrass` `clam` `shrimp` `algae` `crabs`

## images/backgrounds/ (1920 × 1080 each)

Each world scrolls sideways through four zones, and each zone is one screen wide. Keep the bottom 220 px plain, because the card tray covers it.

| File | Zone |
|------|------|
| `menu` | Main menu, quiz and sticker book |
| `safari_savanna` `safari_bamboo` `safari_jungle` `safari_bush` | Safari zones, left to right |
| `aviary_gum` `aviary_billabong` `aviary_outback` `aviary_shore` | Aviary zones, left to right |
| `ocean_reef` `ocean_seagrass` `ocean_open` `ocean_shallows` | Ocean zones, left to right |

Animals are placed at fixed spots (the `x`, `gy` / `cy` values in the `WORLDS` table in the script), so painted branches and rocks should line up with those, or adjust the numbers.

## images/ui/

`logo.png` replaces the "WILD WORLDS" title on the menu (about 900 px wide, transparent).

## fonts/

The brand fonts are Cranberry (titles), Fredoka (buttons and subheadings) and Handy Casual (body text and animal facts). Fredoka loads from Google Fonts. Cranberry and Handy Casual are not on Google Fonts, so add the font files here with these names (`.woff2`, `.ttf` or `.otf`):

| File | Used for |
|------|----------|
| `Cranberry.woff2` | Titles |
| `HandyCasual.woff2` | Body text and animal facts |

Until the files are added, the game falls back to Lilita One (titles) and Patrick Hand (body text).

## audio/music/ (seamless loops)

`menu` `safari` `aviary` `ocean` `quiz`

## audio/sfx/

| File | Plays when |
|------|-----------|
| `click` | a button is pressed |
| `tap` | an animal or card is tapped |
| `pickup` / `putback` | a card is picked up / dropped back in the tray |
| `pop` | new cards arrive |
| `whoosh` | the view slides or a panel opens |
| `correct` / `wrong` | right or wrong answer |
| `munch` | an animal eats |
| `star` | a star is earned |
| `fanfare` | a world or quiz is finished |

## Opening the game

Double-clicking `wild_worlds.html` works. For the smoothest graphics, serve the folder instead, for example `python3 -m http.server` and open `http://localhost:8000/wild_worlds.html`.
