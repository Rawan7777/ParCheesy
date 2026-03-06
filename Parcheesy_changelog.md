# 🎲🧀 ParCheesy — Changelog

> *A browser-based, 4-player Parcheesi game — with a cheesy twist.*

---

## 🔵 v1.0 — Initial Board
`2025-03-08`

Set up the initial project. Created `parchisi.html` with the full board layout — four colored home bases (blue, red, yellow, green), all 68 numbered path cells, the 7-cell colored winning paths, safe spots with star icons, and the center finish triangle. Created `parchisi.css` with all base styles: color variables, home box/oval styles, board cell classes (`.wides`, `.longes`, columns/rows), colored cell classes, and star image sizing. Added a `.gitignore`.

---

## 🔴 v1.1 — Pawns & Dice
`2025-03-09`

Added pawn images (`blue.png`, `red.png`, `yellow.png`, `green.png`), all dice face images (`dice_one.png` through `dice_six.png`, `dice-crown.png`), and the favicon (`icon.png`). Placed all 16 pawn containers in HTML (4 per color). Added 4 dice roller buttons outside the board (one per player). Fixed a bug with the colored winning path IDs (blue/green paths were swapped). Created `parchisi.js`: calculated home coordinates using the oval element positions, positioned all 16 pawns at their home slots, and wired up the dice roll buttons — clicking a roller randomly picks two dice values and updates the dice images.

---

## 🟡 v1.2 — Board Fixes & Movement Start
`2025-03-10`

Renamed `dice-crown.png` to `dice_crown.png` and updated all references. Replaced all dice face images with improved versions. Removed the pink debug background and cleaned up CSS. Fixed the center triangle colors (top = blue, bottom = green). Renamed all pawn elements from "piece" to "pawn". Made red/yellow/green rollers hidden by default. Added CSS transition animations to all pawn containers. Started computing x/y coordinates of all 68 board spots and added initial pawn entry logic when a 5 is rolled — with a basic `after_home()` function for automated follow-up movement.

---

## 🟢 v1.3 — Number UI & Movement Engine
`2025-03-12`

Added a floating "numbers container" UI — a small white box with two clickable buttons (`.numbers-container`, `.number-one`, `.number-two`) letting the player choose which die to apply. Introduced `who_is_home`, `blue_containers`, `who_is_outof_home_indexes`, and `who_isin_spot` tracking objects. Built out full entry logic for blue: 5+5 (enter two pawns), single-5, and sum-to-5 scenarios. Added three helper functions: `movements()` for step-by-step CSS transitions, `parallel_check()` to offset two pawns sharing a spot, and `center_check()` to re-center a lone pawn.

---

## 🔵 v1.4 — Circle Indicators & Big Refactor
`2025-03-15`

Added the `.circle` CSS class — a semi-transparent purple circle that floats dice numbers above pawns on the board. Major JS refactor with consistent semicolons, better comments, and cleaner naming. Added `long_center` coordinates for vertical cells and `roller_deactivater()` to prevent re-rolling mid-turn. Added `number_sail()` to dynamically create and position circles above out-of-home pawns, and `number_sail_destroyer()` to clean them up. Improved `movements()` to handle board wraparound (past cell 68 → back to cell 1). Improved `parallel_check()` to handle vertical spots.

---

## 🔴 v1.5 — Rename & Hover Logic *(AKA: "headache")*
`2025-03-17`

Renamed `clicked1`/`clicked2` to `is_dice_1_clicked`/`is_dice_2_clicked` for clarity. Added handling for the sum-to-5 entry case where both dice are consumed at once. Fixed parallel check to also offset pawns vertically on long cells. Improved `number_sail()` — moved the `setTimeout` inside the per-pawn loop so each pawn gets its own delayed placement. Added mouseover behavior to circles using the `hovered` array and `numbers_float()` to show a popup on hover.

> ⚠️ **Known issue:** hovering multiple pieces then selecting one could cause all previously hovered pieces to move together.

---

## 🟡 v1.6 — Hover Bug Fix *(AKA: "headache fixed")*
`2025-03-17`

