# CHROMACHAIN 🎮

A neon noir color-matching arcade game built in a single self-contained HTML file. No dependencies, no installs — just open and play.

---

## How to Play

A **target color** glows at the top center of the screen. Your job: click only the floating orbs that match it.

| Action | Result |
|---|---|
| Click a **matching** orb | +points, chain progress |
| Complete a **3-hit chain** | New target color + score multiplier rises |
| Click a **wrong color** orb | Lose a life, chain resets |
| Click **empty space** | Nothing happens |
| Let a matching orb **expire** | Chain progress drops by 1 |

You have **3 lives**. Lose them all and it's game over.

---

## Scoring

- Each correct hit awards **10 × your current multiplier × a level bonus**
- Your **multiplier** starts at ×1.0 and increases by +0.5 with every completed chain (max ×5.0)
- Wrong-color clicks reduce the multiplier by −0.5
- High score is saved automatically in your browser

---

## Difficulty Scaling

Every **10 seconds**, the game levels up:

- Orbs spawn **faster**
- Orbs **expire sooner**
- More orbs on screen simultaneously

There is no level cap.

---

## Visual & Audio Features

- **Neon Noir aesthetic** — dark background with a color-shifting parallax grid
- **Particle bursts** on every hit, with intensity scaling to your current chain
- **Screen shake** that grows with combo length
- **Color flash** overlay — cyan for hits, red for mistakes, gold for chain completions
- **Squash & stretch** animations on orb destruction
- **Cursor glow** — turns gold when hovering over a correct orb
- **Synthesized audio** via Web Audio API — no external sound files required

---

## Technical Details

| Property | Value |
|---|---|
| File | Single `.html` file |
| Dependencies | None (Google Fonts loaded via CDN) |
| Renderer | HTML5 Canvas (2D), 60 FPS via `requestAnimationFrame` |
| Audio | Web Audio API — procedurally synthesized |
| Storage | `localStorage` for high score persistence |
| Input | Mouse click + touch support |

---

## Running the Game

Just open `chromachain.html` in any modern browser. No server required.

```bash
open chromachain.html        # macOS
start chromachain.html       # Windows
xdg-open chromachain.html    # Linux
```

---

## File Structure

```
chromachain.html
├── <style>        — All CSS (layout, screens, animations, HUD)
├── Audio engine   — Web Audio API tone synthesizer
├── Canvas setup   — Dual-canvas (background + game layer)
├── Particle system — Burst, spray, and float-text classes
├── Orb class      — Physics, rendering, lifecycle
├── Background     — Parallax scrolling grid with hue shift
├── Game state     — Spawn, difficulty scaling, chain logic
└── Input handler  — Mouse + touch, cursor feedback
```

---

*Built with vanilla HTML, CSS, and JavaScript. No frameworks. No build step.*
