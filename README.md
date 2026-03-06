# RA Tracker

A personal dashboard for [RetroAchievements](https://retroachievements.org) 

**Live demo:** `https://bleongambetta.github.io/ra-tracker`

---

## Why I Built This

RetroAchievements is great, but its default views make it hard to:

- Browse your full game library in one place with flexible filtering
- Track multiple simultaneous events and challenges
- Know at a glance which specific achievements in a game qualify toward an event goal
- Manage a priority queue of what to play next

This tool solves all of that with a clean, mobile-friendly interface that talks directly to the RA public API.

---

## Features

###  Library View
- Pulls all your completed and recently played games
- Filter by console, progress status (not started / in progress / completed), or search by title
- Sort by recently played, title, completion %, or console
- Live progress bars per game

### Events Tracker
Two event types supported:

**Hub / List events** — for goals like *"earn 100 XP in the Dinosaurs hub."* Add games from your library and track overall completion % per game.

**Achievement Page events** — for structured events like Achievement of the Week. Add games, then use the achievement picker to select exactly which achievements count toward the event. The tracker shows earned vs. qualifying in real time.

Each event supports:
- Color coding
- Goal description and reference URL
- Priority-ordered play queue with drag-up/drag-down reordering
- Per-game progress tracking

### Backup & Restore
Export your event configuration as a JSON file. Import it back at any time. Useful since event data lives in browser local storage.

---

## Setup

### Prerequisites
- A [RetroAchievements](https://retroachievements.org) account
- Your RA API key (found at **retroachievements.org → Settings → API Key**)

### Running Locally
Because the tool makes fetch requests to the RA API, it needs to be served over HTTP rather than opened as a `file://` URL. The easiest way:

```bash
# Python 3
cd path/to/ra-tracker
python3 -m http.server 8080
```

Then open `http://localhost:8080/ra-tracker.html` in your browser.

### Hosted Version (GitHub Pages)
The live version at `https://yourusername.github.io/ra-tracker` works on desktop and mobile with no setup needed — just enter your credentials on the login screen.

---

## Usage Notes

**API key storage:** Your API key is stored in your browser's local storage only. It is never included in the source code or sent anywhere except directly to `retroachievements.org`.

**API rate limits:** RetroAchievements asks users to stay under 4 calls per second. This tool only fetches on explicit user actions (not polling), so normal usage is well within limits.

**Data persistence:** Library data is fetched live from RA. Event configuration (your events, game queues, achievement selections) is saved to local storage and is browser/device-specific. Use the Export feature regularly to back up your event data.

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript — no dependencies, no build tools
- [RetroAchievements API](https://api.docs.retroachievements.org/)
- Google Fonts (Press Start 2P, IBM Plex Mono, Nunito)
- Hosted via GitHub Pages

---

## Project Status

Personal tool, actively used. Not accepting contributions, but feel free to fork it for your own use.

---

*Part of my personal projects collection — see my [main profile](https://github.com/bleongambetta) for professional work.*
