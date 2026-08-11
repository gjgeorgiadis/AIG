# Alexander's Game Zone

A small collection of self-contained, arcade-style HTML games made for Alexander.
Each game is a single `.html` file that runs in any modern browser (and works great
on a phone/tablet in full-screen). No server, build step, or internet connection is
required — just open the file.

---

## Games

| File | Title | What it is |
| --- | --- | --- |
| `index.html` | **Alexander's Game Zone** | The landing page. Shows a photo banner and a grid of game cards that link to each game. To add a game, edit the `GAMES` array near the top of the `<script>`. |
| `alexanders-towers.html` | **Alexander's Towers** | Tap to drop and stack floors; the better your timing, the higher you build. Climbs past real-world buildings (photos from Wikimedia Commons), ordered by real height. |
| `Alexander-Brain.html` | **Alexander's Brain** | Four quick brain / memory mini-games with a countdown and score screen. |
| `tic-tac-toe.html` | **Alexander's Tic-Tac-Toe** | Classic three-in-a-row. Play against a friend (2-player) or against the computer. The computer plays optimally (minimax) 90% of the time and randomly 10% of the time. |
| `sharkdive.html` | **Alexander's Shark Dive** | Dive for the treasure without getting bitten ten times. |
| `firepatrol.html` | **Alexander's Fire Patrol** | Fly the water plane and put out the fires to save the town. |
| `jungle-drop.html` | **Alexander's Jungle Drop** | A plinko-style game on a Connect-4-shaped board. Drop a coin from any column; pegs (obstacles, never placed adjacent) bounce it left or right at random, and it falls into a bucket worth points. Random bucket values each round. Win a big animated reward (super crocodile, unicorn, or laser tiger) at good drops. 2-player or vs computer with Easy / Medium / Hard. Hard plays the exact expected-value-maximizing column. |

### How the pieces fit together
- **Images** are embedded directly in the HTML as base64 data URIs, so each game is fully
  self-contained — except the Towers building photos, which are loaded from Wikimedia URLs.
- **Banner / hero photos:** `index.html` uses `BANNER_IMG`, Towers uses `HEADER_IMG`, and
  Tic-Tac-Toe / Brain embed the photo inline.
- **Styling** uses the Fredoka + Nunito Google Fonts with a bright, kid-friendly palette.

---

## "Charlie" edition

The `Charlie/` folder contains copies of these games adapted for a friend's son, Charlie:
- All "Alexander's X" titles become "Charlie's X".
- The landing-page banner uses `Charlie_banner.jpg`, and each game's photo of Alexander
  is replaced with a photo of Charlie (image files live in the `Charlie/` folder).
- Adds a new game, **Charlie's Connect-4** (`charlie-connect-4.html`) — play a friend or
  the computer (90% optimal move / 10% random), styled to match the other games.

The original files in this main folder are kept unchanged.

---

## Change log

### 2026-08-11
- Linked the two new games, **Shark Dive** (`sharkdive.html`) and **Fire Patrol**
  (`firepatrol.html`), from the landing page with matching card icons.
- Replaced the header photo of Alexander in both new games with fresh face-cropped shots
  from the `Photos/` folder (pool photo for Shark Dive, red-jacket photo for Fire Patrol).
- Removed the short-lived **Blast** game and all references to it.
- Added `.gitignore` (excludes `Backup/`, `Charlie/`, `Photos/`, `.claude/`, macOS junk) in
  preparation for syncing the folder to https://github.com/gjgeorgiadis/AIG.

### 2026-07-17
- Added a new game, **Alexander's Jungle Drop** (`jungle-drop.html`), and linked it from the
  landing page. Plinko-style coin drop on a 7×6 board: random non-adjacent pegs deflect coins
  left/right (50/50), coins land in point buckets (random values each round), fancy animated
  reward creatures (super crocodile / unicorn / laser tiger) with "Good job!" pop-ups.
  2-player and vs-computer (Easy / Medium / Hard; Hard picks the max expected-value column).
- Tweaks: top **and** bottom rows are kept clear of pegs; obstacles reshuffle every round;
  15 coins per player; players are **Alexander** (red) and **Daddy** (yellow), with reward
  pop-ups greeting whoever made the drop.
- Later tweaks: reward animals grant a random **1–20 bonus points** shown on the pop-up.
- Board rules v2: every column now has **at least one** peg and some have two or more (random
  count 10–13 and random spots; pegs never sit horizontally side-by-side so the physics stays
  valid). Obstacles **and** the point buckets reshuffle after each **pair** of turns — both
  players face the same board on their paired turns, then it re-randomizes. Fixed point set
  **25, 18, 15, 12, 9, 6, 3** with their positions shuffled each pair.
- Added a top-left **‹ Menu** pill that returns to `index.html`, matching the other games
  (the in-game 🏠 button, now grouped with 🔊 on the right, still opens the mode picker).

### 2026-06-17
- Created this README to track the games and their changes.
- Created the `Charlie/` edition: copied all four games, rebranded "Alexander" → "Charlie",
  swapped in Charlie's banner and photos.
- Added a new **Charlie's Connect-4** game (friend & smart-computer modes) and linked it
  from the Charlie landing page.
- Re-generated the Charlie **Brain** game from the latest edited main version.
- Renamed the Charlie game files to drop the names — `Towers-game.html`, `Brain-game.html`,
  `Tic-tac-toe.html`, `Connect-4.html` — and rewired `Charlie/index.html` to match.
  (Main folder filenames left unchanged.)
- Charlie **Towers**: removed "Casa Agua" and "Valley Lo Towers"; replaced them with
  "Hodzics Residence" (3 floors), using `Z_house.jpg` from the Charlie folder.
