# MTG Pauper SpezlCounter

Live life point tracking for Magic: The Gathering Pauper tournaments. Synced via Firebase Realtime Database. Includes Best of 3 series tracking, confirmation modals, and remote admin panel.

## Files

- **controller.html** — 1024×600 touchscreen interface for adjusting life totals, with game tracking
- **overlay.html** — OBS overlay (both players' life totals side-by-side)
- **overlay-p1.html** — OBS overlay for Player 1 only
- **overlay-p2.html** — OBS overlay for Player 2 only
- **admin.html** — Admin panel to manage series state remotely (password protected)

## Features

- **Best of 3 series tracking** — Dots below each player's life total show games won (max 2)
- **Next Game flow** — Buttons to confirm who won the current game and reset life to 20
- **Confirmation modals** — "Next Game" and "End Game" require confirmation to prevent accidents
- **Admin panel** — Remote management with password protection (default: `spezlpauper`)
- **Real-time sync** — All changes sync to Firebase instantly

## Quick Start

### On Tournament Touchscreen:
https://denpha.github.io/SpezlCounter/controller.html

**Flow:**
1. Enter player names or click SKIP
2. Use + / − buttons to adjust life totals
3. Click NEXT GAME → select winner → life resets to 20, dot added
4. Repeat until series ends (first to 2)
5. Click END GAME → confirm → returns to name entry

### Admin Panel (Remote Management):
https://denpha.github.io/SpezlCounter/admin.html

Password: `spezlpauper`

Manage:
- Games won for each player
- Reset entire series
- View live game state

### In OBS as Browser Source:
- **Overlay (both):** https://denpha.github.io/SpezlCounter/overlay.html
- **Player 1 only:** https://denpha.github.io/SpezlCounter/overlay-p1.html
- **Player 2 only:** https://denpha.github.io/SpezlCounter/overlay-p2.html

---

**Created for the Pauper Spezl tournament series** ⚔
