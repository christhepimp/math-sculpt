# MathClay

**Solid mathematical clay made of fractions.**

A square block of digital clay is divided into **5,832 units** (18³).  
Each unit is exactly the fraction `1/5832` of the whole square.  
You control every unit with pure math.

**Live demo:** [https://christhepimp.github.io/math-sculpt/](https://christhepimp.github.io/math-sculpt/)

---

## The core idea

```
// Direction from angles
dir = (cos(el)·sin(az), sin(el), cos(el)·cos(az))

// Grow / shrink along that direction from the origin
// (perpendicular components stay the same; outer cells move farther)
s = pos · dir
pos = pos - s·dir + (s × (1 + distance × unit_length)) · dir
```

**Unit lengths** (the measure for distance):

- `1` ≈ one unit of growth along the chosen angle
- `2` ≈ two units of growth
- `0.5` ≈ half a unit
- Negative values contract toward the origin

1. Select any units (tap, mini-grid, or d-pad)
2. Type any azimuth angle (0–360°)
3. Type any elevation angle (−90–90°)
4. Type distance in unit lengths
5. Run — the selected cells grow or shrink along the straight line of that angle

---

## What you see

- A true **solid cube** rendered with InstancedMesh boxes (no gaps)
- Each of the 5,832 fractions is a real little cube that touches its neighbors
- Selected units turn pink so you always know what the math will affect
- Thin green reference grid (half previous visual weight)
- Orbit / zoom / pan with one or two fingers

---

## Pure math terminal

Everything is driven by typed numbers:

- **Azimuth + elevation** define an exact 3D direction
- **Distance** grows or shrinks selected cells along that direction from the origin
- **RGB color** — select cell(s) on the mini-grid, set R/G/B (0–1), Apply
- Mini-grid + layer slider + d-pad for precise cell selection
- Click / tap the main clay to add units to selection
- Reset to perfect solid square anytime

No brushes limited to preset directions. No locked tools.  
Just math applied to fractions of a solid square.

---

## Philosophy

| Concept        | MathClay                                      |
|----------------|-----------------------------------------------|
| Building block | Unit / fraction (id, position, color)         |
| Solid form     | Dense packing of 5,832 cubes                  |
| Sculpt         | Scale parallel component from origin along dir |
| Control        | Pure typed math (any angle + distance + RGB)  |
| Detail         | More units = higher precision                 |
| Interface      | Simple terminal + mini-grid anyone can use    |

You are not editing polygons or topology.  
You are moving and coloring the actual fractions that make up the clay.

---

## Current status

- Solid InstancedMesh cube (no sparse points)
- Full math terminal (any direction + grow/shrink distance from origin)
- RGB color controls for selected cells (via mini-grid or multi-select)
- Thinner reference grid
- Mini-grid + d-pad + layer slider for precise selection
- Click / tap to add nearby units to selection
- Reset to perfect solid square
- API surface for AI / external commands (same math)
- Works on desktop and mobile browsers via GitHub Pages

---

## Roadmap

- Higher unit counts with spatial acceleration
- Undo stack
- Export of the unit cloud / simple mesh
- Optional smoother surface appearance while keeping the fraction model underneath

---

**MathClay** — a solid square of fractions you sculpt with pure math.
