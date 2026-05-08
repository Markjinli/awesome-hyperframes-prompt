# Kinetic Title Sequence — "MOMENTUM"

> 10-second pure kinetic typography sequence at 60fps. Each letter flies in from random off-screen positions, settles into the word, then pulses and explodes with neon cyan glow on a deep void background. Single continuous composition.

---

## Use Cases

- Brand film and title sequence openers
- Music video lyric reveals and text effects
- Event and conference opening titles
- Esports and gaming tournament graphics
- Motion design portfolio showreel openers

---

## Key Techniques

| Technique | Where | Why |
|-----------|-------|-----|
| **Independent letter control** | All phases | Each letter is a separate `<span>` with unique ID -- enables per-letter GSAP animation targeting |
| **Randomized explosive entrance** | Phase 1 (0-2.5s) | Each letter flies from random `x: +/-600, y: +/-400` with `power4.out` deceleration -- chaotic energy resolving into order |
| **Wave pulse propagation** | Phase 2 (2.5-4s) | Sequential `scale(1 -> 1.08 -> 1)` travels left-to-right with 0.08s stagger -- the word "breathes" |
| **Letter solos** | Phase 3 (4-7s) | Each letter lifts up (-60px), scales to 1.3, glows brighter, while others dim to 30% -- individual spotlight sequence |
| **Unity explosion** | Phase 4 (7-8.5s) | All letters simultaneously `scale(1 -> 1.15)` then slam back with `elastic.out` + 40-60 particle burst -- climactic release |
| **Particle system** | Phase 4 | JS-generated cyan `<div>` particles spawn at letter positions and fly to random destinations -- reinforcement of energy |
| **Neon glow** | All phases | Multi-layered `text-shadow: 0 0 20px/60px/120px/200px` -- neon tube aesthetic |
| **Motion trails** | Phase 1 | `::before` pseudo-elements clone letters with lower opacity and transform lag -- speed smear |
| **60fps target** | Global | High frame rate for smooth kinetic motion -- requires `will-change` and efficient particle counts |

---

## Customization

1. Replace `"MOMENTUM"` with your word -- letters are auto-handled as individual spans
2. Adjust neon color `#00F0FF` (cyan) -> your glow color
3. Modify font: `Outfit Black 900, 180px` -> your typeface and size
4. Tune particle count `{{PARTICLE_COUNT}}` (default 50) for performance
5. Adjust fly-in ranges: `x: +/-600, y: +/-400` -> wider or tighter entrance
6. Change background `#0A0A0A` -> your void color

---

## Template Metadata

- **Category**: Motion Typography
- **Subcategory**: Kinetic Title
- **Format**: 16:9 Horizontal (1920x1080)
- **Duration**: 10s (single continuous composition)
- **Frame Rate**: 60fps
- **Difficulty**: Advanced -- requires per-letter DOM control and particle system
- **Animation Engine**: GSAP 3
- **Fonts**: Outfit (Google Fonts)
- **Blocks suggested**: `particle-system`, `text-glitch`, `neon-glow`
