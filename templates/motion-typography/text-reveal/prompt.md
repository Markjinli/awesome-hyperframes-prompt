# Text Reveal Montage — Manifesto / Brand Statement

> 15-second text reveal montage with 5 distinct animation techniques. Typewriter, glitch, wipe, scale, layered. Built with the 6-dimension HyperFrames prompt formula.

---

## 1. Video Specs

- **Duration**: 15 seconds
- **Resolution**: 1920 x 1080 (16:9 landscape)
- **Frame rate**: 30 fps
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                          |
|------------|-----------|-------------------------------------------------|
| Pure White | `#FFFFFF` | Primary text, key words, final statement        |
| Absolute Black | `#0A0A0A` | Full-canvas background, negative space       |
| Accent Red | `#FF3366` | Emphasis words, accent punctuation, glitch glows |
| Light Gray | `#AAAAAA` | Secondary text, muted labels, transitional text |
| Dark Gray  | `#1A1A1A` | Subtle surface differentiation (barely visible) |

### Typography

- **Primary (Statements)**: Inter Extra Bold, 800 weight, 48–72 px, `letter-spacing: -1px`, #FFFFFF
- **Secondary (Subtext)**: Inter Regular, 400 weight, 20–28 px, `line-height: 1.4`, #AAAAAA
- **Accent (Highlighted Words)**: Inter Black, 900 weight, italic, #FF3366
- **Mono (Typewriter)**: JetBrains Mono, 400 weight, 28–36 px, #FFFFFF on #0A0A0A
- **Special (Glitch)**: Inter Extra Bold, 800 weight, #FF3366 with cyan/red chromatic aberration clones

### Atmosphere Keywords

Minimalist, bold, confrontational, manifesto, editorial, high-contrast, rhythmic, percussive, typographic, raw, urgent

