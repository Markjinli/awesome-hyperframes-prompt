# Emotional Story — "Letters Never Sent"

> 40-second emotional brand short for a handwriting/letter app. Poetic, nostalgic, deeply human. Built with the 6-dimension HyperFrames prompt formula.

---

## 1. Video Specs

- **Duration**: 40 seconds
- **Resolution**: 1920 x 1080 (16:9 landscape)
- **Frame rate**: 24 fps (film cadence)
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                          |
|------------|-----------|-------------------------------------------------|
| Deep Ink   | `#2B2B2B` | Backgrounds, shadow text, vignettes             |
| Warm Paper | `#C4A882` | Headlines, key words, light accents             |
| Faded Parchment | `#E8D5C0` | Secondary text, soft glows, paper texture       |
| Subtle Wash| `#D9C7B2` | Mid-tone transitions, ink-wash backgrounds       |
| Ink Blue   | `#1E232B` | Deep shadow accents, ink-bottle dark             |

### Typography

- **Primary (Handwritten)**: Caveat, 400 weight, 48–96 px — used for letter excerpts, emotional phrases
- **Secondary (Serif)**: Cormorant Garamond, 300 italic, 24–36 px — used for narration lines, dates
- **Tertiary (Sans)**: Inter, 300 weight, 16–20 px — used for app UI hints, subtle labels

### Atmosphere Keywords

Nostalgic, intimate, melancholic-but-hopeful, tactile, paper-textured, slow-burn, poetic, quiet, handcrafted, memory

