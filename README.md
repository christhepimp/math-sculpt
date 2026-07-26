# Math Sculpt

**Geometry and color are both pure mathematics.**

Start with a square clay box. Every deformation and every color is defined by math expressions. No brushes. No painted textures. Only formulas.

## Live Demo

Enable GitHub Pages (Settings → Pages → branch `main` / root):

**https://christhepimp.github.io/math-sculpt/**

## Pure math systems

### Geometry
- **Y mode**: formula returns a number → displacement on Y
- **Vector mode**: formula returns `[nx, ny, nz]` → complete mathematical remapping of every vertex

### Color
Formula must return `[r, g, b]` in the 0–1 range. Applied as vertex colors, driven entirely by math on the original box coordinates (and time).

Examples:
```js
[0.75 + 0.25*Math.sin(x*4), 0.55 + 0.2*Math.cos(z*3), 0.4]   // warm clay variation
[0.2 + 0.3*Math.abs(x), 0.4 + 0.4*Math.abs(y), 0.7 + 0.3*Math.abs(z)]  // xyz → rgb
[0.9, 0.3 + 0.4*Math.abs(Math.sin(x*8)), 0.15]                 // lava stripes
```

## Detail

Subdivision goes up to **128** (~100k+ triangles). That is the practical real-time ceiling for a pure client-side Three.js mesh generated from a single box.

This cannot match Unreal Engine + Nanite geometric density or Lumen lighting. Those systems are built for offline/authoring pipelines and massive streaming geometry. What you get here is the densest practical **pure-math, real-time, browser-native** sculpt from a starting box.

## Symbols

| Symbol | Meaning |
|--------|---------|
| `x y z` | Original coordinates of the square box vertex |
| `t` | Time (seconds) |
| `Math` | Full JavaScript Math object |

---

Math is the sculptor. Math is the painter.