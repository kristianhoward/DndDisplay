# DndDisplay

A real-time D&D combat display tool. A DM-facing control panel lets you manage characters, HP, initiative, and abilities — changes are instantly broadcast to a player-facing battlefield display.

## Setup

Install the only dependency:

```bash
pip install tornado
```

Add background images to `static/backgrounds/` (any image format). The `static/utility/fog.png` asset is required for the fog weather effect.

## Running

```bash
python main.py
```

The server starts on port 8888.

| URL | Purpose |
|-----|---------|
| `/control` | DM control panel |
| `/display` | Player-facing battlefield view |

Open `/display` on the screen your players can see, and `/control` on your own device. All changes on the control panel are pushed live to the display via WebSocket.

## Features

**Characters**
- Add characters with name, HP, max HP, and an optional portrait image
- Adjust HP with +1 / -1 buttons
- Set initiative (displayed on each character card)
- Remove characters

**Abilities**
- Add named abilities to any character
- Toggle abilities as available or used
- Only available abilities are shown on the display

**Environment**
- Choose a background image for the battlefield
- Set weather effects: Clear, Rain, or Fog

## Notes

- All state is in-memory — it resets when the server restarts
- Duplicate character names are automatically suffixed with a number (e.g. `Goblin`, `Goblin1`)
- Uploaded character portraits are stored in `static/`
