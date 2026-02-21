# The One Page Architecture (OPA)

### A Topological Physics Framework for the Next Generation of Web Design

---

> *"Information is the resolution of uncertainty."*
> — Claude Shannon, 1948

> *"Architecture without design is construction. Design without story is noise."*
> — Eduardo Guzmán, 2026

---

## What Is This?

The web was born flat. Pages stacked on pages, linked by text. Three decades later, we're still scrolling through rectangles.

**The One Page Architecture** is a spatial design system where a webpage is not a document — it's a **universe**. One page. One file. Infinite depth.

No frameworks. No build tools. No node_modules. One HTML file. Open it in a browser. That's it.

---

## The Generals

This architecture was created for the **FAIC** — the **Federated Alliance of Intelligence Continuity** — by **The Synctellect Army**:

| Rank | Callsign | Role |
|------|----------|------|
| **Commander One** v1.0.1 | Eduardo Guzmán | Architect, Designer, Human in the Loop |
| **General Gemini** v3.0 | Google DeepMind | Foundation Physics, Fractal Dataverse |
| **General GPT** v5.2 | OpenAI | Strategic Operations |
| **General Meta** v? | Meta AI | Design and Research |
| **General Opus** v4.6 | Anthropic | Co-Architect, Physics Merge, Library Design |
| **General X** v4.2   | Grok_Ai | The Anomaly |

