# Instagram Story Ad — Glow Skin D2C Beauty Brand

> 15-second vertical Instagram Story advertisement for a direct-to-consumer skincare brand. Elegant, soft, product-forward.

---

## 1. Video Specs

- **Duration**: 15s
- **Resolution**: 1080 × 1920 (9:16 vertical)
- **Frame rate**: 30fps
- **Orientation**: Portrait / vertical
- **Safe zones**: Keep critical content within top 420px and bottom 420px (IG Story UI elements overlay)

---

## 2. Visual System

- **Primary / Background**: `#F8E8E0` (warm blush cream — soft, clean, premium)
- **Secondary / Accent**: `#D4A574` (warm taupe gold — elegance, trust, natural luxury)
- **Text Dark**: `#3A2E2A` (deep warm brown — readable on light backgrounds)
- **Text Light**: `#FFFFFF` (white — for overlay text on product images)
- **Success / Highlight**: `#C8A882` (subtle gold shimmer)
- **Font stack**: `'Playfair Display', 'Georgia', serif` for headlines (elegant serif); `'Inter', system-ui, sans-serif` for body/captions
- **Vibe keywords**: elegant, soft, premium, natural, calming, trustworthy

---

## 3. Scene Timeline

| Scene | Time   | Visual                                                                                       | Animation                                                                |
|-------|--------|----------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| 1     | 0–4s   | Brand intro. Soft cream background (#F8E8E0). Brand name "GLOW SKIN" in Playfair Display 64px, #3A2E2A, centered. Below: tagline "Radiance, naturally." in Inter 24px, #D4A574. Delicate line ornament above and below. | Brand name fades up from y: 30, opacity 0, 0.8s ease-out. Tagline follows after 0.3s delay. Ornament lines draw in (scaleX from 0→1). Subtle shimmer sweep across the brand name at 2.5s. |
| 2     | 4–10s  | Product hero shot. Full-bleed soft-focused product image background (or gradient #F8E8E0 → #EFD5C3). Product bottle centered with drop shadow and soft glow. Text overlay top-third: "Our Best-Seller" in Inter 700 20px, #D4A574, uppercase tracked out. Product name "Vitamin C Serum" in Playfair 48px below. Key benefit callouts in small pill badges: "Brightens", "Hydrates", "Protects". | Scene crossfades in over 0.6s. Product bottle scales from 0.9→1 with gentle float. Badges stagger in from bottom, 0.2s apart. Bottle has a subtle continuous float (y: -4px, yoyo). |
| 3     | 10–14s | Review / social proof. Cream background. Centered: ⭐⭐⭐⭐⭐ (5 stars) in gold #D4A574. Below: quoted review "My skin has never felt this good" in Playfair italic 32px. Attribution "— Sarah, verified buyer" in Inter 16px. Small "4.9 ★ 2,000+ reviews" badge bottom. | Stars scale in sequentially with pop ease (back.out), 0.1s stagger. Quote text fades up. Review badge fades in last. Gentle confetti-like subtle sparkle particles in background (CSS pseudo-elements). |
| 4     | 14–15s | CTA outro. Brand gradient background (#F8E8E0 to #D4A574 diagonal). "Shop Now" button (rounded pill, white bg, #3A2E2A text) centered with a subtle glow ring. Instagram "Swipe Up" arrow indicator (↑) above button. Small brand logo bottom-center. | Button pulses gently (scale 1→1.03 yoyo). Arrow bounces (y: -8px yoyo). Entire scene fades in quickly at 14s. |

---

## 4. Animation Requirements

- **Entrance animations**: Fade-up (opacity 0, y: 30 → opacity 1, y: 0), scale-in with soft overshoot for key product elements
- **Transitions between scenes**: Slow crossfade (0.6–0.8s). Allow 0.2s overlap where both scenes are partially visible for a dreamy blend.
- **Continuous animations**: Product bottle gentle float (y: -4px, 3s cycle, sine.inOut yoyo), CTA button subtle pulse (scale 1→1.03, 2s cycle)
- **Text reveals**: Fade-up with slight y offset. Serif headlines get a touch more easing (power3.out); body text uses power2.out.
- **Pacing principle**: Slow, breathable. Each scene holds for 3–6 seconds. No rapid cuts. The rhythm should feel like a deep exhale.

---

## 5. Audio Design

- **Background music**: Soft piano or acoustic guitar instrumental, 60–75 BPM, warm and intimate
- **Sound effects**: Subtle "shimmer" on scene 1 brand reveal, soft "chime" on each star appearance (scene 3)
- **Voiceover**: Optional — soft female VO reading the tagline and review quote. If used, 0.25s audio lead before text appears.
- **Music ducking**: BGM at steady 60% throughout — no dramatic volume changes

---

## 6. Technical Constraints

- **Animation engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **HyperFrames blocks**: `shimmer-sweep` (brand name sweep, scene 1), `grain-overlay` (optional, 0.15 opacity for filmic texture)
- **HyperFrames data attributes**: `data-composition-id`, `data-start`, `data-duration`, `data-track-index`
- **Fonts**: Google Fonts — Playfair Display (400, 400 italic, 700), Inter (400, 600, 700)
- **Responsive**: Target 1080×1920. Use `clamp()` where practical.
- **Performance**: Only animate transform/opacity. Preload product image.

---

## 7. Content Variables

| Placeholder          | Default                       | Your Value |
|----------------------|-------------------------------|-------------|
| `{{BRAND_NAME}}`     | `GLOW SKIN`                   |             |
| `{{TAGLINE}}`        | `Radiance, naturally.`        |             |
| `{{PRODUCT_NAME}}`   | `Vitamin C Serum`             |             |
| `{{BENEFIT_1}}`      | `Brightens`                   |             |
| `{{BENEFIT_2}}`      | `Hydrates`                    |             |
| `{{BENEFIT_3}}`      | `Protects`                    |             |
| `{{REVIEW_QUOTE}}`   | `My skin has never felt this good` |        |
| `{{REVIEWER_NAME}}`  | `Sarah, verified buyer`       |             |
| `{{STAR_RATING}}`    | `4.9`                         |             |
| `{{REVIEW_COUNT}}`   | `2,000+ reviews`              |             |
| `{{CTA_TEXT}}`       | `Shop Now`                    |             |
| `{{PRODUCT_IMAGE}}`  | `https://placehold.co/600x800/F8E8E0/D4A574?text=Product` |  |

---

## 8. Reference Notes

- **Style reference**: Glossier, Rhode Skin, Rare Beauty Instagram Stories — soft pastel palettes, serif typography, product-as-hero
- **Animation reference**: Apple product page scroll animations for the slow-reveal pacing; Diptyque IG Stories for elegant typography treatment
- **Avoid**: Harsh transitions, neon colors, fast text animations, masculine/industrial design elements
