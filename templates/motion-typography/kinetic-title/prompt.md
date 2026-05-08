# Kinetic Title Sequence — "MOMENTUM"

> 10-second pure kinetic typography sequence. Each letter animates independently — explode in, settle, pulse together. Built with the 6-dimension HyperFrames prompt formula.

---

## 1. Video Specs

- **Duration**: 10 seconds
- **Resolution**: 1920 x 1080 (16:9 landscape)
- **Frame rate**: 60 fps (for smooth kinetic motion)
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                          |
|------------|-----------|-------------------------------------------------|
| Neon Cyan  | `#00F0FF` | Letter fill, glow halos, light streaks          |
| Deep Void  | `#0A0A0A` | Full-canvas background, absolute black          |
| Electric White | `#E0F7FF` | Letter core highlights, spark particles      |
| Cyan Shadow | `#003840` | Deep letter shadows, depth layer                |

### Typography

- **Primary**: Outfit Black, 900 weight, 180px, `letter-spacing: 12px`
- **No secondary fonts** — this is a single-word, single-font piece. All visual interest comes from motion, not typographic contrast.
- **Text treatment**: Each letter is an independent DOM element. No ligatures. Individual tracking control.

### Atmosphere Keywords

Explosive, electric, futuristic, high-impact, neon-noir, pure-motion, typographic-art, kinetic, energetic, synaesthetic

### Graphic Language
- Neon cyan glow: `text-shadow: 0 0 20px #00F0FF, 0 0 60px #00F0FF, 0 0 120px #00F0FF, 0 0 200px rgba(0,240,255,0.4)`
- Background: Subtle radial gradient from #0A0A0A at edges to #0D1A1C at center (barely perceptible depth)
- Particle system: Small cyan dots that trail the letters during entrance, fade out after settling
- Grid reference lines: Faint cyan grid (opacity 0.03) on background for spatial reference — visible only during letter movement

---

## 3. The Word

- **Word**: MOMENTUM
- **Letters**: M · O · M · E · N · T · U · M (8 letters, each independent)
- **Letter spacing**: 12px between letters (tight but not touching), total word width ~1400px centered
- **Letter properties**: Each letter at 180px Outfit Black 900. Fill: #00F0FF. Stroke: none. Glow via text-shadow.

---

## 4. Scene / Phases (Single Continuous Sequence)

This is a single 10-second composition — there are no scene cuts. The sequence unfolds in five kinematic phases.

### Phase 1 — Explosion In (0s – 2.5s)

- **Visual**: All 8 letters are invisible. At 0s, each letter simultaneously begins flying in from a random off-screen position to its final resting position in the centered "MOMENTUM" word. Each letter travels along a slightly arced path (cubic-bezier) and arrives at a different time, creating a staggered settling effect. Letters leave faint cyan motion trails.
- **Animation**:
  - Each letter starts at a random position: x ∈ [-600, +600], y ∈ [-400, +400], rotation ∈ [-180deg, +180deg]
  - Each letter travels to its final position (x=0, y=0, rotation=0) over 1.2–2.2s (varied durations)
  - Easing: `power4.out` for deceleration — letters slow down as they approach home
  - Motion trail: Each letter has a `::before` pseudo-element that clones the letter with lower opacity and a slight transform lag, creating a smear
  - By 2.5s: All 8 letters have settled into their grid positions
- **Audio cue**: A deep sub-bass sweep (20Hz → 80Hz). At 1.5s, a metallic "clang" as the first letter (M) locks into position. Subtle whoosh on each letter's arrival.

### Phase 2 — The Settle Pulse (2.5s – 4s)

- **Visual**: All 8 letters are now in position. The word "MOMENTUM" is fully legible. The letters breathe — a synchronized pulse travels through the word from left to right, each letter scaling up slightly (1 → 1.08 → 1) in sequence, creating a wave. Neon glow intensifies during the pulse.
- **Animation**:
  - Wave pulse: Letters scale sequentially from left to right (M→O→M→E→N→T→U→M) with 0.08s stagger
  - Each letter: scale(1) → scale(1.08) (0.15s, sine.inOut) → scale(1) (0.15s, sine.inOut)
  - Glow intensifies during scale peak (text-shadow spread +40%)
  - The wave travels across the word twice (2.5s → 3.5s, then 3.5s → 4s at faster tempo)
