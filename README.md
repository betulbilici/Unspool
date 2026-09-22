# 🧶 Pati & The Magic Yarn (`Unspool`)

A charming, retro-styled 2D physics puzzle-platformer built entirely in a self-contained single-file web application using **HTML5 Canvas**, **Matter.js** (2D physics engine), and the **Web Audio API** for 100% procedural 16-bit retro sound effects.

No external asset files (images, audio files, or fonts) are required; every visual asset and audio effect is generated procedurally in real-time.

---

## 🎮 Play Online / How to Run

1. Simply open [`index.html`](./index.html) in any modern web browser (Chrome, Edge, Firefox, Safari).
2. Or serve it locally using any static web server:
   ```bash
   # Python 3
   python -m http.server 8080
   ```
   Then navigate to `http://localhost:8080`.

---

## 🐱 Protagonist: Pati

Meet **Pati**, a chubby, white British Shorthair kitten featuring:
- Procedurally rendered round cheeks, delicate inner pink ears, glowing amber/golden iris eyes with animated blinking.
- A fluffy physics-driven animated tail that sways with sine waves and responds dynamically to running and jumping.
- Animated trot cycle with little pink-padded paws.
- Platformer physics with **coyote time** (130ms), **jump input buffering** (120ms), and variable jump height.

---

## 🧵 Core Mechanic: Dynamic Unspooling Yarn Ball

- **Dynamic Matter.js Rigid Circle Body**: Rolls with realistic momentum, friction, and bounce.
- **Unspooling & Shrinking**: Starts at a full radius of **30px**. As it rolls across floors and platforms, it unspools and shrinks proportionally down to a minimum of **12px**.
- **Mass Dynamics ($m \propto r^2$)**:
  - **Large Ball (Heavy)**: Activates weight-sensitive pressure plates and mechanical switches.
  - **Small Ball (Nimble)**: Rolls faster, bounces higher, and squeezes through narrow bookshelf gaps and tight crawlspaces.
- **Thread Trail**: Leaves a trail of wool thread along touched ground surfaces, dynamically linking back to the rolling ball.
- **Checkpoints (Yarn Spools)**: Floating magical spools that rewind the yarn ball back to its full 30px size with sparkling particle effects.

---

## 🛋️ Level Guide & Stages

### 🌸 Stage 1: Living Room Floor (Warmup & Weight Puzzle)
- **Objective**: Learn rolling physics and weight thresholds.
- **Puzzle**: Roll the heavy yarn ball into the floor depression onto the weight switch. When weighed down, it tilts a hinged wooden ramp upward, allowing Pati to scale the velvet sofa and snuggle into the wicker cat basket.

### 📚 Stage 2: Bookshelf Ascent (Tunnel & Springboard Mechanics)
- **Objective**: Use yarn unspooling to navigate tight crawlspaces.
- **Puzzle**: Roll the yarn ball to shrink it below 18px so it fits into the low-ceiling bookshelf tunnel. Launch the ball onto an upper bookshelf ledge via a springboard, leap up using intermediate books and checkpoints, and reach the high shelf cat bed.

### 🌙 Stage 3: Nightstand Climax (Moving Platforms & Weight Preservation)
- **Objective**: Platforming timing and yarn weight preservation.
- **Puzzle**: Guide Pati and the yarn ball across oscillating hardcover book platforms above the floor drop. Manage the ball's distance or recharge it at the mid-air spool to keep enough weight to unlock the heavy golden barrier guarding the nightstand top basket.

---

## ⌨️ Controls

| Action | Keyboard | Touch / On-Screen |
| :--- | :--- | :--- |
| **Move Left / Right** | `A` / `D` or `◀` / `▶` | Left / Right Buttons (`◀` / `▶`) |
| **Jump** | `W` / `▲` / `Space` | Jump Button (`▲`) |
| **Cute Meow** | `E` | Meow Button (`🐱`) |
| **Restart Room** | `R` | Reset Button (`🔄`) |
| **Toggle Audio** | `M` | Sound Button (`🔊` / `🔇`) |

---

## 🛠️ Technical Stack & Architecture

- **Rendering**: HTML5 2D Canvas with sub-pixel crisp vector/pixel aesthetics and warm living room palettes.
- **Physics**: Matter.js (v0.19.0) with rigid-body collisions, custom raycast ground sensors, and dynamic mass scaling.
- **Audio Synthesizer**: Web Audio API module generating:
  - Jump frequency sweep (triangle wave glide)
  - Kitten meow with dual formant filters, pitch inflection, and vibrato
  - Rolling hum with velocity-modulated lowpass filtered noise
  - Mechanical switch click & heavy bass clunk
  - Springboard pitch-dive "boing"
  - Spool pickup crystal arpeggio
  - Victory fanfare
- **Zero Build Tools**: Single self-contained HTML file without npm, webpack, or external build steps.