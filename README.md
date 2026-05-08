# 🚗 JellyCar // Neon Drive

A browser-based remake of the classic JellyCar, built as a single self-contained `index.html` file with no build tools or dependencies to install.

## How It's Made

The game is written entirely in **vanilla JavaScript** and rendered on an **HTML5 Canvas**. Physics are powered by [**Matter.js**](https://brm.io/matter-js/) (loaded from CDN), which handles rigid-body collisions, constraints, and the world simulation.

The jelly car itself is the core technical trick: the chassis is a **grid of particle bodies** linked together with spring constraints at tuned stiffness and damping values. This gives the car its signature squishy, deformable feel. The wheels are separate circular bodies attached to the nearest chassis particles via flexible axle constraints. The **GROW mechanic** works by lerping a scale multiplier each frame and applying it to every body and constraint rest-length simultaneously, so the car physically inflates rather than just appearing larger.

Rendering is done by tracing a smooth quadratic-curve path through the outline particles each frame, producing the blob-like silhouette. Three hand-crafted levels ship with the game, each with its own visual theme (Synthwave, Petscop, Guardian) and unique obstacles including jump ramps, stacked crates, spinning gears, and moving platforms.

## ▶️ Running in Your Browser

No installation or server required — just open the file:

````bash
# Clone the repo
git clone https://github.com/shaskel2/JellyCar_remake.git

# Open the game — that's it!
open index.html
````

Or simply **drag `index.html` into any modern browser window**.

## 🎮 Controls

| Key | Action |
|---|---|
| `W` / `↑` | Accelerate |
| `S` / `↓` | Reverse |
| `A` `D` / `← →` | Tilt |
| `Space` | Toggle GROW |
| `R` | Reset car |
| `M` | Back to menu |
