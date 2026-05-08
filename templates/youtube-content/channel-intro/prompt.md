# YouTube Channel Intro — "DeepTech"

> 15-second high-energy channel intro for a tech review channel. Bold, fast, punchy. Built with the 6-dimension HyperFrames prompt formula.

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
| Brand Red  | `#FF0050` | Hero accents, logo mark, key text, CTA bursts   |
| Deep Black | `#141414` | Backgrounds, negative space, contrast anchor    |
| Clean White| `#FFFFFF` | Primary text, icon strokes, product outlines    |
| Dark Gray  | `#2A2A2A` | Card surfaces, secondary backgrounds            |
| Muted Red  | `#330010` | Subtle glow halos, shadow accents               |

### Typography

- **Primary (Headlines)**: Inter Extra Bold, 800 weight, 64–120 px, `letter-spacing: -2px`
- **Secondary (Labels)**: Inter Semi Bold, 600 weight, 20–28 px, `letter-spacing: 1px`, uppercase
- **Tertiary (Body)**: Inter Regular, 400 weight, 18–24 px
- **Channel Name Lockup**: Custom lockup — "DEEP" in Inter Black 900, "TECH" in Inter Light 300

### Atmosphere Keywords

High-energy, premium, authoritative, kinetic, punchy, MKBHD-clean, Linus-energy, confident, slick, modern, reviewer-cred

### Graphic Language
- Bold geometric accents — diagonal slashes, sharp corners, split-color backgrounds
- Glow halos behind hero text (box-shadow + radial-gradient on pseudo-elements)
- Subtle grid pattern on dark backgrounds (rgba(255,255,255,0.03) lines, 80px spacing)
- Product silhouettes with rim lighting

---

## 3. Brand Assets

- **Channel Name**: DeepTech
- **Tagline**: "Deeper reviews. Smarter choices."
- **Upload Schedule**: Every Tuesday & Friday
- **Content Pillars**: Smartphone reviews, laptop deep-dives, PC builds, gadget comparisons
- **Logo Mark**: A stylized "D" with a circuit-board accent line cutting through the letterform — bold geometric mark in #FF0050

---

## 4. Scene Timeline

### Scene 1 — The Hook: Product Montage (0s – 6s)

- **Visual**: Rapid-fire montage of 6 tech product shots alternating between clean product-on-white and dark moody tabletop photography. Quick cuts synced to beat. Products: smartphone, laptop, headphones, smartwatch, GPU, mechanical keyboard. Each product appears with a subtle scale burst and diagonal accent line.
- **Layout**: Products appear in rapid sequence, each held for ~0.8s. Position alternates — center, left-third, right-third — creating visual rhythm. Each product has a thin diagonal #FF0050 accent line (2px, 45deg) that slashes across frame.
- **Animation**: Each product enters with scale(0.85) + opacity 0 → scale(1.02) → scale(1) in 0.5s (expo.out). Accent lines draw from length 0% → 100% in 0.3s. Between products, a 2-frame flash (white frame at 10% opacity) creates edit energy. Background alternates #141414 / #FFFFFF every other product.
- **Audio cue**: Punchy electronic beat at 128 BPM. Bass kick on each product cut. Rising synth swell through the sequence.

### Scene 2 — Identity Reveal (6s – 11s)

