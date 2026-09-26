# Garden Oasis

An idle garden game with rebirths, pets, auction house, food critic, and cosmic progression. Built as a single-page app (plain HTML + CSS + vanilla JS, no build step, no dependencies beyond the Tailwind CDN in `index.html`).

## How to run it

Either option works — open the file in any modern browser (Chrome/Edge recommended):

- **`index.html`** — the UI. Must be in the same folder as `game.js` (it loads the game logic via `<script src="game.js">`).
- **`Garden Oasis (single-file).html`** — the whole game inlined into one self-contained file. Use this if you only want to carry one file around.
- **`Garden Oasis.zip`** — the packaged bundle (all three files) for easy download.

### Files

| File | Purpose |
| --- | --- |
| `index.html` | All screens, HTML and CSS |
| `game.js` | All game logic (single script, no modules) |
| `Garden Oasis (single-file).html` | Auto-generated fallback (rebuilt from `index.html` + `game.js`) |
| `Garden Oasis.zip` | Distribution zip |

## How to play

1. Give your garden a name on the welcome screen and press Start.
2. Plant seeds on the 5x5 grid, water them, harvest for coins.
3. Buy seeds, gear and pets from their screens. Pets run passive abilities on a timer.
4. Visit the Food Critic and cook recipes for Critic Points and Experienced Chef Points.
5. Reach 125 Critic Points for a Gourmet Egg; incubate and hatch it for one of 5 hidden egg pets.
6. Make $2M to hit Level 10 and use the Aethelgard Sanctuary in the Ascend screen for a **Cosmic Rebirth** — everything resets for a Rebirth Token and permanent upgrades.

## What was done over the last 2 days

This is the complete build log for the last two development sessions.

### Day 1 — Rebuild, welcome screen, and file split

- Salvaged and rebuilt the entire game from a single legacy HTML file into a clean, validated codebase.
- **Welcome screen overhaul**: new cosmic start screen with animated gradient sky, twinkling starfield, drifting aurora blobs, floating flora, name input, rich feature badges, and a pulsing card.
- **Rebirth stage 2**: fixed the vault — Venus Flytrap and Solar Bloom machines now reward into an iridescent bucket.
- **Rebirth stage 3**: Transcendent rarity added end-to-end — rarity badge styling, upgrade label, auction chips. Added a duplicate-function guard.
- **Split the project** into `game.js` + `index.html` (game logic extracted from the inline script; Tailwind CDN kept in the HTML). A single-file build is auto-generated as a fallback.
- **Start-button hardening**: the boot sequence now exposes `goGarden` globally, guards against double-start, sets `window.gameReady`, traps boot errors, and renders a small on-screen BOOT DIAG overlay for diagnostics. The button also alerts helpfully if `game.js` is missing (e.g. someone opened `index.html` alone).
- **Real verification**: exercised the game in headless Chrome — boot produces zero runtime errors, and screenshots were captured for the welcome and garden screens. Opening either build in a real browser works.

### Day 2 — Gourmet Egg system, sanctuary polish, GitHub

- **Gourmet Egg system** (the v12 addition):
  - Every 125 Critic Points automatically grants 1 Gourmet Egg.
  - New **Gourmet Egg Incubator** on the Food Critic screen: incubate (5 minutes), watch the progress bar and timer, then hatch.
  - Hatch table: Bagel Bunny (50%), Pancake Mole (38%), Sushi Bear (7%), Spaghetti Sloth (4%), French Fry Ferret (1%).
  - Each egg pet has a bespoke passive ability wired into the pet engine:
    - Bagel Bunny — eats a carrot for a 6x fortune.
    - Pancake Mole — digs up coins, gear, or fruit.
    - Sushi Bear — may freeze/chill a plant and feeds friends.
    - Spaghetti Sloth — grows Pasta/Sauce/Meatball mutations and merges all three into SPAGHETTI.
    - French Fry Ferret — levels up a random pet; can't be mimicked or refreshed.
  - Eggs are protected from the sell and gambling systems so they can't be accidentally destroyed, and hidden from the pet shop until hatched.
- **Sanctuary artistic pass**: reflowed the ascension screen into a more magical presentation — aurora veil and ribbon layers, shooting stars, floating light motes, an animated gradient sanctuary title with a sweeping underline, an orbital rune ring around the obelisk with a pulsing halo, a spinning conic-gradient border on the singularity card, a flowing sheen across the Cosmic Rebirth button, panel light-sweeps, and hover glows on upgrades and vault items. Plus global polish: themed scrollbars, text selection color, and a gentle screen entrance animation.
- **GitHub publishing**: installed Git and GitHub CLI, initialized the repo, and pushed everything here.

## Tech notes

- `game.js` is one flat script loaded by `index.html`. The single-file build is produced by inlining `game.js` into `index.html` — regenerate it whenever either source file changes.
- Game state persists in `localStorage` under the player-chosen garden name.
- Validated with esprima (JS parse), a duplicate-function scanner, feature checks, and headless-Chrome boot tests before each release.

## Changelog

- **v12.0** — Gourmet Egg system, incubator, 5 egg pets + abilities, pasta/spaghetti mutations, sanctuary art pass.
- **v8.0** — Rebuilt launch baseline: proven booting in Chrome with zero errors.