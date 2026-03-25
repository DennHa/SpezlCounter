# MTG Pauper SpezlCounter

Live life point tracking for Magic: The Gathering Pauper tournaments. Synced via Firebase Realtime Database. Includes Best of 3/5 series tracking, deck management, card display overlays, and remote admin panel.

## Files

- **controller.html** — 1024×600 touchscreen interface for adjusting life totals, with game tracking and timer
- **admin.html** — Admin panel to manage series state remotely (password protected)
- **overlay.html** — OBS overlay (both players' life totals, names, and wins side-by-side)
- **overlay-p1-name.html**, **overlay-p2-name.html** — Player name overlays
- **overlay-p1-deck.html**, **overlay-p2-deck.html** — Deck name overlays
- **overlay-p1-life.html**, **overlay-p2-life.html** — Large life total displays with state coloring
- **overlay-p1-wins.html**, **overlay-p2-wins.html** — Series win indicators (dot displays)
- **overlay-round.html** — Current round number
- **overlay-timer.html** — Game timer (MM:SS format, clickable to pause)
- **overlay-card.html** — Magic card image display (via Scryfall)

## Features

- **Best of 3 & 5 series tracking** — Selectable format in admin panel with auto-series completion
- **Player & deck management** — Set and edit player names and deck names at game start or via admin panel
- **Card image overlay** — Display Scryfall card images via admin panel (paste Scryfall URL and push)
- **Round tracking** — Auto-incrementing round counter per game
- **In-game timer** — Counts up from 0, clickable to pause/resume
- **Next Game flow** — Buttons to confirm winner and reset life to 20
- **Confirmation modals** — "Next Game" and "End Series" require confirmation to prevent accidents
- **Admin panel** — Remote management of player names, decks, wins, series format, and card images
- **Real-time sync** — All changes sync to Firebase instantly
- **Color-coded life totals** — Visual indicators for warning/danger/critical life states with delta animations

## Quick Start

### On Tournament Touchscreen (Landscape):
https://dennha.github.io/SpezlCounter/controller.html

### On Mobile Device (iPhone, Android):
https://dennha.github.io/SpezlCounter/controller-mobile.html

**Flow:**
1. Enter player names and deck names (or click SKIP for defaults)
2. Select Best of 3 or 5 format in admin panel
3. Use + / − buttons to adjust life totals
4. Click NEXT → select winner → life resets to 20, dot added
5. Repeat until series ends (first to 2 or 3 wins)
6. Click END → confirm → returns to name entry

### Admin Panel (Remote Management):
https://dennha.github.io/SpezlCounter/admin.html

Password required to log in.

Manage:
- Player names and deck names (with REFRESH button to sync from controller)
- Games won for each player
- Series format (BO3 or BO5)
- Card image from Scryfall URL (PUSH button to update overlay)
- Reset entire series

### In OBS as Browser Sources:
- **Combined overlay:** https://dennha.github.io/SpezlCounter/overlay.html
- **Player 1 name:** https://dennha.github.io/SpezlCounter/overlay-p1-name.html
- **Player 2 name:** https://dennha.github.io/SpezlCounter/overlay-p2-name.html
- **Player 1 deck:** https://dennha.github.io/SpezlCounter/overlay-p1-deck.html
- **Player 2 deck:** https://dennha.github.io/SpezlCounter/overlay-p2-deck.html
- **Player 1 life:** https://dennha.github.io/SpezlCounter/overlay-p1-life.html
- **Player 2 life:** https://dennha.github.io/SpezlCounter/overlay-p2-life.html
- **Player 1 wins:** https://dennha.github.io/SpezlCounter/overlay-p1-wins.html
- **Player 2 wins:** https://dennha.github.io/SpezlCounter/overlay-p2-wins.html
- **Round counter:** https://dennha.github.io/SpezlCounter/overlay-round.html
- **Game timer:** https://dennha.github.io/SpezlCounter/overlay-timer.html
- **Card image:** https://dennha.github.io/SpezlCounter/overlay-card.html

---

**Created for the Pauper Spezl tournament series** ⚔