- **Audio cue**: A rising electronic arpeggio, each note corresponding to one letter's pulse. Eight-note sequence, then repeated faster. Synth texture thickens.

### Phase 3 — Individual Letter Solos (4s – 7s)

- **Visual**: The wave culminates in a sequence where each letter takes a brief solo. One at a time, a letter lifts upward (y: -60px), scales up (1 → 1.3), glows brighter, then drops back into position. The sequence moves through the word twice — first pass: M(4s), O(4.3s), M2(4.6s), E(4.9s); second pass faster: N(5.3s), T(5.6s), U(5.9s), M3(6.2s). During each solo, the other letters dim to 30% opacity.
- **Animation**:
  - Solo letter: y: 0 → -60px → 0 (0.25s up, 0.15s hold, 0.2s down) using power3.out for lift, power2.in for drop
  - Scale: 1 → 1.3 → 1 (sync with y animation)
  - Glow: text-shadow expands to 0 0 40px, 0 0 100px, 0 0 180px during peak
  - Other letters: opacity 1 → 0.3 → 1 (0.15s transition each direction)
- **Audio cue**: Each letter solo gets a distinct synth tone — 8 different pitches forming a melody. Percussion enters — a driving kick + snare pattern at 120 BPM. The word is building momentum.

### Phase 4 — The Unity Explosion (7s – 8.5s)

- **Visual**: After the final letter (the second M, "M3") returns from its solo, all 8 letters simultaneously explode outward slightly (scale 1 → 1.15), then slam back together into perfect formation. The neon glow reaches maximum intensity — the entire word blazes. Cyan particles burst from the letter edges and drift outward. The background grid briefly flashes to full visibility.
- **Animation**:
  - All letters: scale(1 → 1.15, 0.3s, expo.out) → scale(1, 0.4s, elastic.out(1, 0.3))
  - Glow: text-shadow values 3x for 0.5s, then settle to 1.2x intensity
  - Particles: 40–60 small cyan circles (4px) spawn at random letter positions, fly outward with randomized velocity (GSAP to random x/y, stagger 0.01s, opacity 1 → 0 over 1s)
  - Background grid: opacity 0.03 → 0.15 → 0.03 over 1.2s
  - Camera-like shake: The entire word container jitters (x: ±4px, y: ±3px, random, 0.05s intervals, 0.6s duration)
- **Audio cue**: A massive bass drop. Distorted synth chord. White noise burst layered under the particle explosion. The percussion cuts for 0.3s, then returns harder.

### Phase 5 — The Sustain (8.5s – 10s)

- **Visual**: All 8 letters hold position, glowing intensely but steadily. The particles have faded. The word "MOMENTUM" is solid, powerful, definitive. A slow, subtle breathing continues — the entire word scales gently (1 → 1.02, 2s cycle, yoyo). At 9.5s, a final pulse of the neon glow (brief 1.5x intensity) before settling to the end state. Fade to black over the final 0.3s.
- **Animation**:
  - Breathing: scale(1 → 1.02, 2s cycle, sine.inOut, yoyo, repeat)
  - Glow sustain: text-shadow at 1.2x steady, with subtle intensity oscillation (±10%, 3s cycle)
  - Final pulse at 9.5s: glow 2x for 0.3s
  - Fade out: word opacity 1 → 0, background stays black, 0.3s
- **Audio cue**: Music holds on a sustained synth chord with reverb tail. At 9.5s, a final bass hit. Reverb decays through the fade-out. Silence at 10s.

---

## 5. Animation Requirements