Fixed a bug from v1.5 where `numbers_float()` received a container object instead of an array — added `name_index = array[0]` at the top. Added the `hovered` array to properly track which pawn was last hovered when showing the floating dice selector.

---

## 🟢 v1.7 — Half-Circles & Logic Fixes *(AKA: "headache v2")*
`2025-03-20`

Added `.left-half-circle` and `.right-half-circle` CSS classes for showing split dice values on a pawn. Fixed the 5+5 / one-pawn-at-entry turn close-out with proper `is_dice_1_clicked`, `is_dice_2_clicked`, and `roller_deactivater()` calls. Refactored `parallel_check()` to use spot number ranges instead of DOM coordinates. Refactored `center_check()` to take `(who_isin_spot, spot_number)` for cleaner direction detection.

---

## 🔵 v1.8 — Float Removal & Timing Fix *(AKA: "headache v2 fixed")*
`2025-03-20`

Removed `numbers_float()` entirely — replaced all call sites with `number_sail()`. Fixed a timing bug in the board wraparound animation inside `movements()`. Removed leftover UI visibility resets for `number_one`/`number_two` that were no longer needed.

---

## 🔴 v1.9 — Colored Winning Paths *(before id's rename)*
`2025-03-21`

Added `blues`, `reds`, `yellows`, `greens` objects to reference the 7 colored winning-path cells per color and computed their x/y spot coordinates. Added `who_isin_spot` entries for all colored path spots. In `movements()`, added the `is_colored` flag and initial structure for routing pawns into their color-specific winning paths (blue → `d69`–`d75`, red → `d76`–`d82`, etc.) after completing the main loop.

---

## 🟡 v1.10 — Unified d1–d96 ID System *(after id's rename)*
`2025-03-22`

Renamed all colored winning path cell IDs in the HTML from color-based names (e.g. `blue1`–`blue7`) to a sequential `d` series: blue path → `d69`–`d75`, red → `d76`–`d82`, yellow → `d83`–`d89`, green → `d90`–`d96`. Updated all JS references. The entire board is now addressable with a single unified `d1`–`d96` numbering system.

---

## 🟢 v1.11 — Static Float Removal
`2025-03-25`

Removed the old static `numbers-container` HTML element and its CSS (`.number-one`, `.number-two` styles) — fully replaced by the dynamic `number_sail` circles. Cleaned up the HTML accordingly.

---

## 🔵 v1.12 — Variable Rename & Debug Expansion
`2025-03-26`

Renamed `who_is_home_indexes` → `who_is_home_nicknames` and `who_is_outof_home_indexes` → `who_is_outof_home_nicknames` throughout. Major expansion of the debug `dicy()` function to simulate a longer multi-turn sequence covering all four pawns entering the board and moving around. Continued refactoring entry conditions with the new nickname variable names.

---

## 🔴 v1.13 — Debug Cleanup
`2025-03-27`

Simplified the debug `dicy()` function back to a shorter sequence for focused testing. Minor code cleanup.

---

## 🟡 v1.14 — All-Color Home Placement Fix
`2025-03-29`

Fixed a long-standing bug: the yellow and green winning path IDs in the HTML were in reverse order. Added coordinate references for all four colors' home ovals (`blue_oval1_cords` through `yellow_oval4_cords`) and rewrote the home positioning logic to compute each pawn's home location precisely from its oval's bounding box — replacing the old shared `close_cords`/`far_cords` shortcut. This fixed pawn placement for all four colors.

---

## 🟢 v1.15 — Multi-Color Groundwork
`2025-03-30`

Added unique IDs and CSS styles for all 16 home oval elements (`blue_oval_one` through `green_oval_four`) using underscore naming. Rebuilt all 16 pawn containers in HTML with the new underscore convention (`blue_one_container`, `red_two_container`, etc.) and added explicit pawn images. Groundwork commit preparing for full multi-color JS support.

---

## 🔵 v1.16 — Turn System & Finish Triangle
`2025-04-02`

Added a `round` variable to track whose turn it is. Added full winning path routing in `movements()`: a pawn reaching the end of the outer loop is now redirected into the correct color-specific path rather than wrapping the board. Added `finishers_maker()` — places finished pawns into neat arranged positions inside the center finish triangle, with unique coordinates for the 1st through 4th pawn to finish, per color.

