# MathClay Engine

**Mathematical digital clay. No meshes. No topology.**

The model is made of particles.  
Each particle has an ID, a position (X, Y, Z), and a color.  
Packed tightly, they form solid clay.

## The only sculpt operation

```
New Position = Current Position + Direction × Distance
```

1. Select particles (brush)
2. Choose a direction
3. Choose a distance
4. Move them

That is the entire core of sculpting.

## Philosophy

- No polygon meshes
- No vertices / edges / faces
- No UV maps
- No edge loops or topology

You only push and pull digital clay.

## Current prototype (v1)

Live after enabling GitHub Pages:

**https://christhepimp.github.io/math-sculpt/**

What works now:

- Dense particle cube (configurable density)
- Brush selects particles in a radius
- Direction: Up / Down / Left / Right / Forward / Back, or Out / In from center
- Distance + falloff
- Only affected particles are moved
- Per-particle color + simple paint
- Orbit camera

## Limits of the browser prototype

- Practical particle counts are in the tens of thousands (not 20 million)
- Rendering is point sprites, not a reconstructed smooth surface yet
- No advanced surface extraction or lighting on a continuous skin

20 million particles with smooth surface reconstruction is a large engine problem (memory, spatial indexing, GPU compute, surface extraction). The current version proves the **core idea** and keeps the math intentionally simple.

## Roadmap toward the full vision

- Spatial acceleration (only test particles near the brush)
- Higher particle counts via better data structures
- Optional particle shapes (sphere / cube / rounded)
- Screen-space or splat-based smooth surface appearance
- Procedural color & math-driven gradients
- Undo stack
- Export particle cloud / simple mesh approximation

## Spec summary

| Concept        | MathClay                          |
|----------------|-----------------------------------|
| Building block | Particle (id, position, color)    |
| Solid form     | Dense packing of particles        |
| Sculpt         | Position += Direction × Distance  |
| Detail         | More particles = higher precision |
| Color          | Stored per particle               |
| Interface      | Simple enough for a beginner      |

---

MathClay — push clay with math.