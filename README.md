# Garden Oasis

An idle garden game: plant, water, harvest, cook, and ascend. Runs in any modern browser, no install needed.

## Quick start

Open **`Garden Oasis (single-file).html`** anywhere — that one file contains the whole game.

Prefer the split version? Keep **`index.html`** and **`game.js`** in the same folder and open `index.html` (it loads `game.js`; an on-screen BOOT DIAG line confirms the game started clean, which should read `goGarden=function gameReady=boolean:true errs=[none]`).

`Garden Oasis.zip` bundles all three files for downloading/sharing.

## How the game works

The core loop:

1. **Plant** seeds from the Shop into your 5x5 garden grid.
2. **Water & harvest** your plants to sell for coins.
3. **Buy better seeds, gear, and pets.** Rarities go Common → Rare → Mythic → Divine → Prismatic → Exotic → Iridescent/Transcendent.
4. **Cook** harvested produce into dishes and submit them to the Food Critic for Critic Points.
5. **Ascend.** Reach the Aethelgard Sanctuary (Ascend screen) and a price point, pay the cost, and perform a Cosmic Rebirth — you lose your garden but gain a permanent Rebirth Token and unlockable permanent upgrades.

Everything autosaves to `localStorage` under your garden name. Your garden keeps growing while you're away (plants grow over real time).

## Feature tour

- **Garden** — 5x5 grid, watering retains plant value, growth/collection bonuses, watering-can refills.
- **Shop** — 6 seed rarities, hybrid plants, dynamic pack pricing.
- **Inventory** — all your seeds, harvested plants, gear, tools and crafted food.
- **Pets** — adopt pets that run passive abilities on cooldown (food, money, mutations, lore, leveling). New hatchable egg pets are listed below.
- **Auction** — rare seeds on a price timer; snipe the dip before 30-second price drops.
- **Index / Vault** — plant collection log plus exotic and transcendent vault machines (Venus Flytrap, Solar Bloom).
- **Gear** — tools that boost planting, watering, harvesting, and passive income.
- **Food Critic** — cook dishes from master recipes, submit them for Critic Points, claim milestone rewards every 25/75/150/… points, and use the Gourmet Egg Incubator (1 egg per 125 Critic Points, 5-minute hatch).
- **Rebirth / Sanctum** — Cosmic Rebirth, Rebirth Tokens, permanent sanctum upgrades, exotic vault machines.
- **Events** — seasonal token events and special rules.
- **DLC codes** — redeemable codes grant bonuses.
- **Admin / console** — sandbox tools (unlocked with a secret code).

### Gourmet Eggs and egg pets

Earn a Gourmet Egg for every 125 Critic Points, incubate it (5 minutes), then hatch for one of:

| Egg pet | Chance | Passive |
| --- | --- | --- |
| Bagel Bunny | 50% | Eats a carrot for a 6x fortune |
| Pancake Mole | 38% | Digs up coins, gear, or treasure |
| Sushi Bear | 7% | Freezes/chills a plant and feeds friends |
| Spaghetti Sloth | 4% | Grows Pasta/Sauce/Meatball mutations; merges all three into SPAGHETTI |
| French Fry Ferret | 1% | Levels up a random pet; cannot be mimicked or refreshed |

## Controls

- Bottom navigation switches between screens (Garden, Shop, Inventory, Pets, Gear, Sell, Ascend, Events, etc.).
- Keyboard nav available for main screens via the nav links.

## Upcoming events and features

Current dev focus (v12.0, "Grand Feast"):

- Pierre's Bakery with a 3-slot oven queue and 5 bakeable pastries — already shipping.
- Critic Cravings: a rotating golden-banner dish; fulfill it three times for a golden chef badge.
- Weekly Cook-Off with a GOLDEN SPATULA award.
- World Chef Rankings and the Oasis Gazette archive.
- Le Jardin Restaurant ($25M) and Rat Chef Remy ($2.5M) passive income.

On the roadmap after that:

- **Eternal Zen Garden** — a seasonal event with serenity-themed plants and meditation bonuses.
- **Chef's Table expansion** — more of Pierre's recipes and an oven upgrade path.
- **Community World Chef Rankings** — a real online leaderboard.
- **Festival of Garnish** — mini-event cooking battles.
- **Mobile-first polish** — better touch layout and performance on phones.

## Technical notes

- Plain HTML/CSS/JS, no framework, no build step. `game.js` is one script; the single-file build inlines it into `index.html` and should be regenerated whenever either changes.
- Validated on each release with a JS syntax check (esprima), a duplicate-function scanner, and headless-Chrome boot tests (zero runtime errors).
- Credits: this game's development has been assisted by an opencode AI agent across its recent builds.

## Changelog

- **v12.0** — Gourmet Eggs + incubation, five egg pets and abilities, pasta/spaghetti mutations, sanctuary art pass, Grand Feast kitchen (Pierre's Bakery, Critic Cravings, Cook-Off GOLDEN SPATULA, World Chef Rankings, Oasis Gazette, Le Jardin + Remy).
- **v8.0** — Rebuilt launch baseline, welcome overhaul, file split, start-button hardening.