---

## 🔴 v1.17 — Turn Cycling & Finish Polish
`2025-04-03`

Added `round_selector()` — cycles turns between all four players (blue → red → green → yellow → blue…) and shows/hides the correct dice roller. Extended winning path routing to properly handle all four colors with their correct first path cell and winning spot numbers. Polished `finishers_maker()` to cover all four colors' finish triangle positions.

---

## 🏆 v1.18 — Full 4-Player Game
`2025-04-04`

> 🎉 **Major milestone** — the game now works for all four players end-to-end.

Expanded from blue-only to all four players. Updated all image assets and renamed the page title to "ParCheesy". Refactored `roll_dice()` to accept color-specific parameters and wired all four rollers with their respective color data. Added per-color home/outof-home tracking arrays. Added `kill()` and `go_back_home()` — when a pawn lands on a lone enemy, the enemy is sent back home. Added capture detection with a bonus 20-move reward. Added triple-doubles punishment: if `double` reaches 3, `go_back_home()` fires on the player's furthest pawn. Added `roller_switcher()` to activate/deactivate the correct roller between turns and on doubles.

---

## 🟢 v1.19 — Real Dice & Safe Spots
`2025-04-05`

Renamed `icon.png` to `ParCheesyIcon.png` and updated the favicon link. Activated real random dice rolling (`Math.floor(Math.random() * 6) + 1`). Fully wired up the kill and capture flow with `go_back_home()` in all scenarios. Updated `movements()` to accept and pass all color-tracking parameters. Added safe spot detection to prevent capturing pawns on starred cells.

---

## 🔵 v1.20 — Triple-Doubles & Dupe Fix
`2025-04-11`

Added the triple-doubles check before any entry/movement logic so it triggers first. Added a `roller_switcher()` call after the doubles check to properly deactivate the roller. Fixed a duplicate-push bug in `who_isin_spot` inside `movements()` using `.includes()` checks. Cleaned up dead code and minor logic fixes around entry spot checks.

---

## 🔴 v1.21 — Blockades & Overshoot Prevention
`2025-04-13`

Re-enabled real random dice rolling. Added blockade detection in `movements()`: a pawn cannot pass through a cell occupied by two enemy pawns of the same color. Added overshoot prevention for the winning paths — a pawn that would overshoot the final cell is blocked from moving. Fixed several edge-case bugs in the kill/safe-spot/blockade interaction. Improved double-reset logic after triple doubles.

---

## 🏆 v1.22 — Full UI Polish & Asset Cleanup
`2025-09-26`

> 🎉 **Major milestone** — the game now has a complete, polished UI.

Reorganized all images into an `img/` folder. Added player avatar images for all four colors. Updated all `src` references to the new paths. Renamed `parchisi.html` → `index.html`. Added a score tracker UI, rules modal button and overlay, and a turn indicator. Major CSS overhaul: full game UI shell with player panels, avatar display, score counters, rules button, dark background theme, and polished layout.

---

## 📖 README.md added — Full Documentation
`2026-03-05`

Added a comprehensive `README.md` fully documenting the project: what ParCheesy is, the name and logo concept, all game features, how to play (setup, turn flow, winning), a full rules table, board layout diagram, entry points per color, file structure, and getting started instructions.

---

## 📜 Parcheesy_changelog.md added — Project Change History
`2026-03-06`

Added a dedicated `Parcheesy_changelog.md` file to track the evolution of the project.  
This file records updates, fixes, structural changes, and development notes over time, providing a clear chronological history of modifications made to ParCheesy. It helps keep documentation organized and allows contributors to quickly understand what has changed between development stages.

---

## 🔤 Project_Files_Renamed — Consistent "ParCheesy" Naming
`2026-03-06`

Renamed the main project files to consistently use the **ParCheesy** project name instead of the previous `parchisi` naming. This aligns the file structure with the project branding and improves clarity across the repository.


This change ensures naming consistency throughout the project and makes the repository structure clearer and easier to navigate.

---

*🎲 Built with pure HTML + CSS + JS. No libraries, no frameworks, no shortcuts.*
