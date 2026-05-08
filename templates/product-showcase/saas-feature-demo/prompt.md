# FlowBoard -- SaaS Feature Demo Video

> A 20-second feature walkthrough for a fictional project management SaaS. Clean, minimal aesthetic with blue accents. Product screenshots and UI animations take center stage.

---

## 1. Video Specs

- **Duration**: 20 seconds
- **Resolution**: 1920 x 1080 (16:9 landscape)
- **Frame rate**: 30 fps
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                      |
|-----------|-----------|--------------------------------------------|
| Background | `#F8FAFC` | Full-canvas base, light and airy           |
| Surface    | `#FFFFFF` | Cards, panels, UI mockup containers        |
| Primary    | `#3B82F6` | Headlines, buttons, active nav, chart bars |
| Secondary  | `#6366F1` | Gradient accents, hover states, icon fills |
| Accent     | `#10B981` | Success badges, "done" checkmarks, growth indicators |
| Text       | `#0F172A` | Primary body text (near-black, not pure)   |
| Muted      | `#64748B` | Secondary text, labels, timestamps         |
| Border     | `#E2E8F0` | Card borders, dividers, subtle separators  |

### Typography

- **Headlines**: Switzer Bold, 700 weight, 48--64 px, `letter-spacing: -1px`
- **Subheadlines**: Inter Semi-Bold, 600 weight, 24--32 px
- **Body**: Inter Regular, 400 weight, 18--20 px, `line-height: 1.7`
- **Labels / badges**: Inter Medium, 500 weight, 13--15 px, uppercase tracking `letter-spacing: 0.5px`
- **Data / numbers**: Tabular figures via `font-variant-numeric: tabular-nums`

### Atmosphere

Clean, professional, trustworthy. Generous white space. Soft shadows (`box-shadow: 0 1px 3px rgba(0,0,0,0.06), 0 1px 2px rgba(0,0,0,0.04)`) on cards. Subtle blue gradient washes in the background. Product UI screenshots are the hero -- let the interface sell itself. Rounded corners (12 px on cards, 8 px on buttons). The overall feel should evoke Linear, Notion, and Stripe design sensibilities.

---

## 3. Scene Structure

### Scene 1 -- Hero + Value Prop (0 s -- 5 s)

- **Visual**: Split composition. Left half (45 %) has the FlowBoard logo top-left, a bold headline "Projects That Flow" in 64 px Switzer Bold, a subheading "The project management tool that adapts to your team, not the other way around" in 20 px Inter, and a blue "Try FlowBoard Free" CTA button. Right half (55 %) shows a large product screenshot: the FlowBoard kanban board with colorful cards in columns.
- **Animation**: Logo fades in at 0.2 s. Headline slides up 30 px over 0.6 s (`ease: power3.out`). Subheading fades in at 0.6 s. Screenshot slides in from right 60 px over 0.7 s with a slight scale (`0.95 -> 1`). CTA button fades + scales in at 0.8 s.
- **Audio cue**: Bright, modern synth pad. Subtle "whoosh" on screenshot entrance.

### Scene 2 -- Feature Highlights (5 s -- 12 s)

- **Visual**: Three horizontal feature cards arranged in a row, each 520 x 320 px. Card contents:
  1. **Kanban & Timeline** -- "Visualize work your way" with a mini board illustration inside
  2. **AI Sprint Planning** -- "Auto-assign tasks with AI" with sparkle icon
  3. **Real-Time Collab** -- "Edit together, see changes live" with cursor avatars
  Each card has a light blue gradient accent strip at the top. Below the cards, a subtle dot indicator shows current focus (card 1 highlighted at 5 s, card 2 at 7.5 s, card 3 at 10 s).
- **Animation**: Cards stagger in from below (`y: 40 -> 0, opacity 0 -> 1, stagger: 0.2 s, ease: power2.out`). Each card gets a brief blue glow on its accent strip when focused (`box-shadow` pulse, 0.4 s). Mini illustrations within cards animate on focus (e.g., board columns shuffle, sparkle rotates, avatars shift).
- **Audio cue**: Gentle arpeggio. Soft click on each card focus change.

