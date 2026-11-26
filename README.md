# Once Upon a Gotcha

**A fairytale troll platformer where the storybook is alive and wants you gone.**

*500 pages. One tin soldier. One door per page. The floor has opinions.*

Version 1.0 · single-file HTML5 game · plays on phones and desktops · no install, no server, no account

---

## 1. What this game is

You are a one-legged tin soldier. Each page of the storybook is a single-screen board. Your only job is to reach the door.

The trick is that the page is trying to kill you. The floor rises, drops, slides, shoves and lies. Walls close in. Ceilings come down. Springs bounce you into thorns. Doors run away. Portals send you somewhere worse. The obvious, easy move is almost always part of the trap.

You will die. A lot. That is the design:

1. You see something safe-looking, and you do the obvious thing.
2. The page kills you. Restart is instant.
3. Now you know how it killed you, so you try again.
4. The page kills you a different way, because there are several layers of tricks.
5. Eventually you work out the right route, and the door opens.

The pages are built to be learned through deaths. Most pages kill you more than once before you get through. Every page is beatable, and a solver bot has proven it.

The game is inspired by the "troll level" puzzle genre (the *Level Devil* style), re-skinned as a storybook with fairytale hazards: wolves, witches, rats, gingerbread, mirrors, beanstalks, trolls and midnight clocks.

---

## 2. Quick start

### Play it
Open `game/index.html` in any modern browser. That is the whole game.

It is one self-contained file. It makes no network requests except an optional Google Fonts stylesheet for the storybook typeface. If the font cannot load, the game falls back to a system serif font and plays normally.

### Put it online (GitHub Pages)
1. Create a new GitHub repository.
2. Upload `game/index.html` to the repository root (name it `index.html`).
3. In the repository, go to **Settings → Pages**, choose the main branch and the root folder, and save.
4. After a minute or so, your game is live at `https://<your-username>.github.io/<repo-name>/`.

Any static host works the same way (Netlify, Cloudflare Pages, itch.io HTML5 upload, your own server). Nothing needs a backend.

### Add it to a phone home screen
Open the hosted link in the phone browser and use **Share → Add to Home Screen** (iOS) or **Install / Add to Home Screen** (Android). The game is full-screen and touch-first.

---

## 3. Controls

| Action | Touch | Keyboard |
|---|---|---|
| Move left / right | ◀ ▶ on-screen buttons | Arrow keys or A / D |
| Jump | ▲ button | Space, Up arrow, W or Z |
| Restart the page instantly | (pause menu) | R |
| Pause | II button | Esc or P |
| Mute / unmute | (pause menu) | M |

Notes:
- Jump height is fixed. You cannot hold the button for a higher jump. Normal jumps clear about 3.4 tiles up, and the widest gap you can safely clear is 4 tiles.
- Restart is instant and free. Deaths are meant to be cheap.
- The game pauses automatically if you switch tabs or apps.

---

## 4. Features

### Campaign
- **500 pages in 25 chapters.** Pages escalate gradually, and each chapter has its own theme, name and look.
- **Chapter / page select.** You unlock pages as you clear them.
- **Tester mode:** a checkbox on the page-select screen unlocks every page. It is meant for playtesters and for skipping around.
- **Progress is saved** in your browser (localStorage key `gotcha_v1`). You can also reset it from the page-select screen with "Forget my progress".
- **Death counters.** Deaths for the current page and your total deaths are always on screen, and the ending shows your total.

### Feel
- **Instant restart** and a short, snappy death animation with screen shake.
- **Storybook death quips.** Each cause of death has its own set of wry lines, and the game gets a little more pointed if you keep dying on the same page.
- **Page captions.** Every page has a short caption that sets the mood without spoiling the trap.
- **Ghosts remember.** Hazards you have already seen reveal themselves from then on, within the same page.
- **Sound.** Synthesized sound effects for jumps, springs, pops, thuds, potions, vanishing floors and deaths. No audio files are needed. Mute with M or from the pause menu.
- **Responsive layout.** The game scales to any screen and handles rotation. It has a fixed 640×352 logical resolution with crisp pixel-style rendering.
- **Fixed-step 60 Hz physics**, so a page plays the same on every device.

