# MathClay

**Solid mathematical clay made of fractions.**

A square block of digital clay is divided into **5,832 units** (18³).  
Each unit is exactly the fraction `1/5832` of the whole square.  
You control every unit with pure math.

**Live demo:** [https://christhepimp.github.io/math-sculpt/](https://christhepimp.github.io/math-sculpt/)

---

## The core idea

```
pos += dir(azimuth, elevation) × (distance / 500)
```

1. Select any units by number (or range, or by tapping)
2. Type any azimuth angle (0–360°)
3. Type any elevation angle (−90–90°)
4. Type any distance
5. Run

That single operation is enough to push, pull, stretch, and reshape the solid square into **any 3D form**.

---

## What you see

- A true **solid cube** rendered with InstancedMesh boxes (no gaps)
- Each of the 5,832 fractions is a real little cube that touches its neighbors
- Selected units turn pink so you always know what the math will move
- Orbit / zoom / pan with one or two fingers

---

## Pure math terminal

Everything is driven by typed numbers:

- Select units: `0, 1, 5, 100-200` or tap the clay
- Azimuth + elevation define an exact 3D direction
- Distance scales how far those fractions travel
- Run as many times as you want — the design space is unlimited

No brushes limited to preset directions. No locked tools.  
Just math applied to fractions of a solid square.

---

## Philosophy

| Concept        | MathClay                              |
|----------------|---------------------------------------|
| Building block | Unit / fraction (id, position, color) |
| Solid form     | Dense packing of 5,832 cubes          |
| Sculpt         | `pos += dir × distance`               |
| Control        | Pure typed math (any angle + distance)|
| Detail         | More units = higher precision         |
| Interface      | Simple terminal anyone can use        |

You are not editing polygons or topology.  
You are moving the actual fractions that make up the clay.

---

## Current status

- Solid InstancedMesh cube (no sparse points)
- Full math terminal (any direction, any distance)
- Click / tap to add nearby units to selection
- Unit number overlay
- Reset to perfect solid square
- Works on desktop and mobile browsers via GitHub Pages

---

## Roadmap

- Higher unit counts with spatial acceleration
- Undo stack
- Export of the unit cloud / simple mesh
- Optional smoother surface appearance while keeping the fraction model underneath

---

**MathClay** — a solid square of fractions you sculpt with pure math.
