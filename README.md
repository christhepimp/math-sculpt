# Math Sculpt

**Precision mathematical sculpting starting from a square clay box.**

Open the live app → write math → watch the clay deform in real time.

## Live Demo

Enable GitHub Pages (Settings → Pages → Deploy from branch `main` / root), then the app will be at:

**https://christhepimp.github.io/math-sculpt/**

You can also just open `index.html` locally in any modern browser.

## How it works

1. You start with a **subdivided cube** (the “clay box”).
2. Type a JavaScript math expression that returns a **Y displacement**.
3. Available variables:
   - `x`, `y`, `z` — original vertex position
   - `t` — time in seconds
   - `Math` — full Math object (`sin`, `cos`, `sqrt`, `abs`, `pow`, `random`, etc.)
4. Hit **Apply** or just keep typing (it updates live).

### Example formulas

```js
Math.sin(x * 3) * Math.cos(z * 3) * 0.25     // classic ripple
Math.sin(Math.sqrt(x*x + z*z) * 6) * 0.2     // radial waves
Math.pow(Math.abs(x), 1.5) * Math.sign(x) * 0.2  // sharp crease
(Math.random() - 0.5) * 0.4                  // noise
```

## Controls

| Control        | What it does                          |
|----------------|---------------------------------------|
| Subdivision    | Higher = finer clay (more vertices)   |
| Strength       | Multiplier on the formula result      |
| Box size       | Overall scale of the starting cube    |
| Presets        | One-click common deformations         |
| Reset Clay     | Restore the perfect square box        |

## Tech

- Pure Three.js (no build step)
- Single `index.html` — ready for GitHub Pages or any static host
- Orbit controls, soft lighting, clay-colored material

## Next ideas you can add

- Export to STL / OBJ
- Multi-axis displacement (return a vector)
- Brush-based local sculpting on top of the math
- Save / load formula presets
- Animation of the formula over time

---

Made for people who like their clay precise.