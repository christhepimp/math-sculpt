# MathClay

**Solid mathematical clay made of fractions.**

A square block of digital clay is divided into **5,832 units** (18³).  
Each unit is exactly the fraction `1/5832` of the whole square.  
You control every unit with pure math.

**Live demo:** [https://christhepimp.github.io/math-sculpt/](https://christhepimp.github.io/math-sculpt/)

---

## The core idea

Azimuth + elevation give a direction.  
Distance grows or shrinks the selected units **along that direction from the origin**.

```
dir = direction from (azimuth, elevation)

for each selected unit:
  s = position · dir          // how far it currently is along the direction
  new_s = s × (1 + distance × cell)
  position = position − s·dir + new_s·dir
```

- Perpendicular components stay the same
- Outer units move farther out; inner ones move less
- Positive distance expands, negative contracts

**Unit lengths** (what “distance” means):

- `1` ≈ one cell of growth along the angle
- `2` ≈ two cells
- `0.5` ≈ half a cell
- Negative values pull toward the origin

1. Select units (tap the clay, or use the mini-grid + d-pad)
2. Type azimuth (0–360°)
3. Type elevation (−90–90°)
4. Type distance
5. Run math

---

## What you see

- A true **solid cube** rendered with InstancedMesh boxes (no gaps)
- Each of the 5,832 fractions is a real little cube that touches its neighbors
- Selected units turn pink so you always know what the math will affect
- Thin green reference grid (half previous visual weight)
- Orbit / zoom / pan with one or two fingers

---

## Math terminal

Open the **MATH** panel on the right.

### Sculpt
- Azimuth, elevation, distance fields
- **Run math** — grows/shrinks the current selection along the chosen angle
- Clear select / Reset square

### Clay color (RGB)
- Select one or more cells on the **mini-grid** (or by tapping)
- R, G, B fields (0–1) auto-fill with the current cell’s color when you move the cursor
- Live color swatch
- **Apply color to selected** — paints the clay inside those grid cells

### Grid select
- Mini 3D view of the current layer
- Axis buttons (X / Y / Z) + layer slider
- D-pad + SELECT button (or tap a cell on the mini view)
- Cursor position and selection count shown live

### API (for AI / external control)
- Connect / Disconnect
- Live view snapshot
- Paste JSON commands that use the **exact same** azimuth + elevation + distance + color math

---

## Philosophy

| Concept        | MathClay                                              |
|----------------|-------------------------------------------------------|
| Building block | Unit / fraction (id, position, color)                 |
| Solid form     | Dense packing of 5,832 cubes                          |
| Sculpt         | Scale the parallel component from the origin along dir |
| Color          | RGB (0–1) applied to selected units                   |
| Control        | Typed math + mini-grid selection                      |
| Detail         | More units = higher precision                         |
| Interface      | Terminal + mini-grid anyone can use                   |

You are not editing polygons or topology.  
You are moving and coloring the actual fractions that make up the clay.

---

## Current status

- Solid InstancedMesh cube (no sparse points)
- Grow / shrink along any angle from the origin (not rigid travel)
- RGB color controls driven by mini-grid selection
- Thinner reference grid
- Mini-grid + layer slider + d-pad for precise cell picking
- Click / tap the main view to add units to selection
- Reset to perfect solid square
- API surface that uses the identical math (sculpt + color + batch)
- Works on desktop and mobile browsers via GitHub Pages

---

## Roadmap

- Higher unit counts with spatial acceleration
- Undo stack
- Export of the unit cloud / simple mesh
- Optional smoother surface appearance while keeping the fraction model underneath

---

**MathClay** — a solid square of fractions you sculpt with pure math.
