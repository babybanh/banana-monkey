# Banana Monkey

Fast local reskin of the successful Catch Me If You Can game foundation.

This first pass keeps the proven movement, collecting, chasing, hazard, credits, tuning, and restart behavior while swapping in Ellie's Banana Monkey music and beach artwork.

## Run Locally

```bash
npm install
npm run dev
```

Build check:

```bash
npm run build
```

## Main Editing File

Start here:

```text
src/gameConfig.js
```

That file controls the title/copy, credits, music path, stage backgrounds, character sizes, speeds, hitboxes, UI positions, joystick zone, z-order, spawn margins, phase thresholds, and tuning storage keys.

## Role Map

The game still uses the Catch Me mechanics internally, but the Banana Monkey skin maps them like this:

| Banana Monkey role | Current internal role | Browser-ready file |
| --- | --- | --- |
| Banana Hand follower | `bunbun` / `player` | `public/assets/images/reskin-lab/characters/player.png` |
| Banana Monkey lead | `bun` / `lead` | `public/assets/images/reskin-lab/characters/lead.png` |
| Banana collectible | `banana` | `public/assets/images/reskin-lab/characters/collectible.png` |
| Bomb hazard | `bomb` | `public/assets/images/reskin-lab/characters/hazard.png` |
| Shark first chaser | `gorilla` | `public/assets/images/reskin-lab/characters/chaser-a.png` |
| Alligator second chaser | `g2` | `public/assets/images/reskin-lab/characters/chaser-b.png` |
| Sunset beach background | full-frame background | `public/assets/images/reskin-lab/backgrounds/sunset-stage.png` |
| Sunny beach alternate | full-frame background option | `public/assets/images/reskin-lab/backgrounds/sunny-stage.png` |
| Concept modal image | concept image | `public/assets/images/reskin-lab/concept/original-concept.png` |
| Ellie music | background music | `public/assets/audio/music/banana-monkey-theme.mp3` |

Original full-size source files are archived in `asset-sources/banana-monkey/`. Only optimized game-ready copies should live under `public/assets/images/reskin-lab/`.

## Current Draft

- Sunset beach is the default background; sunny beach is available in the tuning panel.
- Banana Monkey starts as the lead character.
- Banana Hand appears after 9 bananas and follows the monkey.
- Keyboard movement with arrow keys and WASD.
- Floating joystick for mouse/touch.
- Banana scoring, hearts, shark/alligator chasers, bombs, combo bonus, invincibility, auto-restart, and music toggle.
- Credits link Ellie to `https://www.youtube.com/watch?v=5RmrYkf2INU`.
- Debug panel toggles with backtick or F2; tuning panel toggles with `T`.

## First-Pass Boundaries

- Local playable shell only.
- No GitHub/Vercel deployment yet.
- Do not copy from Attack of Ziziphus for this project.
