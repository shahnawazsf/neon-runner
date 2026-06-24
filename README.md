# Neon Runner

A 3D endless runner game (à la Subway Surfers) built entirely in a **single HTML file** with [Three.js](https://threejs.org/). No build step, no dependencies to install — just open it in a browser.

![genre](https://img.shields.io/badge/genre-endless%20runner-22e3ff) ![tech](https://img.shields.io/badge/Three.js-r128-9b5cff) ![single file](https://img.shields.io/badge/build-single%20HTML%20file-ff2bd6)

## Play

Open `index.html` in any modern browser, or serve it locally:

```bash
python -m http.server 8000
# then visit http://localhost:8000/index.html
```

## Controls

| Action | Keys | Mobile |
|--------|------|--------|
| Switch lanes | `←` `→` / `A` `D` | swipe left/right |
| Jump (clear pink barriers) | `↑` / `W` / `Space` | swipe up |
| Slide (clear violet arches) | `↓` / `S` | swipe down |

## Features

- Third-person, behind-the-player 3D perspective with a smooth following camera
- Endless recycling track with a neon synthwave city aesthetic and atmospheric fog
- Three lanes with smooth interpolated lane switching, jumping, and sliding
- Randomly spawned obstacles (jump barriers + slide arches) and collectible rotating coins
- Collision detection: obstacles end the run, coins increase your count
- Live HUD: distance-based score + coin counter
- Particle burst and floating `+10` popup on every coin pickup
- Start / Game Over / Play Again flow with a persistent best score (`localStorage`)
- Progressive speed ramp — the longer you survive, the faster it gets

## Tech notes

Everything lives in `index.html`: markup, CSS, and game logic. Gameplay is tuned through a single `CONFIG` object. Obstacles, coins, and particles use object pooling (recycle instead of allocate) to keep the frame rate steady.

## License

MIT