### The trap catalog (what the pages can do to you)

**Floors and terrain**
- Floors that **drop out** from under you, sometimes before the door, sometimes right after you "feel safe".
- **Hidden floor spikes** and **hidden ceiling spikes** that only appear when you rise under them or step on them.
- **Pillars** that rise from the ground, sometimes to block you and sometimes to shove you into a pit.
- **Walls that walk.** Walls rise behind or ahead of you and chase you across the page, and you hide in a ditch or outrun them.
- **Ceilings** that close down, hang hidden spiked slabs, or drop teeth where you linger.
- **Hammers and thwomps** timed to punish the wrong rhythm.
- **Gingerbread crumble floors** that dissolve as you walk.
- **Conveyor belts**, shown as swirling wind, that carry you toward pits, pillars and hidden thorns.
- **Ice** that stops you from stopping.

**Props with a second job**
- **Springs** that bounce you into hidden thorns, and **hidden springs** that look like nothing.
- **Mimic doors** (the "candy door") that kill on touch, and **running doors** that flee as you approach.
- **Rolling jack-in-the-boxes** that charge from either side.
- **Rats** that follow the piper's tune.
- **Huffing wolves**: wind that pushes you into pits, or holds you back.
- **Pop-up brick walls** (the three little pigs) that appear and trap you.

**Rule-benders (sparkle zones)**
- **Mirror zones** that reverse your left and right controls.
- **Speed boots** (faster, so you overshoot your landing).
- **Fairy dust** (floatier jumps).
- **Honey** (slower movement while something rushes at you).
- Zone effects trigger when you pass through a column, so they cannot be hopped over.

**Portals**
- **Warp portals** that teleport you across a pit, back to the start of a section, or onto a floor that is already leaving. The scariest portal is often the right one, and sometimes it's the only one.

**Height (the "Tall Tale" and beyond)**
- Pages with **multiple floors**, so you drop down shafts to the next floor.
- **Shaft pairs.** Drop one way and the spikes slide out of your way. Drop the other way and the spikes move into it.
- **Wall shafts.** A wall swings across your fall in the wrong shaft.
- **Triple shafts.** Three holes, one safe.
- **Landing traps.** After a safe drop you can face a ceiling that waits for you to linger, a roof that follows you down, a chasing wall, a floor that leaves, flipped controls, or a gap before the door.
- **Fall damage is not a thing, but falling off the bottom of the screen is.**

---

## 5. The campaign: all 25 chapters

