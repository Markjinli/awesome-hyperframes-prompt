# Social Media Ad — CoinFlow Fintech App

> 30-second horizontal social media advertisement. Dynamic, data-driven, trust-building fintech promo.

---

## 1. Video Specs

- **Duration**: 30s
- **Resolution**: 1920 × 1080 (16:9 horizontal)
- **Frame rate**: 30fps
- **Orientation**: Landscape / horizontal
- **Platform targets**: YouTube pre-roll, Facebook/Instagram Feed video, LinkedIn video ad

---

## 2. Visual System

- **Primary / Brand**: `#6C3CE1` (electric violet — trust, innovation, fintech energy)
- **Secondary / Accent**: `#00D4AA` (mint green — growth, money, positivity)
- **Background Dark**: `#0D0D1A` (near-black navy — premium tech, high contrast)
- **Background Light**: `#F5F3FF` (soft lavender-white — clean data sections)
- **Text Primary**: `#FFFFFF` (white on dark), `#0D0D1A` (dark on light)
- **Data Highlight**: `#FFB830` (warm amber — for key numbers, ratings, trust badges)
- **Font stack**: `'Space Grotesk', 'Inter', system-ui, sans-serif` — geometric authority for finance
- **Vibe keywords**: dynamic, trustworthy, innovative, premium, data-driven, confident

---

## 4 Scene TimeLine (30s)

| Scene | Time    | Visual                                                                                                    | Animation                                                                           |
|-------|---------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| 1     | 0–6s    | **The Hook**. Dark background (#0D0D1A). Large animated number counter (users, e.g., "2,438,921") rolling up from 0 in #00D4AA, 96px Space Grotesk Bold. Below: "People already trust CoinFlow" in white 28px. Subtle grid pattern background. | Counter animates from 0→2,438,921 over 1.8s (power2.out). Text below fades up. Grid lines draw in subtly. Subtle glow pulse on the final number. |
| 2     | 6–16s   | **The Problem & Solution**. Split into two sub-scenes: (a) 6–11s: Dark card slides in showing pain points — "Hidden fees", "Slow transfers", "Confusing UI" each with a red ✕ icon. (b) 11–16s: Card flips/transforms to show CoinFlow solutions — "Zero hidden fees ✓", "Instant transfers ✓", "Beautiful design ✓" in #00D4AA. | Pain points stagger in from left with red tint. At 11s, a sleek horizontal wipe transitions to solutions. Each solution slides in from bottom with green checkmark scale-pop. |
| 3     | 16–24s  | **Social Proof & Trust**. Three trust elements arranged horizontally: (left) ★ 4.8 rating card with App Store / Google Play badges, (center) "Featured in" logos (TechCrunch, Forbes, etc.), (right) Security badge "Bank-Grade Encryption". All on light background (#F5F3FF) with subtle card shadows. | Cards scale in with stagger (0.15s apart). Star rating fills left-to-right. Trust badge icons glow briefly on entrance. Featured logos fade in row by row. |
| 4     | 24–30s  | **CTA Finale**. Bold gradient background (#6C3CE1 → #00D4AA diagonal). Large heading "Start your financial journey" (56px, white, bold). Subtext "Join 2M+ users. Free to start." Below: prominent CTA button "Get CoinFlow Free" (white bg pill, #6C3CE1 text, with glow ring). Small footer: App Store + Google Play download badges. | Heading scales in from 0.85 with elastic ease. Button pulses (scale 1→1.04, yoyo, sine.inOut). Download badges slide up. Entire composition has a subtle floating motion. Fade to brand logo at 29.5s. |

---

## 5. Animation Requirements

- **Entrance animations**: Counter number roll (GSAP textContent snap), scale+fade combos, slide-in from edges (30–60px offset)
- **Transition between scenes**: Quick horizontal wipe (0.4s) between scenes 1→2 and 2→3. Scene 3→4 uses a diagonal gradient sweep (0.5s) for energy lift.
- **Continuous animations**: CTA pulse loop, subtle background gradient shift (hue-rotate via CSS filter animation), floating trust badges (y: ±6px, 3s cycle)
- **Data animations**: Counter roll-up (GSAP with snap), progress bars filling, star ratings filling left-to-right
- **Text reveals**: Staggered word reveals for key benefits, fade-up for descriptive text
- **Pacing**: Scene 1 fast energy grab → Scene 2 steady explanatory → Scene 3 building trust → Scene 4 energetic climax

---

## 6. Audio Design

- **Background music**: Modern tech-house or upbeat electronic, 110–125 BPM, confident and driving. Steady energy throughout.
- **Sound effects**:
  - Counter roll-up: ascending digital tick sounds (0–2s of scene 1)
  - Pain point reveals: low "buzz" / error tone (subtle, 0.1s)
  - Solution reveals: satisfying "ding" on each checkmark
  - Trust badges: soft "shimmer" on appearance
  - CTA: strong "impact" hit at 24s beat drop
- **Voiceover**: Optional male VO, energetic and trustworthy tone. If used, sync text reveals to VO pacing.
- **Music ducking**: BGM at 100% during transitions, dip to 70% during voiceover or text-heavy moments.

---

## 7. Technical Constraints

- **Animation engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **HyperFrames blocks**: `apple-money-count` (scene 1 counter roll-up), `data-chart` (optional, scene 3), `logo-outro` (scene 4 end)
- **HyperFrames data attributes**: `data-composition-id`, `data-start`, `data-duration`, `data-track-index`
- **Fonts**: Google Fonts — Space Grotesk (400, 500, 700), Inter (400, 600)
- **Responsive**: Target 1920×1080. Use `clamp()` for scalable typography.
- **Performance**: Animate transform/opacity only. Avoid animating box-shadow (use pseudo-element opacity instead). Preload brand logo.

---

## 8. Content Variables

| Placeholder            | Default                          | Your Value |
|------------------------|----------------------------------|-------------|
| `{{APP_NAME}}`         | `CoinFlow`                       |             |
| `{{USER_COUNT}}`       | `2,438,921`                      |             |
| `{{USER_COUNT_SHORT}}` | `2M+`                           |             |
| `{{PAIN_POINT_1}}`     | `Hidden fees`                    |             |
| `{{PAIN_POINT_2}}`     | `Slow transfers`                 |             |
| `{{PAIN_POINT_3}}`     | `Confusing UI`                   |             |
| `{{SOLUTION_1}}`       | `Zero hidden fees`               |             |
| `{{SOLUTION_2}}`       | `Instant transfers`              |             |
| `{{SOLUTION_3}}`       | `Beautiful design`               |             |
| `{{RATING}}`           | `4.8`                            |             |
| `{{FEATURE_1}}`        | `TechCrunch`                     |             |
| `{{FEATURE_2}}`        | `Forbes`                         |             |
| `{{HEADLINE}}`         | `Start your financial journey`   |             |
| `{{CTA_TEXT}}`         | `Get CoinFlow Free`              |             |
| `{{APP_LOGO}}`         | `https://placehold.co/200x200/6C3CE1/white?text=CF` |  |

---

## 9. Reference Notes

- **Style reference**: Robinhood product launch videos, Revolut ads, Stripe's data-visualization aesthetic — clean data, bold numbers, confident motion
- **Animation reference**: Apple keynote number roll-ups for counter polish; Stripe Sessions keynotes for data transition choreography
- **Avoid**: Cluttered layouts (max 3 focal points per scene), childish animations (no bouncy cartoon eases), low-contrast text (finance needs clarity)