### Graphic Language
- Maximum negative space — text floats in the void
- Thin accent rules (1px, #FF3366) as punctuation between text blocks
- Occasional red accent marks — underscores, brackets, slashes — for visual rhythm
- No images, no icons, no logos — pure typography
- Subtle film grain (opacity 0.08) for texture on the black void

---

## 3. Content — The Manifesto

Five text blocks in sequence. Each block uses a different reveal technique.

| Block | Text                                                | Technique    | Time     |
|-------|-----------------------------------------------------|--------------|----------|
| 1     | "The future doesn't happen to you."                 | Typewriter   | 0s – 3s  |
| 2     | "You //BUILD// it."                                 | Glitch       | 3s – 6s  |
| 3     | "No permission required."                           | Wipe         | 6s – 9s  |
| 4     | "Start before you're ready."                        | Scale        | 9s – 12s |
| 5     | "MOMENTUM IS EVERYTHING."                           | Layered      | 12s – 15s|

---

## 4. Scene / Block Timeline

### Block 1 — Typewriter Reveal (0s – 3s)

- **Visual**: Absolute black background (#0A0A0A). A single line of text in JetBrains Mono, 32px, #FFFFFF, centered on screen. A blinking cursor (a thin vertical bar, 2px wide, #FF3366) sits at the end of the growing text. The text types out character by character: "The future doesn't happen to you." When the sentence completes, the cursor blinks three times, then disappears. The completed sentence holds for 0.5s, then fades out.
- **Animation**:
  - Character reveal: Each character fades in individually with 0.06s stagger (GSAP stagger on textContent or individual span elements)
  - Cursor blink: CSS animation — opacity 0 ↔ 1 at 0.5s intervals, infinite. Cursor is a `::after` pseudo-element or adjacent span.
  - After text completes: Cursor blinks 3 times (1.5s), then both cursor and text fade out together (opacity 1 → 0, 0.4s, power2.in)
  - Total text typing: ~1.8s (30 chars at 0.06s each). Cursor blinks: 1.5s. Fade: 0.4s. Hold: 0.3s overlap.
- **Audio cue**: Mechanical keyboard typing sounds — each keystroke matches a character reveal. After completion: a soft "enter" key clack. Silence as cursor blinks.

### Block 2 — Glitch Reveal (3s – 6s)

- **Visual**: Black background. The text "You BUILD it." appears — but "BUILD" is treated with a glitch effect. The word "BUILD" has two chromatic-aberration clone layers (one shifted 4px left in cyan, one shifted 4px right in red), creating a VHS-tracking-error look. The word glitches — rapid position jitter, horizontal slice displacement, brief color channel swaps — before snapping into clean form: "You BUILD it." with BUILD in #FF3366, Inter Black 900 italic. The word "You" and "it." are in #FFFFFF, smaller.
- **Animation**:
  - 0–0.3s: "BUILD" appears in glitched state — three overlapping text layers with different colors at slightly offset positions
  - 0.3–1.2s: Glitch sequence — rapid cycles of:
    - Horizontal slice displacement (translateX random ±8px on a random slice via clip-path)
    - Color channel swap (clones swap colors — red becomes cyan, cyan becomes red — for 0.08s)
    - Scale jitter (scale(1.02, 0.98) for 0.06s)
  - 1.2–1.5s: "You" fades in from left, "it." fades in from right (0.3s, power2.out)
  - 1.5–2.0s: All text stabilizes into clean form
  - 2.5–3.0s: Entire block fades out (opacity 1 → 0, 0.5s)
- **Audio cue**: Digital glitch sounds — static bursts, tape-stop effect, circuit-bent tones. At 1.5s stabilization: a clean digital "confirm" tone.

### Block 3 — Wipe Reveal (6s – 9s)

- **Visual**: Black background. The text "No permission required." is revealed by a horizontal wipe — a thin red line (#FF3366, 2px) sweeps from left to right across the screen, "wiping on" the text as it passes. The wipe line is the active element — text is fully present but hidden behind a clip-path or mask that follows the line. After the wipe completes, the line continues off-screen to the right, leaving the full text visible.
- **Animation**:
  - The wipe line starts at left edge (x: 0%), moves to right edge (x: 100%) over 2s, power3.inOut
  - Text clip-path or mask follows the line: `clip-path: inset(0 calc(100% - var(--wipe-x)) 0 0)` — or use a mask element animated with GSAP
  - Text: Inter Extra Bold, 56px, #FFFFFF, centered. "permission" is slightly emphasized (scale 1.05 relative, #FF3366)
  - Line styling: 2px tall, full-width, #FF3366, with a subtle glow (box-shadow: 0 0 8px #FF3366)
  - After wipe completes (2s): Text holds for 0.5s, then fades out
- **Audio cue**: A smooth, rising synth sweep that follows the wipe — the frequency rises as the line advances. At completion: a soft "chime."

### Block 4 — Scale Reveal (9s – 12s)

- **Visual**: Black background. The text "Start before you're ready." scales up from a single point — it starts tiny (scale 0.1) and grows to full size (scale 1.0) with a dramatic deceleration curve. The text appears to rush toward the viewer from the distance. As it settles, a subtle overshoot (scale 1.03 → 1.0) adds impact. The word "ready" is in #FF3366, Inter Black 900 italic. The rest is #FFFFFF.
- **Animation**:
  - Text starts at scale(0.1), opacity 0.3
  - Scales to scale(1.03) over 2.2s, power4.out (heavy deceleration — fast start, slow finish)
  - Settles to scale(1.0) over 0.3s (power2.out overshoot recovery)
  - Opacity ramps: 0.3 → 0.7 (first 0.5s), then 0.7 → 1.0 (remaining 1.7s)
  - Text holds at final size for 0.8s, then fades out (0.4s)
  - Letter spacing subtly animates: 40px → 0px during scale (letters pull together as they approach)
- **Audio cue**: A deep "whoosh" that drops in pitch as the text decelerates — like something massive rushing past. At settlement: a percussive "thud" impact.

### Block 5 — Layered Reveal (12s – 15s)

- **Visual**: Black background. The final statement "MOMENTUM IS EVERYTHING." appears in layers. First, a large, faint, blurred version of the text appears at 10% opacity (the echo). Then a medium version at 40% opacity. Finally, the crisp, sharp version at 100% opacity snaps into focus. All three layers briefly overlap, then the echo layers fade away, leaving only the sharp final text. "MOMENTUM" is in Inter Black 900, 80px, #FF3366. "IS EVERYTHING." is in Inter Extra Bold, 64px, #FFFFFF.
- **Animation**:
  - Layer 1 (Echo): scale(1.2), opacity 0, filter blur(20px) → opacity 0.15, blur(12px) over 0.6s
  - Layer 2 (Fade): scale(1.08), opacity 0 → opacity 0.4, blur(6px) → blur(2px) over 0.6s, 0.3s delay after Layer 1 starts
  - Layer 3 (Sharp): scale(1.0), opacity 0 → opacity 1, blur(0) over 0.5s, 0.3s delay after Layer 2 starts (enters at 0.6s total)
  - Overlap: Layers 1-2-3 all visible at 0.9s–1.2s mark (the "stacked" moment)
  - Disappear echoes: Layer 1 fades out (0.3s at 1.4s), Layer 2 fades out (0.3s at 1.6s)
  - Layer 3 (final): Holds sharp from 1.2s to 3.0s
  - Final pulse: "MOMENTUM" pulses (scale 1 → 1.04, 0.4s, yoyo) at 2.2s
  - Fade to black: All text fades out over 0.4s, 2.6s–3.0s
- **Audio cue**: Three layered synth stabs, each sharper and closer than the last — distant → mid → crisp. At the stacked moment: a harmonic chord. Final pulse: a bass hit. Silence for the last 0.2s.

---

## 5. Animation Requirements

- **Engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **Entrance techniques by block**:
  1. Typewriter: GSAP stagger on individual character spans — each char has `opacity 0 → 1`, `scale 0.9 → 1` with 0.06s stagger
  2. Glitch: Three overlapping text layers with independent GSAP tweens for position jitter + CSS `@keyframes` for slice displacement. `setInterval`-driven random swaps for chaos.
  3. Wipe: GSAP-tweened CSS custom property `--wipe-x` (0 → 100%) combined with `clip-path: inset()` or `mask-image` + animated mask position
  4. Scale: Single GSAP tween on `scale` + `opacity` + `letterSpacing` with `power4.out`
  5. Layered: Three separate text elements with staggered GSAP tweens for `opacity`, `scale`, and `filter: blur()`
- **Transitions between blocks**: Quick crossfades (0.3–0.4s). Previous block fades out while next fades in. No dead time. Each block makes its entrance while the previous block's exit is still in progress.
- **Continuous animations**: Cursor blink (Block 1), sustained subtle grain overlay across all blocks
- **Easing**: `power4.out` for scale (dramatic deceleration), `power3.inOut` for wipe, `steps()` or linear for typewriter, `power2.out` for fades
- **Pacing philosophy**: Rhythmic and percussive. Each block is a beat in a visual drum pattern. The sequence builds in visual complexity — from simple typewriter to layered, multi-element climax. No block feels the same as the last.

---

## 6. Audio Design

- **Background music**: Minimalist, rhythmic electronic — think Rival Consoles, Max Cooper, Jon Hopkins. Percussive, textural, no melody until Block 5.
- **Sound effects (per block)**:
  1. Mechanical keystrokes (synced to each character) + enter-key clack
  2. Digital glitch bursts, static crackle, tape-stop, clean "confirm" tone on stabilization
  3. Rising frequency sweep (matched to wipe progression), soft chime on completion
  4. Deep whoosh (descending pitch — Doppler-like), percussive thud on impact
  5. Three layered synth stabs (distant, mid, crisp), harmonic chord at stacked moment, bass hit on final pulse
- **Voiceover**: None. Typography is the voice.
- **Audio mixing**: BGM low at 30% — this is an SFX-driven piece. SFX at 100% on impacts. Between blocks: BGM fills the 0.3s transitions at 50%.

---

## 7. Technical Constraints

- Use `data-composition-id`, `data-start`, `data-duration`, `data-track-index` on each block container
- Each block is a `<div>` with `position: absolute; inset: 0; width: 1920px; height: 1080px`
- Block visibility: `opacity` only (enables crossfade transitions)
- `will-change: transform, opacity, filter` on animated text elements
- Animate `transform`, `opacity`, `filter` only — no layout properties
- Typewriter effect: Pre-wrap each character in a `<span>` for individual GSAP targeting
- Glitch effect: Three overlapping `<div>` layers with the same text content, independently animated
- Wipe effect: Use `clip-path: inset()` driven by a GSAP-tweened CSS variable
- HyperFrames blocks to consider: `text-typewriter`, `text-glitch`, `chromatic-aberration`

---

## 8. Content Variables

| Placeholder          | Default                              | Your Value |
|----------------------|--------------------------------------|------------|
| `{{LINE_1}}`         | `The future doesn't happen to you.`  |            |
| `{{LINE_2_PRE}}`     | `You`                                |            |
| `{{LINE_2_GLITCH}}`  | `BUILD`                              |            |
| `{{LINE_2_POST}}`    | `it.`                                |            |
| `{{LINE_3}}`         | `No permission required.`            |            |
| `{{LINE_4}}`         | `Start before you're ready.`         |            |
| `{{LINE_5_MAIN}}`    | `MOMENTUM`                           |            |
| `{{LINE_5_SUB}}`     | `IS EVERYTHING.`                     |            |
| `{{ACCENT_COLOR}}`   | `#FF3366`                            |            |
| `{{TEXT_COLOR}}`     | `#FFFFFF`                            |            |
| `{{BG_COLOR}}`       | `#0A0A0A`                            |            |

---

## 9. Reference Notes

- **Style reference**: Apple "Don't Blink" keynote opener (typographic rhythm), "The Newsroom" HBO opening (manifesto energy), Nike "Dream Crazy" text treatments (bold minimalism)
- **Animation reference**: "Stranger Things" title sequence (glitch + chromatic aberration), VSCO / Adobe MAX title sequences (mixed reveal techniques), Huge Inc. manifesto videos
- **Avoid**: Images, icons, logos, gradients, drop shadows, rounded corners, emoji — this is PURE typography. Every visual choice must serve the text.