- **Visual**: Deep black background (#141414). The DeepTech logo mark explodes into center — a bold "D" glyph with circuit-board line accent. The channel name "DEEPTECH" scales in beneath it with letter-by-letter stagger. A glowing red underline streaks across. Subtitle "Deeper reviews. Smarter choices." fades up.
- **Animation (GSAP stagger + scale)**:
  - Logo mark: scale 0 → 1.15 → 1 with elastic.out(1, 0.4) over 0.8s
  - "DEEPTECH" letters: Each letter scales from 0 + opacity 0 → 1 + opacity 1 with 0.04s stagger (GSAP SplitText). Letters overshoot slightly for punch.
  - Red underline: Draws left-to-right (scaleX 0 → 1, transform-origin: left) over 1s, power3.inOut, starting 0.4s after first letter
  - Subtitle: Fades up from below (y: 20px → 0, opacity 0 → 1) over 0.6s, starting 0.2s after underline completes
  - Continuous: Logo mark pulses scale(1 → 1.04, 2s cycle, yoyo, sine.inOut). Red glow halo around mark oscillates in intensity.
- **Audio cue**: Beat drops hard at 6s. Sub-bass rumble. A metallic "clang" on logo impact. Synth arpeggio builds behind the letter stagger.

### Scene 3 — CTA + Schedule Lockup (11s – 15s)

- **Visual**: Split composition. Left side (60%) — large bold text "EVERY TUESDAY & FRIDAY" in Inter Extra Bold, #FFFFFF on #141414. Below: social proof line "Join 500K+ tech enthusiasts." Right side (40%) — a vertical stack of platform badges (YouTube, Instagram, TikTok) with the channel handle @deeptech, each in a sleek dark card (#2A2A2A) with red accent border.
- **Animation**: 
  - Text line enters with a horizontal wipe + scale burst (clip-path from left, 0.6s, power3.inOut)
  - "500K+" number counts up from 0 over 1.2s (GSAP snap)
  - Platform badges slide in from right sequentially (stagger 0.2s, expo.out)
  - A final accent slash (#FF0050) sweeps diagonally across the entire frame (opacity 0 → 0.8 → 0, 0.4s) as a punctuation beat at 14s
- **Audio cue**: Music peaks. Final beat hit at 14s on the accent slash. Quick fade-out over last 0.5s.

---

## 5. Animation Requirements

- **Engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **Entrance style**: Scale burst (0 → 1.15 → 1), slide-in from edges (80px offsets), horizontal wipes
- **Transition between scenes**: Hard cuts (Scene 1) + fast crossfade (Scene 1→2, 0.3s) + crossfade (Scene 2→3, 0.4s)
- **Continuous animations**: Logo pulse, glow oscillation, background grid slow pan
- **Text reveals**: GSAP SplitText stagger (character-level, 0.04s stagger) for channel name. Horizontal clip-path wipe for headlines.
- **Easing**: `expo.out` for entrances, `elastic.out(1, 0.4)` for logo reveal, `power3.inOut` for accent lines
- **Timing philosophy**: Fast, tight, zero dead air. Every frame has motion. 128 BPM beat drives the cut timing.

---

## 6. Audio Design

- **Background music**: High-energy electronic / tech-house, 128 BPM, driving bass, crisp percussion
- **Sound effects**: Bass kicks on cuts (scene 1), metallic impact on logo (scene 2), digital sweep on text reveals, accent hit on final slash
- **Voiceover**: None. Music + text driven.
- **Audio mixing**: BGM at 85% throughout. SFX punch through at 100% on key moments (logo, accent slashes). Final 0.5s: quick music fade-out.
- **Beat mapping**: Cuts in Scene 1 exactly on the kick drum. Letter stagger in Scene 2 synced to snare pattern.

---

## 7. Technical Constraints

- Use `data-composition-id`, `data-start`, `data-duration`, `data-track-index` on every scene
- Each scene: `<div>` with `position: absolute; inset: 0; width: 1920px; height: 1080px`
- Scene visibility: `opacity` only — never `display: none`
- `will-change: transform, opacity` on animated elements
- Animate `transform` and `opacity` only — no layout properties
- GSAP SplitText for character-level stagger (include SplitText plugin or use manual span wrapping)
- HyperFrames blocks to consider: `product-showcase`, `logo-reveal`, `social-overlay`

---

## 8. Content Variables

| Placeholder            | Default                        | Your Value |
|------------------------|--------------------------------|------------|
| `{{CHANNEL_NAME}}`     | `DeepTech`                     |            |
| `{{TAGLINE}}`          | `Deeper reviews. Smarter choices.` |        |
| `{{SCHEDULE}}`         | `EVERY TUESDAY & FRIDAY`       |            |
| `{{SUB_COUNT}}`        | `500K+`                        |            |
| `{{HANDLE}}`           | `@deeptech`                    |            |
| `{{PRODUCT_1}}`        | Smartphone render / photo      |            |
| `{{PRODUCT_2}}`        | Laptop render / photo          |            |
| `{{PRODUCT_3}}`        | Headphones render / photo      |            |
| `{{PRODUCT_4}}`        | Smartwatch render / photo      |            |
| `{{PRODUCT_5}}`        | GPU render / photo             |            |
| `{{PRODUCT_6}}`        | Keyboard render / photo        |            |
| `{{BRAND_RED}}`        | `#FF0050`                      |            |

---

## 9. Reference Notes

- **Style reference**: MKBHD channel intro (clean product photography, bold cuts), Linus Tech Tips (high energy, personality-driven pace), Mrwhosetheboss (cinematic product reveals)
- **Animation reference**: Apple event "Fast Cut" sections, Nike product launch edits (beat-synced cuts, scale bursts)
- **Avoid**: Slow fades (Scene 1 is hard cuts), low-contrast text, cluttered frames, overlong holds — if nothing moves for 0.5s, it's too long