- **Engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **Key techniques**:
  - **Independent letter control**: Each letter is a separate `<span>` element with a unique ID. GSAP timelines target individual letters.
  - **Motion paths**: Letters fly in from random positions using GSAP `x`, `y`, `rotation` tweens (no MotionPath plugin needed — direct property tweens with power4.out create natural deceleration arcs)
  - **Motion trails**: CSS `::before` pseudo-elements on each letter span, animated with a slight delay behind the main element
  - **Particle system**: JavaScript-generated `<div>` elements appended to a particle container, animated with GSAP to random destinations
  - **Stagger waves**: GSAP `stagger` with `from: "left"` or manual timeline sequencing for waves and solos
- **Entrance style**: Explosive deceleration (power4.out) — letters fly in fast and brake hard
- **Continuous animations**: Breathing scale, glow oscillation, subtle background grid drift
- **Easing**: `power4.out` for letter entrances, `sine.inOut` for breathing, `elastic.out(1, 0.3)` for unity slam, `power2.inOut` for solo lifts
- **Timing philosophy**: Pure motion-driven. No stillness. Every frame is either anticipation, action, or reaction. The word is the protagonist — it lives and breathes.

---

## 6. Audio Design

- **Background music**: Cinematic electronic / synthwave. Builds from deep sub-bass (Phase 1) to full percussion + synth chords (Phases 3–5). 120 BPM.
- **Sound effects**: 
  - Letter arrivals: Metallic "clangs" or tonal impacts (8 discrete hits)
  - Wave pulse: Rising synth arpeggio (8 notes)
  - Letter solos: Distinct synth tones (8 pitches, melody)
  - Unity explosion: Bass drop + distorted chord + white noise burst
  - Final pulse: Bass hit + reverb tail
- **Voiceover**: None. The word IS the voice.
- **Audio mixing**: BGM at 80%. SFX punch through at 100% on impacts. Phase 1: sub-heavy. Phase 3: percussion-forward. Phase 4: full spectrum. Phase 5: reverb decay.

---

## 7. Technical Constraints

- Use `data-composition-id`, `data-start`, `data-duration`, `data-track-index` on the scene container
- Single composition (no scene cuts): `data-composition-id="momentum-word"` `data-start="0"` `data-duration="10"`
- Each letter in its own `<span>` with unique `id` for individual animation targeting
- Particle container as a separate `data-track-index="2"` overlay
- Background grid as `data-track-index="0"`
- `will-change: transform, opacity, text-shadow` on letter spans
- Animate `transform`, `opacity`, and `textShadow` only
- 60fps render needs efficient animation — limit particle count, use `will-change`, avoid layout thrashing
- HyperFrames blocks to consider: `particle-system`, `text-glitch` (optional for Phase 4), `neon-glow`

---

## 8. Content Variables

| Placeholder       | Default      | Your Value |
|-------------------|--------------|------------|
| `{{WORD}}`        | `MOMENTUM`   |            |
| `{{NEON_COLOR}}`  | `#00F0FF`    |            |
| `{{BG_COLOR}}`    | `#0A0A0A`    |            |
| `{{FONT_FAMILY}}` | `Outfit`     |            |
| `{{FONT_WEIGHT}}` | `900`        |            |
| `{{FONT_SIZE}}`   | `180px`      |            |
| `{{PARTICLE_COUNT}}` | `50`      |            |
| `{{TOTAL_DURATION}}` | `10`      |            |

---

## 9. Reference Notes

- **Style reference**: "Enter the Void" title sequence (Gaspar Noe), "TRON: Legacy" title cards, Nike "Mamba Forever" kinetic typography spots
- **Animation reference**: Apple "Don't Blink" kinetic type (WWDC openers), Gmunk / Bradley G Munkowitz title design, Animography animated typefaces
- **Technical reference**: GSAP `.staggerTo()` for wave effects, CSS text-shadow for neon glow, DOM-based particle systems
- **Avoid**: Scene cuts (it's one continuous take), subtle/muted color (this is neon-on-void, maximum contrast), serif fonts, slow fades (every entrance is high-velocity)
