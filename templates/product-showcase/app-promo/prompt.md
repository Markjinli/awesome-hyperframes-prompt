# PulseFit -- Mobile App Promo Video

> A 15-second vertical-format promo for Instagram Reels / TikTok. Vibrant, energetic aesthetic for a fictional fitness app. Fast-paced with bold typography and gradient-driven visuals.

---

## 1. Video Specs

- **Duration**: 15 seconds
- **Resolution**: 1080 x 1920 (9:16 vertical)
- **Frame rate**: 30 fps
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`
- **Platform target**: Instagram Reels, TikTok, YouTube Shorts

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                        |
|-----------|-----------|----------------------------------------------|
| Background | `#0F0F1A` | Deep base for gradient overlays              |
| Primary    | `#FF6B35` | Orange -- headlines, CTAs, energy accents    |
| Secondary  | `#A855F7` | Purple -- gradient partner, icon fills       |
| Gradient   | `135deg, #FF6B35 0%, #A855F7 100%` | Hero text, buttons, decorative blobs |
| Accent     | `#00F5D4` | Neon teal -- counters, highlights, badges    |
| Text       | `#FFFFFF` | Primary text on dark backgrounds             |
| Dark Text  | `#1A1A2E` | Text on light/white surfaces (rare)          |
| Overlay    | `rgba(15,15,26,0.7)` | Semi-transparent backdrop for text readability |

### Typography

- **Headlines**: Outfit Bold, 800 weight, 56--72 px, `letter-spacing: -1.5px`
- **Subheadlines**: Outfit Semi-Bold, 600 weight, 28--36 px
- **Body**: Outfit Regular, 400 weight, 20--24 px, `line-height: 1.5`
- **Stats / Numbers**: Outfit Extra Bold, 900 weight, 64--80 px, `letter-spacing: -2px`
- **Captions**: Outfit Medium, 500 weight, 16--18 px

### Atmosphere

High-energy, youthful, aspirational. Dark backgrounds with vivid orange-to-purple gradient splashes. Bold, oversized typography that fills the vertical frame. Fast cuts. Glowing elements. The aesthetic should feel like a premium fitness brand -- think Nike Training Club meets a music festival aftermovie. Large emoji-style icons used as graphic accents. Subtle grain texture overlay.

---

## 3. Scene Structure

### Scene 1 -- Hook + Brand (0 s -- 4 s)

- **Visual**: Full vertical canvas. A large gradient blob (orange-purple) pulses at center as background. Center text stacks:
  - Top: Small "INTRODUCING" label in Outfit Medium, teal color, `letter-spacing: 4px`
  - Middle: "PULSEFIT" in 80 px Outfit Extra Bold, gradient text (`#FF6B35 -> #A855F7`), with a subtle text-shadow glow
  - Bottom: "Your AI Fitness Coach" in 28 px Outfit Semi-Bold, white
  Below text, a row of three fitness icons (dumbbell, heart-rate, flame) bounce in sequence.
- **Animation**: Blob pulses (`scale 0.9 -> 1.1`, 2 s loop). "INTRODUCING" fades in at 0.1 s. "PULSEFIT" scales in from 0.7 with `ease: back.out(1.7)` at 0.3 s, then has a continuous subtle float (`y: -3 -> 3`). Tagline slides up at 0.8 s. Icons stagger-bounce (`y: -20 -> 0, stagger: 0.12 s, ease: bounce.out`).
- **Audio cue**: Punchy beat drop at 0 s. Bass hit on "PULSEFIT" reveal.

### Scene 2 -- Features + Social Proof (4 s -- 10 s)

- **Visual**: Fast-cut sequence within a single composition. Background is a dark gradient with animated orange/purple accent lines sweeping across. Content is three "feature bursts" that appear and disappear in rapid succession:
  - **Burst 1 (4 s -- 6 s)**: Large phone mockup centered, showing the PulseFit workout screen. Overlay text: "200+ WORKOUTS" in 56 px Outfit Extra Bold, orange. Sub-label: "From HIIT to Yoga" in 20 px.
  - **Burst 2 (6 s -- 8 s)**: Phone mockup shifts to nutrition tracking screen. Overlay text: "MEAL PLANS BY AI" in 56 px, purple gradient. Sub-label: "Personalized. Precise. Delicious." in 20 px.
  - **Burst 3 (8 s -- 10 s)**: Phone mockup shifts to community/leaderboard screen. Overlay text: "500K+ COMMUNITY" in 64 px, teal. Three user avatar circles pop in below.
