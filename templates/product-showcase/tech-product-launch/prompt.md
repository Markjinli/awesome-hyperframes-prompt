# Nexus AI -- Tech Product Launch Video

> A 30-second cinematic product launch for a fictional AI platform. Dark tech aesthetic with neon accents, built with the 6-dimension HyperFrames prompt formula.

---

## 1. Video Specs

- **Duration**: 30 seconds
- **Resolution**: 1920 x 1080 (16:9 landscape)
- **Frame rate**: 30 fps
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                    |
|-----------|-----------|------------------------------------------|
| Background | `#0A0A1A` | Full-canvas base, all compositions       |
| Surface    | `#12122A` | Cards, panels, glass overlays            |
| Primary    | `#6C5CE7` | Headlines, logo mark, key CTAs           |
| Secondary  | `#00D2FF` | Accent lines, icon strokes, data glow    |
| Accent     | `#FF6B6B` | Call-to-action button, critical data     |
| Text       | `#FFFFFF` | Primary body text                        |
| Muted      | `rgba(255,255,255,0.6)` | Secondary text, labels   |

### Typography

- **Headlines**: Inter Extra Bold, 800 weight, 64--96 px, `letter-spacing: -2px`
- **Subheadlines**: Inter Bold, 600 weight, 28--36 px
- **Body**: Inter Regular, 400 weight, 20--24 px, `line-height: 1.6`
- **Code / labels**: JetBrains Mono, 14--16 px, `letter-spacing: 0.5px`
- **Gradient text** (primary headlines): `linear-gradient(135deg, #6C5CE7, #00D2FF)`

### Atmosphere

Dark, futuristic, high-contrast. Subtle grid lines on the background. Soft purple/cyan glow halos behind key elements. Glassmorphism cards with `backdrop-filter: blur(12px)`. Generous negative space to let breathing room around the hero message.

---

## 3. Scene Structure

### Scene 1 -- Logo Reveal (0 s -- 5 s)

- **Visual**: Dark canvas. A single glowing dot pulses at center, then expands into the Nexus AI logo mark (a stylized hexagon + "N" monogram). The wordmark "NEXUS AI" slides up from below.
- **Animation**: Dot `scale 0 -> 1.5` with `ease: elastic.out(1,0.4)`. Logo mark fades + scales in (`opacity 0 -> 1, scale 0.6 -> 1`, 0.8 s). Wordmark slides up 40 px over 0.6 s with `ease: power3.out`. A subtle glow pulse sustains until scene end.
- **Audio cue**: Deep bass swell + high-frequency shimmer on logo reveal.

### Scene 2 -- The Problem Statement (5 s -- 11 s)

- **Visual**: Split layout. Left side (40 %) shows a dark glass card with the headline "Your Data Is Scattered" in muted red. Below it, three pain-point bullets fade in sequentially: "Silos slow decisions", "Manual workflows drain time", "Insights arrive too late". Right side (60 %) shows a stylized network diagram where disconnected nodes gradually link together.
- **Animation**: Background grid lines slowly pan upward (`y: -20 px` over 6 s, `ease: none`). Pain-point bullets use staggered fade-up (`stagger: 0.25 s`). Network nodes use GSAP `drawSVG` to animate connecting lines.
- **Audio cue**: Low, tense drone. Subtle "glitch" sfx on each bullet appearance.

### Scene 3 -- The Solution (11 s -- 20 s)

- **Visual**: Full-canvas composition. Center holds a large glassmorphism hero card (800 x 500 px, `border-radius: 24px`, `background: rgba(18,18,42,0.6)`, `backdrop-filter: blur(20px)`, `border: 1px solid rgba(108,92,231,0.3)`). Inside the card, three feature pillars animate in:
  1. **Unified Intelligence** -- icon + label + "Connect every data source" description
  2. **Real-Time Insights** -- icon + label + "Answers in milliseconds" description
  3. **Autonomous Agents** -- icon + label + "AI that takes action" description
- **Animation**: Hero card scales in (`scale 0.9 -> 1, opacity 0 -> 1`, 0.5 s). Feature pillars stagger in from below (`y: 30 -> 0, opacity 0 -> 1, stagger: 0.3 s`). Each pillar icon has a subtle continuous float (`y: -5 -> 5, repeat: -1, yoyo: true, duration: 3 s`).
- **Audio cue**: Uplifting synth arpeggio. "Pop" sfx on each pillar reveal.

### Scene 4 -- Performance Metrics (20 s -- 26 s)

- **Visual**: Data-dense composition. Three large stat cards in a horizontal row, each containing a counter number that rolls up to its target value:
  - **10x** faster decisions
  - **99.9%** uptime SLA
  - **500K+** data points / sec
  Below them, a horizontal bar chart animates in, comparing "Before Nexus AI" (short, muted bars) vs "With Nexus AI" (long, gradient bars) for three KPIs: Speed, Accuracy, Cost Savings.
- **Animation**: Counters use GSAP number roll-up (`snap: { textContent: 1 }`, 1.2 s). Bar chart bars grow from width 0 to target (`duration: 0.8 s, stagger: 0.15 s, ease: power2.out`). Stat cards fade in with a slight scale pop.
- **Audio cue**: Driving percussion. Metallic "ting" on each counter completion.

### Scene 5 -- CTA / Outro (26 s -- 30 s)

- **Visual**: Back to dark canvas. The Nexus AI logo mark returns to center at smaller scale. A bold CTA headline appears: "The Future Is Unified." Below it, a glowing CTA button reads "Join the Waitlist" with a subtle pulse animation. Footer text: "nexus.ai" in JetBrains Mono.
- **Animation**: Logo crossfades in (`opacity 0 -> 1`, 0.5 s). Headline types in character-by-character (or slides up). CTA button pulses continuously (`scale 1 -> 1.04, repeat: -1, yoyo: true`). A soft vignette darkens the canvas edges.
- **Audio cue**: Music swells to crescendo. Final bass hit on logo land.

---

## 4. Animation Requirements

- **Engine**: GSAP 3 (loaded via CDN `<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js">`)
- **Entrance style**: Fade-up + scale for hero elements, stagger for lists
- **Transition between scenes**: 0.4 s crossfade (`opacity 1 -> 0` on outgoing, `opacity 0 -> 1` on incoming with 0.2 s overlap)
- **Continuous micro-animations**: Floating icons, pulsing CTA, slowly drifting background grid
- **Easing**: Use `power2.out` for entrances, `power3.inOut` for scene transitions, `elastic.out(1,0.4)` for logo reveal

---

## 5. Audio Design

- **Background music**: Cinematic electronic / synthwave, 120 BPM, building intensity from Scene 1 to Scene 5
- **Sound effects**: Logo reveal shimmer, bullet-point "pops", counter "dings", CTA pulse
- **Voiceover**: None (music + text driven)
- **Audio mixing**: BGM at 80 % during scenes 1-3, duck to 50 % during Scene 4 data reveal for impact, swell to 90 % for outro

---

## 6. Technical Constraints

- Use `data-composition-id` attribute on every scene container
- Use `data-start` and `data-duration` for time control
- Use `data-track-index` for layer ordering (background = 0, content = 1, overlays = 2)
- Each scene is a `<div>` with `position: absolute; inset: 0; width: 1920px; height: 1080px`
- Scene visibility driven by `opacity` toggling (not `display: none`, which breaks GSAP timelines)
- `will-change: transform, opacity` on animated elements for GPU acceleration
- Do NOT animate `width`, `height`, `left`, or `top` -- use `transform` only
- HyperFrames blocks to consider: `structured-grid`, `data-chart`, `social-overlay`, `shader-transition`