### Texture
- Full-canvas paper grain overlay (SVG feTurbulence + color matrix for warm tint)
- Soft vignette on every scene (radial-gradient from transparent to #2B2B2B at 65%)
- Subtle ink-bleed edge effect on text (text-shadow with warm spread)
- Slow drift micro-animation on paper fiber background

---

## 3. Brand Assets

- **App Name**: Letters Never Sent
- **Tagline**: "The words you never wrote. Finally heard."
- **Core Metaphor**: The app is a bridge between what was left unsaid and what can be expressed now
- **Logo**: Wordmark in Caveat, warm paper on deep ink

---

## 4. Scene Timeline

### Scene 1 — Old Letters (0s – 7s)

- **Visual**: Deep ink background (#2B2B2B). A stack of aged, yellowed envelopes fades into view, slightly rotated and scattered. One envelope lifts subtly as if breathing. The handwritten word "Unsent." appears in Caveat, #C4A882, with a soft ink-bleed glow.
- **Animation**: Envelopes fade in with staggered opacity (0.8s stagger, power2.out). The top envelope slowly floats upward (y: -12px over 6s, sine.inOut). "Unsent." writes itself via a clip-path reveal (left-to-right, 2s, power3.inOut). Subtle paper grain pulses.
- **Audio cue**: Soft vinyl crackle. Distant, muffled sounds of pen scratching on paper.

### Scene 2 — Ink Spreads (7s – 14s)

- **Visual**: Close-up metaphor — a fountain pen nib touches parchment. A drop of deep blue ink (#1E232B) spreads outward in slow motion, bleeding into organic, vein-like patterns. The ink forms the silhouette of a face in profile. Text overlay: "Every silence has a shape." in Cormorant Garamond italic, #E8D5C0.
- **Animation**: Ink drop enters from top-center (scale 0 → 1, elastic.out). Ink spread uses a clip-path circle expanding from center (0% → 100%, 4s, power2.inOut). Face silhouette resolves slowly (opacity 0 → 0.3 over 2s). Quote fades in after 5s, holds 3s.
- **Audio cue**: A single piano note, sustained with reverb. The scratch of a nib grows closer, more intimate.

### Scene 3 — Fading Memories (14s – 22s)

- **Visual**: A wall of old photographs, slightly desaturated, pinned with twine. Photos slowly lose saturation and blur — memories fading. Handwritten words appear across them one by one: "missed", "goodbye", "sorry", "I should have..." — each in Caveat, #C4A882, at different sizes and rotations. Photos gently sway.
- **Animation**: Photos enter in a 3×2 grid, each with a soft scale+fade (stagger 0.3s). Words appear on random photos with a typewriter-style character reveal (stagger 0.06s per char). Photos desaturate (CSS filter: saturate(1) → saturate(0.2)) over 5s. Sway uses rotation ±1deg, infinite yoyo.
- **Audio cue**: Soft, melancholic string quartet. Muffled voice echoes — fragments of sentences, barely audible.

### Scene 4 — Reconnection (22s – 30s)

- **Visual**: The composition brightens. The photo wall dissolves into a warm paper texture background (#E8D5C0). Two hands (silhouettes, backlit) reach toward each other across the frame. Between them, a glowing line of handwritten text forms a bridge: "It's never too late." A smartphone screen glows softly at the bottom, showing the app's compose screen.
- **Animation**: Crossfade from Scene 3 (2s dissolve). Left hand enters from left (x: -80px → 0), right hand from right (x: +80px → 0) over 2.5s, power3.out. Bridge text writes itself letter-by-letter from center outward (stagger 0.04s). Phone screen fades up from bottom, subtle pulse glow.
- **Audio cue**: Music shifts to a warm major key. A soft cello line enters. The muffled voices become clear: "I miss you."

### Scene 5 — The App as Bridge (30s – 35s)

- **Visual**: Clean, warm app interface mockup centered on screen. The compose screen of "Letters Never Sent" fills the frame — a clean text editor with parchment background. The cursor blinks gently. A line of text types itself: "Dear Mom, I never told you..." The app's wordmark logo fades in at the top. Below the editor, three feature badges: "Write Freely", "Send or Save", "No Pressure."
- **Animation**: App UI fades in (opacity 0 → 1, 0.8s). Cursor blink uses CSS animation (opacity toggle, 1s cycle). Message text types in with staggered character reveal (0.05s per char). Feature badges slide up from bottom (y: 30 → 0, stagger 0.15s, power2.out). Logo fades in from top.
- **Audio cue**: Gentle, hopeful piano melody. The scratch of pen on paper returns — but now it sounds purposeful, resolved.

### Scene 6 — Warm Ending (35s – 40s)

- **Visual**: Return to deep ink background. The full app logo — "Letters Never Sent" in Caveat, #C4A882 — centers on screen with a warm halo glow. The tagline appears below: "The words you never wrote. Finally heard." in Cormorant Garamond italic, #E8D5C0. A small, warm light (like a candle flame) flickers at the bottom. Paper grain overlay is at its richest.
- **Animation**: Logo scales in gently (scale 0.9 → 1, 2s, power3.out). Halo pulse (box-shadow intensity oscillates, 3s cycle). Tagline fades in after 1.5s delay. Candle light flickers with randomized opacity (GSAP random, 0.15s interval). Slow fade to black over final 1.5s. Paper grain holds to last frame.
- **Audio cue**: Music resolves to a single held piano chord. Pen scratch one last time, then silence. Vinyl crackle fades out at 39s.

---

## 5. Animation Requirements

- **Engine**: GSAP 3 (loaded via CDN `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **Transition style**: Slow dissolves (1.5–2s crossfade overlap). Scene N fades out while Scene N+1 fades in — 1s overlap minimum. This is NOT a fast-cut piece.
- **Entrance style**: Fade-up (opacity 0 → 1, y: 20px → 0) for most elements. Scale for hero reveals.
- **Text reveals**: 
  - Handwritten text: clip-path left-to-right reveal (simulates writing)
  - Serif quotes: soft fade-up with blur → sharp transition (simulates coming into focus)
  - Typewriter: GSAP textContent stagger for character-by-character reveals
- **Continuous animations**: Paper grain drift, photo sway (±1deg), candle flicker, cursor blink
- **Easing**: `power2.out` for entrances, `power3.inOut` for scene dissolves, `sine.inOut` for floating elements
- **Pacing philosophy**: Slow, deliberate, meditative. Every scene gives the viewer time to feel before moving on.

---

## 6. Audio Design

- **Background music**: Solo piano + string quartet, ambient/neo-classical, building from melancholic (scenes 1–3) to hopeful (scenes 4–6)
- **Sound effects**: Vinyl crackle (continuous), pen scratch (scenes 1, 2, 6), paper rustle (scene 1), muffled voices (scene 3), soft UI click (scene 5)
- **Voiceover**: None. Music + text driven. The silence between notes is as important as the notes.
- **Audio mixing**: BGM at 70% during text-heavy scenes (3, 5), at 85% during atmospheric scenes (1, 2, 4, 6)
- **Key audio moments**: 
  - 0s: Vinyl crackle starts
  - 7s: First piano note drops
  - 22s: Key change to major — emotional turning point
  - 39s: Final pen scratch, then silence

---

## 7. Technical Constraints

- Use `data-composition-id` attribute on every scene container
- Use `data-start` and `data-duration` for time control
- Use `data-track-index` for layer ordering (background = 0, content = 1, overlays = 2)
- Each scene is a `<div>` with `position: absolute; inset: 0; width: 1920px; height: 1080px`
- Scene visibility driven by `opacity` toggling (not `display: none`)
- `will-change: transform, opacity` on animated elements for GPU acceleration
- Do NOT animate `width`, `height`, `left`, or `top` — use `transform` only
- Paper texture uses SVG feTurbulence + feColorMatrix for warm-toned grain
- Clip-path reveals for typewriter/handwriting effects
- HyperFrames blocks to consider: `grain-overlay`, `vignette`, `ken-burns`

---

## 8. Content Variables

| Placeholder            | Default                        | Your Value |
|------------------------|--------------------------------|------------|
| `{{APP_NAME}}`         | `Letters Never Sent`           |            |
| `{{TAGLINE}}`          | `The words you never wrote. Finally heard.` |    |
| `{{SCENE1_WORD}}`      | `Unsent.`                      |            |
| `{{SCENE2_QUOTE}}`     | `Every silence has a shape.`   |            |
| `{{SCENE3_WORDS}}`     | `missed`, `goodbye`, `sorry`, `I should have...` | |
| `{{SCENE4_BRIDGE}}`    | `It's never too late.`         |            |
| `{{SCENE5_MESSAGE}}`   | `Dear Mom, I never told you...`|            |
| `{{INK_COLOR}}`        | `#2B2B2B`                      |            |
| `{{PAPER_COLOR}}`      | `#C4A882`                      |            |
| `{{GRAIN_OPACITY}}`    | `0.3`                          |            |

---

## 9. Reference Notes

- **Style reference**: "Call Me By Your Name" title sequence (handwritten intimacy), "The French Dispatch" (paper-textured compositions), "Her" (warm melancholy, letter-writing theme)
- **Animation reference**: Apple "Wonderlust" event opening (slow reveals, texture), "Firewatch" game trailer typography (handwritten emotional overlays)
- **Avoid**: Fast cuts, bright whites, digital/tech aesthetics, loud audio spikes — this is a quiet, human piece