- **Animation**: Each burst: phone slides in from bottom (`y: 80 -> 0, opacity 0 -> 1`, 0.4 s), overlay text scales in (`scale 0.8 -> 1.05 -> 1`, 0.5 s, `ease: back.out(1.4)`), then everything exits up (`y: 0 -> -60, opacity 1 -> 0`, 0.3 s). Accent lines sweep across the background continuously (`x: -100% -> 200%`, 3 s loops).
- **Audio cue**: Fast hi-hat rhythm. "Swoosh" on each burst transition. "Pop" on each stat reveal.

### Scene 3 -- CTA + Download (10 s -- 15 s)

- **Visual**: High-impact closing composition. Background: full-canvas orange-to-purple gradient (`linear-gradient(135deg, #FF6B35, #A855F7)`). Center content:
  - Top: PulseFit logo mark (stylized heartbeat + "P" monogram) in white
  - Main headline: "READY TO MOVE?" in 72 px Outfit Extra Bold, white, with a subtle dark text-shadow for depth
  - Subheadline: "Download free on iOS & Android" in 24 px Outfit Regular, white at 90 % opacity
  - Two app store badge buttons side by side: App Store and Google Play (white outlined pills)
  - Bottom: Five-star rating row: "4.9" in large numbers with star icons
- **Animation**: Gradient background subtly shifts (`background-position` animation, 5 s loop). Logo bounces in (`scale 0 -> 1.1 -> 1, ease: elastic.out(1,0.3)`, 0.6 s). Headline types up character by character (`stagger: 0.04 s`, 0.8 s total). App store badges slide up from bottom (`y: 40 -> 0, opacity 0 -> 1, stagger: 0.15 s`). Rating stars fill in left-to-right (`clip-path` animation, 0.6 s). Final CTA text "DOWNLOAD NOW" at the very bottom pulses.
- **Audio cue**: Music peaks. Final beat drop at 10 s. Satisfying "ding" on rating reveal. Music fades out from 14 s -- 15 s.

---

## 4. Animation Requirements

- **Engine**: GSAP 3 (CDN) for all sequenced animations
- **Entrance style**: Bouncy/elastic for key moments, fast slides for content bursts, stagger for icons
- **Transition between bursts**: Slide-up exit + slide-up entrance (conveyor-belt feel), 0.3 s each
- **Continuous motion**: Background gradient shift, blob pulse, accent line sweeps, CTA pulse
- **Text animation**: Scale-pop for headlines, character-by-character for final CTA, fade-up for body
- **Easing**: `back.out(1.7)` for logo/headline reveals, `power4.out` for fast content bursts, `elastic.out(1,0.3)` for bouncy icons

---

## 5. Audio Design

- **Background music**: High-energy electronic / future bass, 128--140 BPM. Punchy kick on every beat. Build-up from Scene 1, high energy through Scene 2, peak at Scene 3.
- **Sound effects**: Beat drop at open, transition whooshes (0.2 s), stat "pops" (0.1 s), icon bounce "boings", rating star "dings", final impact hit
- **Voiceover**: None (music + text driven, standard for short-form vertical video)
- **Audio mixing**: BGM front and center at 85 %. SFX layered clearly on top. Quick fade-out over final 1 s.

---

## 6. Technical Constraints

- Use `data-composition-id` for each scene (`hook`, `features`, `cta`)
- Use `data-start` and `data-duration` for timing
- Use `data-track-index` for layer ordering (background effects = 0, content = 1, overlays = 2)
- Vertical canvas: `width: 1080px; height: 1920px`
- Each scene is a full-canvas absolutely-positioned `<div>`
- Phone mockups built with CSS (rounded rectangle + notch + screen content area) -- no external images required
- All text must be large enough to read on mobile (min 18 px at 1080 px wide canvas)
- Safe zone: Keep critical content within 80 px of horizontal edges and 120 px of vertical edges (accounting for platform UI overlays)
- HyperFrames blocks to consider: `social-overlay`, `phone-mockup`, `gradient-background`
