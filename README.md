# MTG Pauper Overlay — Setup Guide

Two-file web app for Magic: The Gathering Pauper tournament scoring, synced via Firebase Realtime Database.

## Files

- **`overlay.html`** — OBS Browser Source overlay (transparent, shows life totals and player names)
- **`controller.html`** — Touch controller (1024×600 landscape, adjusts life points)

## Quick Setup

### 1. Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Click "Create a project"
3. Name it (e.g., `pauper-overlay`)
4. Disable Analytics (optional)
5. Create

### 2. Set Up Realtime Database

1. In Firebase Console, go to **Realtime Database**
2. Click **Create Database**
3. Choose region (closest to you)
4. Start in **Test Mode** (for dev) — data is fully readable/writable
5. Click **Enable**

### 3. Initialize Data Structure

In the **Realtime Database** editor, paste:

```json
{
  "match": {
    "p1": {
      "name": "Spieler 1",
      "life": 20
    },
    "p2": {
      "name": "Spieler 2",
      "life": 20
    }
  }
}
```

### 4. Get Your Database URL

In Realtime Database, look for the URL at the top (e.g., `https://spezlcounter-default-rtdb.europe-west1.firebasedatabase.app`).

### 5. Update Both HTML Files (Already Done!)

Both `overlay.html` and `controller.html` are already configured with your Firebase database URL:

```js
const DB_URL = 'https://spezlcounter-default-rtdb.europe-west1.firebasedatabase.app/match.json';
```

### 6. Open in Browser

- **overlay.html** → Open in OBS as a Browser Source (set size ~1920px wide × 160px tall, position at bottom)
- **controller.html** → Open on a 7" touchscreen (1024×600 landscape) or any device for testing

## Firebase Security Rules (Production)

When deploying, update your Realtime Database rules for safety:

```json
{
  "rules": {
    "match": {
      ".read": true,
      ".write": true
    }
  }
}
```

For stricter control, use authentication (Firebase SDK required — beyond this MVP).

## Features

### Overlay
- ✅ Live polling (500ms) from Firebase
- ✅ Player names + life totals
- ✅ Color-coded life states (normal/warning/danger/critical)
- ✅ Pulse animation for low HP (5–1 LP)
- ✅ Delta animation (floating +/−X numbers)
- ✅ Connection indicator (green/red dot)
- ✅ Transparent background (ready for OBS)

### Controller
- ✅ Name entry modal at start
- ✅ Two elegant player zones (pink vs white)
- ✅ Large dominant life totals (160px)
- ✅ Simple up/down buttons (+1/-1)
- ✅ Accumulated delta display (resets after 5s of no clicks)
- ✅ Reset button to return both players to 20 LP
- ✅ All touches ≥80px for comfortable interaction
- ✅ Minimal, elegant design inspired by card UI

## Pauper Spezl Brand Styling

**Overlay:**
- Colors: Navy (`#11233D`), warm off-white (`#FAF1D9`), MTG mana accents
- Typography: Lora serif (Google Fonts)
- Aesthetic: Flat, MTG card-inspired, no gradients
- Life state colors: normal (white) → warning (yellow) → danger (red + pulse) → critical (dark red)

**Controller:**
- Minimal, elegant design inspired by MTG card interfaces
- Player 1 zone: Pink gradient (`#FF6B9D`)
- Player 2 zone: Warm white (`#FAF1D9`)
- Large life totals (160px), mana symbols (spades/hearts)
- Accumulated delta display: shows cumulative clicks, resets after 5 seconds of inactivity
- Up/down buttons at bottom with semi-transparent overlay

## Deployment

### GitHub Pages

1. Create a GitHub repo `spezl-counter` (or similar)
2. Add both HTML files to the root
3. Enable GitHub Pages in repo Settings → Pages
4. Files available at `https://YOUR-USERNAME.github.io/spezl-counter/overlay.html` etc.

### Self-Hosted

- Upload both HTML files to any web server
- Enable CORS headers (Firebase REST API supports CORS natively)

## Notes

- **No backend** — all logic is client-side
- **No build step** — plain HTML/CSS/JS
- **Firebase REST API** — no JS SDK required, keeps files small
- **Test Mode only** — for tournament use, set proper security rules or use authentication

---

**Created for the Pauper Spezl tournament series** ⚔