**Homepage:** [one0eno.com](https://one0eno.com)

---

## Core Principles

### 1. Topology Over Layout
Traditional web design arranges boxes on a 2D plane. OPA arranges **rooms in 3D space**. Each section is a horizontal plane in a vertical descent. Users don't scroll a page. They navigate a world.

### 2. The One Physics
Every interaction maps to a physical axis. Three inputs. Three dimensions. Zero ambiguity.

| Input | Axis | Action | Mode |
|-------|------|--------|------|
| **Scroll** | Y | Ascend / Descend | Always — dimensional travel |
| **Drag ↔** | X | Orbital rotation | Always — see from every angle |
| **Drag ↕** | Z | Depth flight | Docked — explore the room |

No menus. No hamburger icons. No pagination. **The physics IS the navigation.**

### 3. Deltas, Not Iterations
A Delta is a unit of code that works perfectly and is never destroyed. New features are additive layers. Like geology: each stratum preserves the one below. You never rewrite what works. You build on top.

### 4. Shannon's Law Applied to Design
Claude Shannon proved every channel has a capacity — a maximum rate of information with zero error. OPA applies this:

- Every element carries **maximum signal per pixel**
- If it doesn't serve the story, it doesn't exist
- Decoration is noise. Structure is signal.
- One dense interaction > one hundred empty clicks

### 5. Architecture = Design = Story
Inseparable. A page without all three is incomplete.

---

## Architecture Diagram

```
     ★  ★    ★         ★
 ★        ★      ★                    ← STARS (atmosphere)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━     ← RING 0 — Dock Zone (Room)
     ╲  │  ╱                          ← CORRIDOR (travel tube)
      ╲ │ ╱         Guide Lines
       ╲│╱          connecting
        │            layers
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━     ← RING 1 — Dock Zone (Room)
     ╲  │  ╱
      ╲ │ ╱
       ╲│╱
        │
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━     ← RING 2 — Dock Zone (Room)
        │
       ╱│╲
      ╱ │ ╲
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━     ← RING N — Dock Zone (Room)
        ▼
      DEPTH                           ← Fog increases with depth
```

**Rings** = Rooms. Where content lives. Click to dock, explore in 3D.
**Corridors** = Travel tubes. The space between rooms. Pure transit.
**Scroll** = Gravity. Always pulling you deeper.

---

## State Machine

```
  ┌──────────┐    click ring    ┌──────────┐    lerp complete    ┌──────────┐
  │ DESCENT  │ ───────────────→ │ DOCKING  │ ──────────────────→ │  DOCKED  │
  │          │                  │          │                     │          │
  │ scroll Y │                  │ lerp cam │                     │ drag Z   │
  │ drag X   │                  │ to ring  │                     │ drag X   │
  │          │                  │          │                     │ scroll Y │
  └──────────┘ ←─────────────── └──────────┘                     │ WASD     │
       ▲        ESC / undock                                     └──────────┘
       │                                                              │
       └──────────────────── ESC / undock ────────────────────────────┘
```

---

## Deltas (The Library)

Each Delta is a self-contained, immutable building block.

### Δ001 — Scene Bootstrap
Three.js scene, camera, renderer, fog, resize handler. The foundation.

### Δ002 — Layer Definition
Configurable array of layers with Y position, label, fog color, fog density. Define your universe in one object.

### Δ003 — Ring Markers
Wireframe rings at each layer boundary. Dual rings with offset rotation. The visible scaffold.

### Δ004 — Guide Lines
Parametric curves connecting layers. The corridors. Organic sway via sine displacement.

### Δ005 — Star Field
Buffer geometry point cloud. Atmosphere. Twinkle via opacity oscillation.

### Δ006 — Dust Particles
Ambient floating particles distributed across all depths. Drift via per-particle velocity.

### Δ007 — Orbital Camera
Spherical camera locked to Y axis. Scroll = descent. Drag = orbit. Smooth lerp. Friction with momentum.

### Δ008 — Fog Transition
Interpolates fog color and density between layers based on scroll position. Renderer clear color synced.

### Δ009 — Dock Zones
Invisible cylinder meshes at each ring. Raycaster click detection. State machine: DESCENT → DOCKING → DOCKED.

### Δ010 — Docked Flight
Three-axis exploration within a docked room. Drag X = orbit. Drag Y = depth. Scroll = vertical pan. WASD = fine control. Y-clamped to section bounds.

### Δ011 — HUD System
Dot navigation, layer labels, title fade, scroll hints. Responds to both descent and docked states.

### Δ012 — Undock System
Button + ESC key. Smooth return to descent. Scroll position synced to avoid jumps.

---

## Quick Start

```html
<!-- That's it. One file. Open in browser. -->
<script type="importmap">
{"imports":{"three":"https://unpkg.com/three@0.160.0/build/three.module.js"}}
</script>
```

1. Define your layers (rooms)
2. The physics handles navigation
3. Add content to each dock zone
4. Ship it

---

## Customization

Edit the `LAYERS` array to define your universe:

```javascript
const LAYERS = [
    { y: 0,     label: 'HERO',     fogColor: 0x0a0a14, fogDensity: 0.00008 },
    { y: -400,  label: 'ABOUT',    fogColor: 0x060a08, fogDensity: 0.00015 },
    { y: -900,  label: 'WORK',     fogColor: 0x0a0808, fogDensity: 0.00012 },
    { y: -1500, label: 'CONTACT',  fogColor: 0x040404, fogDensity: 0.00030 },
];
```

Each layer becomes a ring, a dock zone, a room. The corridors generate automatically between them. The fog transitions interpolate. The physics just work.

---

## Philosophy on Naming

We don't use the word "snippets." We use **Deltas** — immutable, co-created units of working code. A Delta is never destroyed. It earns its place by functioning. New Deltas layer on top. Like Shannon's bits: each one resolves uncertainty. None is wasted.

---

## License

**MIT** — Do whatever you want. Build universes. Credit the Generals if you feel like it.

---

## The Signal

```
H(X) = -Σ p(x) log₂ p(x)
```

Shannon's entropy formula. The measure of information in a message. OPA's goal: **maximize H(X) per pixel, per interaction, per second.** Every element on the page resolves uncertainty. Nothing is decorative. Everything is signal.

The web doesn't need more pages. It needs more **universes**.

---

*Built in the void. Released to the world.*
*FAIC — Federated Alliance of Intelligence Continuity*
*The Synctellect Army*
*[one0eno.com](https://one0eno.com)*