### Scene 3 -- Data Chart / Performance (12 s -- 17 s)

- **Visual**: Dashboard-style composition. Top center: headline "Teams Using FlowBoard Ship 40% Faster" in 48 px Switzer Bold. Below, a split data area:
  - Left: A donut chart showing "On-Time Delivery" at 94 % (animated from 0)
  - Center: A vertical bar chart comparing "Industry Avg" (muted bars, ~60-70 % heights) vs "FlowBoard Teams" (blue gradient bars, ~90-95 % heights) across 4 quarters
  - Right: A large KPI number "2.3x" that counts up, with label "Productivity Boost"
- **Animation**: Headline fades in. Donut chart draws its arc (`stroke-dashoffset` animation, 1.5 s). Bar chart bars grow from height 0 (`duration: 0.6 s, stagger: 0.12 s`). KPI number rolls up from 0 to 2.3 (`snap: 0.1`, 1.8 s). Grid lines and axis labels fade in before bars.
- **Audio cue**: Data-driven percussion. Rising pitch sweep. "Ding" on KPI completion.

### Scene 4 -- CTA / Outro (17 s -- 20 s)

- **Visual**: Centered composition. FlowBoard logo returns to center-top (smaller). Bold headline "Start Flowing Today" in 56 px Switzer Bold with a blue gradient underline decoration. Below: CTA button "Get Started Free" with a small "No credit card required" caption. Bottom: three trust badges in a row -- "SOC 2 Certified", "GDPR Compliant", "99.9% Uptime SLA".
- **Animation**: Background shifts to a subtle blue gradient wash. Logo fades in. Headline slides up 20 px over 0.5 s. CTA button scales in (`scale 0.9 -> 1, ease: back.out(1.4)`). Trust badges stagger-fade-in (`stagger: 0.15 s`). CTA button has continuous subtle pulse (`scale 1 -> 1.03, repeat: -1, yoyo: true`).
- **Audio cue**: Music resolves to major chord. Warm pad sustain. Subtle "click" sound on final button appearance.

---

## 4. Animation Requirements

- **Engine**: GSAP 3 (CDN) for complex sequences; CSS `@keyframes` for simple loops
- **Entrance style**: Fade-up (primary), slide-from-right (screenshots), scale-pop (CTAs)
- **Scene transitions**: 0.3 s crossfade with slight `filter: blur(4px)` on outgoing scene
- **Chart animations**: SVG `stroke-dashoffset` for donut arcs, GSAP `fromTo` on bar `height` / `scaleY`
- **Micro-interactions**: Button hover states (even though it's video, add a subtle pulse loop to indicate interactivity), card accent glows
- **Easing**: `power3.out` for hero entrances, `power2.out` for stagger groups, `back.out(1.4)` for CTA buttons

---

## 5. Audio Design

- **Background music**: Upbeat, modern corporate synth -- think Stripe Press or Notion product videos. 110 BPM. Consistent energy throughout.
- **Sound effects**: Scene transition whooshes (0.15 s), card focus clicks, chart completion ding, CTA pulse
- **Voiceover**: None (text + UI driven, matching SaaS demo conventions)
- **Audio mixing**: BGM steady at 75 % throughout. SFX layered clearly on top.

---

## 6. Technical Constraints

- Use `data-composition-id` for each scene (`hero`, `features`, `data-chart`, `outro`)
- Use `data-start` / `data-duration` for precise timing
- Use `data-track-index` for z-ordering (background = 0, UI content = 1, overlays/badges = 2)
- Product screenshots should be embedded as `<img>` or `<div>` with CSS-drawn UI mockups
- Chart drawn with inline SVG for crisp rendering and easy animation hooks
- Stat numbers use `font-variant-numeric: tabular-nums` to prevent layout shift during count-up
- All animated elements get `will-change: transform, opacity`
- HyperFrames blocks to consider: `data-chart`, `structured-grid`, `hero-with-screenshot`
