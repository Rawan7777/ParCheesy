<div align="center">

```
██████╗  █████╗ ██████╗  ██████╗██╗  ██╗███████╗███████╗███████╗██╗   ██╗
██╔══██╗██╔══██╗██╔══██╗██╔════╝██║  ██║██╔════╝██╔════╝██╔════╝╚██╗ ██╔╝
██████╔╝███████║██████╔╝██║     ███████║█████╗  █████╗  ███████╗ ╚████╔╝ 
██╔═══╝ ██╔══██║██╔══██╗██║     ██╔══██║██╔══╝  ██╔══╝  ╚════██║  ╚██╔╝  
██║     ██║  ██║██║  ██║╚██████╗██║  ██║███████╗███████╗███████║   ██║   
╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚══════╝╚══════╝   ╚═╝   
```

### *A browser-based, 4-player Parcheesi game — with a cheesy twist.*

<br>

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
![Players](https://img.shields.io/badge/players-4-blueviolet?style=flat-square)
![Type](https://img.shields.io/badge/project-personal-orange?style=flat-square)
![Status](https://img.shields.io/badge/status-beta-yellow?style=flat-square)
![Author](https://img.shields.io/badge/author-brouane-purple?style=flat-square)

<br>

> *"Strategy is the craft of the warrior. But dice? That's the craft of the universe."*

</div>

---

## 🧀 What is ParCheesy?

**ParCheesy** is a fully playable, browser-based digital board game built from scratch using pure HTML, CSS, and vanilla JavaScript — no libraries, no frameworks, no shortcuts.

It simulates the classic **Parcheesi** board game: four players, four pawns each, two dice, a shared board, and a race to the center. You roll, you move, you capture, you strategize — and you laugh, because this game has *personality*.

### The Name & Identity

The name **ParCheesy** is a playful fusion of *"Parcheesi"* — the classic board game — and *"cheesy"*, reflecting the fun, lighthearted spirit that drives this project. The logo, a **six-sided die made of melting cheese**, captures both the strategy and randomness of dice games while injecting humor and uniqueness through the cheese motif. The melting texture gives it a dynamic, cartoon-like personality that reinforces one central idea: ParCheesy is not just a game — it's a *deliciously fun experience* with a strong identity that's hard to forget.

---

## ✨ Features

- **4-player local multiplayer** — Blue, Red, Green, and Yellow, all on one screen
- **Two dice system** — roll both at once, choose which pawn uses which die
- **Entry rule** — roll a 5 (or sum of 5) to release a pawn from home
- **Capture system** — land on an enemy to send them back to their home
- **Safe spots (⭐)** — 12 starred cells protect pawns from being captured
- **Blockade detection** — can't move through a spot occupied by 2 enemy pawns
- **Bonus move on capture** — kill an enemy and earn a bonus 20-step move
- **Triple doubles punishment** — roll the same number 3 times in a row and your furthest pawn goes back home
- **Colored winning paths** — each player has their own private path to the center
- **Finish triangle placement** — pawns are neatly arranged inside the center as they finish
- **Turn indicator** — only the active player's dice are clickable; others are grayed out
- **Visual number bubbles** — floating circles appear above each movable pawn showing available dice values
- **Rules modal** — a built-in rules overlay accessible at any time
- **Score tracker** — shows each player's finish count (0–4)
- **No dependencies** — pure HTML + CSS + JS. Open the file and play.

---

## 🎮 How to Play

### Setup

```
1. Open index.html in any modern browser
2. Four players sit around the same screen
3. Blue always goes first
```

### Turn Flow

```
Your Turn
   │
   ▼
Click your dice roller
   │
   ▼
Two dice are revealed
   │
   ├── Sum or value is 5?  ──►  A pawn exits home and enters the board at your start spot
   │                             └── Also uses the remaining die value if one die ≠ 5
   │
   ├── Neither is 5?  ──►  Choose a pawn that's already on the board
   │                        └── Click the bubble showing the dice value you want to use
   │                        └── Then click another bubble (or same pawn) for the second die
   │
   └── Both dice same (double)?  ──►  Roll again after using both!
                                       └── 3 doubles in a row → your furthest pawn goes home!
```

### Winning

```
Navigate all 4 of your pawns around the board  →  into your colored path  →  to the center triangle.
First player to place all 4 pawns in the center WINS.
```

---

## 📋 Game Rules

| Rule | Description |
|------|-------------|
| 🏠 Starting | Each player starts with 4 pawns at home |
| 🎲 Entry | Roll a **5** (single die, or both dice summing to 5, or 5+5) to enter the board |
| ↪️ Movement | Pawns move **clockwise** around the 68-cell outer ring |
| ⚔️ Capture | Land on a lone enemy pawn → it goes back home. You earn a **+20 bonus move** |
| ⭐ Safe Spots | 12 starred cells — no captures allowed. Enemy can't land on a spot guarded by 2 of yours |
| 🚧 Blockade | Two pawns of the same color on one spot = a blockade. Enemy pawns **cannot pass through** |
| 🎯 Winning Path | After completing the outer loop, each color enters its own private 7-cell colored path |
| 🏆 Finish | A pawn landing **exactly** on the last cell of the colored path enters the center triangle |
| 🔁 Doubles | Rolling doubles = roll again. Three doubles in a row = furthest pawn sent home |
| ⏭️ Skip | If no legal move exists (all blocked/overshoot), the turn passes automatically |

---

## 🗺️ Board Layout

```
_____________________________________________________
|                 |   .   |   .   |                 |
|                 |   .   |   .   |                 |
|    [ BLUE ]     |   .   |   .   |     [ RED ]     |
|      BASE       |   .   |   .   |      BASE       |
|                 |   .   |   .   |                 |
|                 |   .   |   .   |                 |
|_________________|_______________|_________________|
|   .   .   .   . |               |   .   .   .   . |
|   .   .   .   . |               |   .   .   .   . |
|_________________|     FINISH    |_________________|
|   .   .   .   . |               |   .   .   .   . |
|   .   .   .   . |               |   .   .   .   . |
|_________________|_______________|_________________|
|                 |   .   |   .   |                 |
|                 |   .   |   .   |                 |
|   [ YELLOW ]    |   .   |   .   |    [ GREEN ]    |
|      BASE       |   .   |   .   |      BASE       |
|                 |   .   |   .   |                 |
|                 |   .   |   .   |                 |
|_________________|_______________|_________________|

```

### Entry Points by Color

| Color | Enter Spot | Winning Path | Finish at |
|-------|-----------|--------------|-----------|
| 🔵 Blue | `d52` | `d69` → `d75` | `d76` |
| 🔴 Red | `d35` | `d76` → `d82` | `d83` |
| 🟢 Green | `d18` | `d83` → `d89` | `d90` |
| 🟡 Yellow | `d1` | `d90` → `d96` | `d97` |

---

## 🚀 Getting Started

### Requirements

- Any modern browser (Chrome, Firefox, Edge, Safari)
- No installation. No server. No npm. Just a file.

### File Structure

```
parcheesy/
│
├── index.html                  # Game structure & board layout
├── parchisi.css                # All styles, layout, colors, animations
├── parchisi.js                 # Complete game logic (~1200 lines)
│
└── img/
    ├── ParCheesyIcon.png       # Melting cheese die logo
    ├── rules.png               # Rules button icon
    ├── star.png                # Safe spot star icon
    ├── dice_crown.png          # Default dice face (crown)
    ├── dice_one.png            # Dice face: 1
    ├── dice_two.png            # Dice face: 2
    ├── dice_three.png          # Dice face: 3
    ├── dice_four.png           # Dice face: 4
    ├── dice_five.png           # Dice face: 5
    ├── dice_six.png            # Dice face: 6
    ├── blue.png                # Blue pawn image
    ├── red.png                 # Red pawn image
    ├── green.png               # Green pawn image
    ├── yellow.png              # Yellow pawn image
    ├── blue_avatar.png         # Blue player avatar
    ├── red_avatar.png          # Red player avatar
    ├── green_avatar.png        # Green player avatar
    └── yellow_avatar.png       # Yellow player avatar
```

### Run

```bash
# Option 1: Just open it
open index.html

# Option 2: Serve locally (avoids any CORS edge cases)
python3 -m http.server 8080
# then visit http://localhost:8080
```

---

## 🧠 Architecture & Code Breakdown

The entire game lives in **three files**. Here's how everything connects:

---

### `index.html` — The Board

The HTML file defines the entire visual structure of the board. The 68 main track cells, 28 colored path cells, 4 home zones with their oval slots, 16 pawn containers, 4 dice rollers with their dual dice, 4 player labels and score displays, and the rules modal are all declared here.

Each board cell is a `<div>` with a unique ID (`d1` through `d96`) and CSS classes that control its position, size, and color. The board uses a combination of **CSS Grid** and **absolute positioning** to create the cross-shaped Parcheesi layout.

```
Cells d1–d68    →  outer ring (main track, clockwise)
Cells d69–d75   →  blue's colored winning path
Cells d76–d82   →  red's colored winning path
Cells d83–d89   →  green's colored winning path
Cells d90–d96   →  yellow's colored winning path
```

---

### `parchisi.css` — The Visuals

The CSS handles everything visual: the cross-shaped board layout, home zone quadrants, cell sizing, pawn containers, dice roller styling, avatar placement, the rules modal, and all color theming.

The board cells come in three types: **squares** (center & corners), **wides** (horizontal cells), and **longes** (vertical cells). These are sized differently to fill the board geometry correctly.

Safe spots use a ⭐ star image overlay rather than a color change, keeping the visual language clean. Each colored path section (blues, reds, greens, yellows) is given a distinct background to clearly signal the private runway to victory.

---

### `parchisi.js` — The Brain

This is the core. ~1200 lines of pure vanilla JavaScript that drives everything. No libraries. Here's how it's organized:

```
parchisi.js
│
├── 📐  Coordinate System Setup
│     ├── getBoundingClientRect() for all 96 cells
│     ├── spots{}         →  where pawns sit on each cell (x, y)
│     ├── wide_center{}   →  center x of wide cells (for alignment checks)
│     ├── long_center{}   →  center y of long cells (for alignment checks)
│     └── who_isin_spot{} →  array per cell tracking which pawns are present
│
├── 🏠  Pawn State Management (×4 colors)
│     ├── *_who_is_home{}           →  object: pawns still in home zone
│     ├── *_containers{}            →  immutable reference to all pawn elements
│     ├── *_who_is_outof_home[]     →  array: pawn elements on the board
│     ├── *_who_is_home_nicknames[] →  array: pawn name strings at home
│     └── *_who_is_outof_home_nicknames[] → array: pawn name strings on board
│
├── 🔄  Turn System
│     ├── round (1–4)              →  tracks whose turn it is
│     ├── is_*_finished (boolean)  →  marks a color done when all 4 pawns finish
│     └── round_selector()        →  cycles turns, skips finished players
│
├── 🎲  roll_dice()               →  the main entry point for every turn
│     ├── Generates 2 random dice (1–6)
│     ├── Displays matching dice face images
│     ├── Handles 5+5 → double-entry of two pawns
│     ├── Handles single 5 / sum-of-5 → entry of one pawn
│     ├── Handles doubles → bonus roll, triple-doubles → go_back_home()
│     └── Calls number_sail() to display movement options
│
├── ♟️  movements()              →  moves a pawn step-by-step with animation
│     ├── Uses setTimeout chains (250ms per step) for smooth movement
│     ├── Handles overflow past cell 68 → wraps back to cell 1
│     ├── Detects entry into the colored winning path
│     ├── Detects landing on the finish cell → calls finishers_maker()
│     ├── Calls kill() if landing on a lone enemy
│     └── Calls number_sail() for the remaining dice after a move
│
├── 🏁  finishers_maker()        →  places finished pawns inside the center triangle
│     └── Calculates 4 distinct pixel positions per color quadrant of the triangle
│
├── 🎯  number_sail()            →  the UX brain — shows clickable dice bubbles
│     ├── Creates floating circle/half-circle divs above each movable pawn
│     ├── Checks blockades (2 enemies ahead) for each pawn × each die
│     ├── Checks safe spots (enemy can't be captured there)
│     ├── Checks overshoot (can't move past finish cell)
│     ├── Shows left/right half-circles when both dice are available
│     ├── Shows a single full circle when only one die is valid
│     └── Auto-skips the round if no pawn can legally move
│
├── 🔃  parallel_check()         →  separates two pawns on the same cell (±15px offset)
├── 🎯  center_check()           →  re-centers a pawn if it's misaligned on its cell
├── 🗑️  number_sail_destroyer()  →  removes all floating dice bubble elements from the DOM
│
├── ⚔️  kill()                   →  sends a captured enemy pawn back to its home oval
│     └── Updates who_isin_spot, who_is_home, and who_is_outof_home for the victim's color
│
├── 🔙  go_back_home()           →  triple-doubles penalty: finds the furthest pawn and returns it
│     └── Calculates relative distance from entry point to find the true "furthest" pawn
│
└── 🎰  roller_switcher()        →  locks/unlocks dice rollers to enforce turn order
```

---

## 🔢 The Coordinate System — How Pawns Know Where to Go

Every cell on the board (d1–d96) has its bounding rectangle read at load time using `getBoundingClientRect()`. From this, the game calculates the exact pixel position a pawn container should be placed to appear **centered inside that cell**, relative to the `Main-Container`.

```javascript
spots[`d${i}_spot_x`] = cords.x - Main_Container.x + ((cords.width  - pawn_width)  / 2);
spots[`d${i}_spot_y`] = cords.y - Main_Container.y + ((cords.height - pawn_height) / 2);
```

This means **all pawn movement is coordinate-based** — no layout engine, no re-rendering. A pawn moves by updating its `style.left` and `style.top` CSS properties, and the `setTimeout` chain creates the step-by-step animation.

---

## 🎲 The 5-Rule Explained

Entering the board requires a **5**. The game handles three cases:

```
Case 1: dice_1 == 5 AND dice_2 == 5  →  enter 2 pawns, use both dice
Case 2: dice_1 == 5 OR dice_2 == 5   →  enter 1 pawn, remaining die moves it further
Case 3: dice_1 + dice_2 == 5         →  enter 1 pawn, both dice are consumed
```

When you enter the board and there's an enemy pawn on your entry spot, the kill function is triggered before your pawn lands — and you get a **+20 bonus move** as a reward.

---

## 🚧 Blockade Logic

A **blockade** is formed when 2 pawns of the same color occupy a single cell. No enemy pawn can pass through or land on a blockade. The game detects this in `number_sail()` by scanning every cell between a pawn's current spot and its destination:

```
for each step j from 1 to dice_value:
    if who_isin_spot[spot + j].length == 2:
        is_blockade = true → don't show dice bubble for this pawn
```

Safe spots (⭐) are also blocked to enemies even with a single defender — landing there is simply not permitted if it contains an enemy pawn.

---

## 🔄 The Winning Path Transition

Each color has its own private 7-cell runway leading to the center. The transition from the outer ring into this path happens at a specific "gate" cell:

```
Blue:   passes cell 47 → enters d69 (instead of continuing to d48)
Red:    passes cell 30 → enters d76
Green:  passes cell 13 → enters d83
Yellow: passes cell 64 → enters d90
```

The `movements()` function detects when a pawn is in the "danger zone" (the last few outer-ring cells before the gate) and redirects its movement into the colored path instead of continuing around the board.

---

## 🔁 The Triple Doubles Rule

Rolling doubles (same number on both dice) grants the same player another roll. But rolling doubles **three times in a row** triggers a penalty: the `go_back_home()` function is called.

`go_back_home()` finds the **furthest pawn from home** by calculating each pawn's relative distance from the entry spot, then teleports that pawn back to its home oval — resetting its progress entirely.

```
double == 1 → normal doubles, roll again
double == 2 → second doubles, roll again (careful...)
double == 3 → go_back_home() → furthest pawn sent home → double reset to 0
```

---

## 🎯 Number Sail — The UX System

After each dice roll, the game computes which pawns are legally movable and what dice values they can use. For each eligible pawn, a floating **clickable div** appears above it:

```
Both dice available   →  Left half-circle (dice_1) + Right half-circle (dice_2)
One die available     →  Single full circle showing that die's value
No legal move         →  Pawn added to incompetents[], no bubble shown
```

When all pawns are incompetent (blocked, overshooting finish, or stuck at home), the round auto-skips. This means no player ever gets stuck — the game always moves forward.

---

## 🏆 Finishing the Race

A pawn enters the center only by **landing exactly on the winning cell** (spot 76, 83, 90, or 97). You cannot overshoot it — the game blocks dice selections that would cause overshooting.

When the 4th pawn of a color finishes, the `is_*_finished` flag is set to `true`, and `round_selector()` automatically skips that color's turn in future rounds. The score counter (0–4) for that player updates with each pawn that finishes.

The `finishers_maker()` function places each finishing pawn at a precise pre-calculated pixel position inside the center triangle, stacking them neatly as more finish:

```
1st finisher → top-left of triangle quadrant
2nd finisher → below the 1st
3rd finisher → to the right of the 1st
4th finisher → further right/down
```

---

## 🎨 Design & Colors

| Element | Color |
|---------|-------|
| Board background | Warm cream / dark beige |
| Blue player | `#3030f0` / `rgba(64, 17, 151, ...)` |
| Red player | `#e74935` / `rgba(174, 3, 3, ...)` |
| Green player | `#21a84a` / `rgba(33, 168, 74, ...)` |
| Yellow player | `#dac200` / `rgba(218, 203, 0, ...)` |
| Safe spot badge | ⭐ star image |
| Dice bubble (blue) | semi-transparent indigo/violet |
| Dice bubble (red) | semi-transparent crimson |
| Dice bubble (green) | semi-transparent emerald |
| Dice bubble (yellow) | semi-transparent gold |

---

## 💡 What I Built & What I Learned

ParCheesy is my most complex personal project to date. Here's what building it from scratch taught me:

**DOM Mastery** — Working with `getBoundingClientRect()`, dynamic element creation, `style.left/top` positioning, and event delegation at scale taught me exactly how the DOM renders and lays out content.

**Coordinate-Based Game State** — Instead of using a game framework, I built a full coordinate tracking system using plain JS objects. Every cell, every pawn, every move is tracked through `who_isin_spot{}`, `*_who_is_outof_home[]`, and `*_who_is_home_nicknames[]`.

**Async Movement with setTimeout** — Animating step-by-step pawn movement required chaining `setTimeout` calls at 250ms intervals. Managing timing across multiple concurrent moves (kill + entry + movement) was one of the hardest problems to get right.

**Event-Driven UI** — The floating number bubbles are dynamically created, attached with click listeners, and destroyed after use. This "create → use → destroy" pattern for interactive elements was new territory for me.

**Edge Case Hell** — This game has hundreds of edge cases: what if two pawns need to enter the same cell? What if a pawn is on the gate cell of the colored path? What if both dice overshoot the finish? What if a kill happens on entry? Each one required a deliberate solution.

**No Framework Needed** — The entire game is ~1200 lines of vanilla JavaScript. Building this proved that you don't need React, Vue, or any library to build something genuinely interactive and complex.

---

## 🔮 Known Limitations & Future Plans

### Current Limitations (Beta)

- Local multiplayer only — no online/networked play
- Fixed at exactly 4 players — no 2 or 3 player modes
- No sound effects
- No animations for captures (pawn teleports instantly home)
- No win screen / celebration overlay
- Board is not responsive — designed for desktop browsers

### Planned Improvements

- [ ] **Win screen** — full celebration overlay when a player wins
- [ ] **Capture animation** — animate the pawn flying back home on capture
- [ ] **Sound effects** — dice roll, pawn move, capture, win sounds
- [ ] **2 and 3 player modes** — make player count configurable
- [ ] **Responsive layout** — adapt the board for tablets and larger phones
- [ ] **Online multiplayer** — WebSocket-based networked play
- [ ] **AI player** — a single-player mode with a computer opponent
- [ ] **Undo button** — let a player undo their last move
- [ ] **Game log** — a sidebar showing the history of moves

---

## 📝 Personal Note

ParCheesy started as a question: *"Can I build a real board game from scratch, in the browser, with just JavaScript?"*

The answer turned out to be yes — but it wasn't easy. The coordinate system, the turn logic, the blockade detection, the killing mechanic, the colored path transitions, the triple-doubles rule — every single feature was a problem that needed to be understood and solved from first principles.

There are no libraries here. No canvas. No game engine. Just DOM manipulation, object tracking, and setTimeout chains. Every pawn knows where it is because the code tracks it. Every bubble knows what to offer because the code checks every scenario.

It's not perfect. It's a beta. But it works — and I built it.

---

<div align="center">

*Built with vanilla JavaScript, spatial reasoning, and an unreasonable amount of patience.*

**Now go roll some cheese. 🧀🎲**

</div>
