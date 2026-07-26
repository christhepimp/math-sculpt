# Math Sculpt

**The entire sculpting process is pure mathematics.**

You start with a perfect square clay box.  
Every change after that is defined by a mathematical expression.  
No brushes. No mouse pushing. Only math.

## Live Demo

Enable GitHub Pages (Settings → Pages → Deploy from branch `main` / root):

**https://christhepimp.github.io/math-sculpt/**

Or open `index.html` directly in any modern browser.

## Two pure-math modes

### 1. Y Displacement (classic)
Formula returns a **number**. That number is added to the Y coordinate of every vertex.

```js
Math.sin(x * 3) * Math.cos(z * 3) * 0.25
```

### 2. Full Vector Mapping
Formula returns a **3D point** `[nx, ny, nz]`.  
The mathematics completely defines the new position of every vertex of the box.

```js
[x, y + Math.sin(x*3)*Math.cos(z*3)*0.3, z]
```

```js
[x * Math.cos(0.4) - z * Math.sin(0.4), y, x * Math.sin(0.4) + z * Math.cos(0.4)]  // rotate
```

```js
[x + y*0.15, y, z + y*0.15]  // shear
```

## Available symbols

| Symbol | Meaning |
|--------|---------|
| `x y z` | Original coordinates of the square box vertex |
| `t` | Time in seconds |
| `Math` | Full JavaScript Math object (`sin`, `cos`, `sqrt`, `abs`, `pow`, `random`, `PI`, …) |

## Strength

The strength slider blends between the original box (0) and the pure mathematical result (1+).

## Philosophy

This is not a digital sculpting program with math as a helper.  
**Math is the sculptor.** The box is just the starting domain of the function.

---

Made for people who like their clay precise.