| # | Chapter | Pages | What it does to you |
|---|---|---|---|
| 1 | The Nursery Floor | 1–12 | Gentle start: a floor, a gap, and a gap that appears after you jump. |
| 2 | The Quiet Meadow | 13–18 | Nothing happens here. Probably. |
| 3 | Hammer Time | 19–25 | Timed hammers and floors that punish a bad rhythm. |
| 4 | The Bridge That Bites | 26–31 | Pits, pillars, and rides that end badly. |
| 5 | Do Not Stop | 32–39 | The floor leaves behind you. Keep moving. |
| 6 | Both Ways | 40–47 | Threats from both directions. |
| 7 | Do Not Jump | 48–55 | The habit you built is the trap. |
| 8 | Liars | 56–61 | Doors and floors that are not what they seem. |
| 9 | Looks Helpful | 62–69 | Every helping hand is an offer. |
| 10 | The Trick Rooms | 70–79 | Props with a second job. |
| 11 | Once Upon a Gotcha | 80–89 | The storybook turns on you; first fairytale set-pieces. |
| 12 | The Tall Tale | 90–101 | First multi-floor pages: shafts, portals, ceiling traps. |
| 13 | The Three Little Traps | 102–136 | Straw, sticks and bricks. Walls pop, winds blow. |
| 14 | Gingerbread Lane | 137–171 | Crumbling paths, rats and sugar. |
| 15 | The Ice Queen's Hall | 172–206 | Slippery, sparkly and very sincere about it. |
| 16 | The Beanstalk | 207–241 | Mostly tall pages: drops, shafts and portals. |
| 17 | The Witch's Pantry | 242–276 | Candy doors, hidden pins, ceilings with teeth. |
| 18 | Mirror, Mirror | 277–311 | Reversed controls, portal loops and wrong-way sparkles. |
| 19 | The Piper's Parade | 312–346 | Rats, rhythm thorns, hammers. |
| 20 | The Wolf's Hour | 347–381 | Wind, chasing walls, speed boots. |
| 21 | Under the Troll Bridge | 382–416 | Bridges, closing ceilings, honey. |
| 22 | The Hundred Doors | 417–451 | Doors, portals, and ceilings that bite. |
| 23 | The Clock Strikes Midnight | 452–480 | Everything you have learned, but louder. |
| 24 | Everything Is Alive | 481–490 | The page wants you gone. |
| 25 | The Last Page | 491–500 | Everything you learned, used against you. |

The full list of all 500 page names and captions is in `docs/LEVEL_GUIDE.md`.

---

## 6. How the levels were made

This is a large game for one project, so the levels come from a pipeline instead of being drawn by hand. All the code is in `source/`.

**Hand-built chapters (1–12, 24–25).** These were assembled from named "sections" (a sweeping wall, a bridge, a wave of falling floor, a mirror room, and so on). Chapters 1–11 and 24–25 are mostly layered by script. The hand design is in how the sections are chosen and ordered so that each page teaches before it kills.

**Generated chapters (13–23, 379 pages).** A generator mixes sections, overlays and trap modules for each chapter's theme, then keeps a candidate only if it passes all of these checks:
1. **A solver bot can beat it.** The bot is a weighted A* search over the same physics as the game. This proves the page is beatable.
2. **It is not trivially passable.** A set of blind "just run right" strategies must fail.
3. **It can kill you at least two different ways** under random play. This is what gives you the die, learn, die-differently loop.
4. **Variety pressure.** The generator prefers traps it has used least, so the chapters do not collapse into one repeated gimmick.

**Names and captions** come from a lore table keyed to the traps a page actually contains, so a page with a closing ceiling is named for the ceiling.

**Shared engine.** The browser game and the solver bot run the same deterministic physics file (`core.js`), so "the bot beat it" really does mean "the game can be beaten".

---

## 7. Project layout

```
OnceUponAGotcha-v1.0/
├── README.md                  this file
├── CHANGELOG.md               what was added, in order
├── game/
│   └── index.html             THE GAME. Single file. Deploy this.
├── docs/
│   └── LEVEL_GUIDE.md         all 500 pages: names and captions, by chapter
├── source/
│   ├── shell.html             page template (UI cards, styles)
│   ├── core.js                shared physics and rules (browser and bot)
│   ├── game.js                rendering, input, audio, UI, saving
│   ├── levels.js              generated level data and chapter table
│   ├── levels_head.js         hand-built level header (used by merge.py)
│   ├── build.js               assembles shell + core + levels + game → index.html
│   ├── puzzles.js             section builders (wall sweeps, bridges, stones...)
│   ├── ov.js                  overlay library (huff, ice, crumbs, rats, jack...)
│   ├── mods.js                newer trap modules (boots, belts, jaws, portals...)
│   ├── vboards.js             multi-floor builder, shafts, hand-built tall pages
│   ├── boards.js              board table, assembler, layering and tuning
│   ├── gen.js / genrun.js     the procedural generator and its driver
│   ├── plan.js                chapter plan for generation
│   ├── lore.py / naming.py    names and captions
│   ├── merge.py               boards.json → levels.js
│   └── boards.json            all 500 boards (terrain, acts, warps)
└── tools/
    ├── bot.js                 the solver bot (node bot.js all)
    ├── sols.js                records a solution for every page
    ├── solutions.json         a proven solution for every page (SPOILERS)
    ├── browser_test.py        replays every solution in a real browser
    └── stuck.js               random-play stuck-state detector
```

