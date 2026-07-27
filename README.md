# MathClay

**Solid mathematical clay you sculpt with a grid and pure math.**

Start with a solid square block.  
The grid lets you make **micro adjustments** and **major adjustments** to any part of it.  
Every change is driven by typed math: azimuth, elevation, distance, and RGB color.

**Live demo:** [https://christhepimp.github.io/math-sculpt/](https://christhepimp.github.io/math-sculpt/)

---

## How it works

1. Use the **grid** (mini view + d-pad + layer slider, or tap the clay) to select the cells you want to change.
2. Type an **azimuth** (0–360°) and **elevation** (−90–90°) to set the exact 3D direction.
3. Type a **distance** — this grows or shrinks the selected cells along that direction from the origin.
4. Optionally set **RGB** (0–1) to recolor the clay inside those grid cells.
5. Run.

Small distance values = micro adjustments.  
Larger distance values = major adjustments.  
The grid is how you choose *where* the math is applied.

```
dir = direction from (azimuth, elevation)

for each selected cell:
  s = position · dir
  new_s = s × (1 + distance × cell)
  position = position − s·dir + new_s·dir
```

Perpendicular components stay the same. Outer cells move farther; positive distance expands, negative contracts.

---

## What you see

- A true solid cube rendered with InstancedMesh boxes (no gaps)
- 18×18×18 grid of cells (5,832 total)
- Selected cells turn pink so you always know what the math will affect
- Thin green reference grid
- Orbit / zoom / pan with one or two fingers

---

## Math terminal

Open the **MATH** panel on the right.

### Sculpt
- Azimuth, elevation, distance
- **Run math** — grows/shrinks the current selection along the chosen angle
- Clear select / Reset square

### Clay color (RGB)
- Select cell(s) on the mini-grid
- R, G, B fields (0–1) auto-fill from the current cell
- Live color swatch
- **Apply color to selected**

### Grid select (micro & major targeting)
- Mini 3D view of the current layer
- Axis buttons (X / Y / Z) + layer slider
- D-pad + SELECT (or tap a cell)
- Cursor position and selection count shown live

### API
- Connect / Disconnect
- Live view snapshot
- Paste JSON commands that use the exact same math (sculpt + color + batch)

---

## Philosophy

| Concept     | MathClay                                              |
|-------------|-------------------------------------------------------|
| Starting point | Solid square block                                 |
| Targeting   | Grid for precise selection (micro or major areas)     |
| Sculpt      | Scale along any angle from the origin                 |
| Color       | RGB applied to selected cells                         |
| Control     | Typed math + grid selection                           |
| Interface   | Terminal + mini-grid                                  |

You are not editing polygons or topology.  
You are using the grid to choose cells, then applying pure math to move and color them.

---

## Current status

- Solid InstancedMesh cube
- Grow / shrink along any angle from the origin
- Grid-driven selection for micro and major adjustments
- RGB color controls tied to mini-grid selection
- Thinner reference grid
- Mini-grid + layer slider + d-pad
- Click / tap the main view to add cells to selection
- Reset to perfect solid square
- API that uses the identical math
- Works on desktop and mobile via GitHub Pages

---

## Roadmap

- Higher cell counts with spatial acceleration
- Undo stack
- Export of the cell cloud / simple mesh
- Optional smoother surface appearance while keeping the grid model underneath

---

**MathClay** — solid clay, grid targeting, pure math.