### Rebuilding the game from source
You need Node.js. From inside `source/`:

```
node build.js
```

This writes a fresh `index.html` from `shell.html`, `core.js`, `levels.js` and `game.js`.

### Re-verifying that every page is beatable
The tool scripts expect to sit next to the source files, so copy the contents of `tools/` into `source/` (or run them from a working folder that has both), then:

```
node bot.js all        # solver checks all 500 pages
node sols.js           # records solutions to sols.json
```

`browser_test.py` replays the recorded solutions in a headless browser and needs Python with Playwright installed.

### Regenerating or extending levels
`boards.json` is the source of truth for all 500 boards. To change chapter themes or counts, edit `plan.js` and `gen.js`, run `node genrun.js <chapter> 0 <count>`, then run `python3 naming.py` and `python3 merge.py` and rebuild. The generator also needs the `boards_121.json` base file, which is the hand-built set. If you want to regenerate, ask for the full working folder.

---

## 8. Technical notes

- **Resolution:** 640×352 logical, 40×22 tiles of 16 px, scaled to fit.
- **Simulation:** fixed 60 Hz step with fully deterministic state, so replays and the solver agree exactly.
- **Physics constants:** gravity 0.5, jump impulse −7.4, move speed 2.6, spring −12; player hitbox 10×14.
- **Safety nets:** falling off the bottom of the screen kills you (with a grace counter). If a moving floor ever leaves you embedded in solid ground, the game nudges you out or kills you rather than leaving you stuck.
- **Saving:** a small JSON object in localStorage (`gotcha_v1`) holds your furthest page, total deaths, tester-mode flag and sound setting.
- **Dependencies:** none, apart from the optional Google Fonts stylesheet.
- **Size:** the game file is about 940 KB.

---

## 9. Known limits, stated honestly

- **Not yet playtested by humans at scale.** Every page is proven *beatable* by the bot, but "fair", "fun" and "well paced" are not proven. Difficulty is a judgment, and the first real playtest will find pages that are too hard, too easy or too similar.
- **Chapters 13–23 are generated.** They are varied and solver-checked, but they are less handcrafted than chapters 1–12. Expect some pages to feel related, especially the multi-floor ones built around a shaft or portal choice.
- **The bot can find solutions people won't.** Some pages may be technically beatable only with very tight timing. These are the ones to flag in playtests.
- **Vertical "lift" pages are not included.** A page type where you ride a platform upward was tried and cut, because the solver could not prove those pages beatable in reasonable time.
- **A few page names repeat with a numeral** (for example a "II" or "III" suffix) because the lore table has finite names per trap.
- **A deadly-shaft escape.** In some shaft pages, a player who holds right as they fall can slip past the spikes before they finish widening. It is rare and has not been tuned out.
- **No accessibility options yet** (no colour-blind palette, no remappable keys, no assist mode).
- **No licence file is included.** Add the licence of your choice before you distribute it.

---

## 10. Ideas for what comes next

- A playtest pass with real deaths-per-page data, to retune the hardest and the most repetitive pages.
- New trap families (variable gravity rooms, beanstalk and giant-boot reskins, more storybook props).
- A proper lift/climb page type with a solver that can prove it.
- An optional assist mode (slower hazards, extra checkpoints) for accessibility.
- Daily-challenge pages and a shareable death-count card for social posts.
- A "Hall of Deaths" stats screen (deaths per chapter, nemesis trap).

---

*Once Upon a Gotcha. The story is short. The ending is optional. The floor is not.*
