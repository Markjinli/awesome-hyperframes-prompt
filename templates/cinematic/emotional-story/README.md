# Emotional Story — "Letters Never Sent"

> 40-second emotional brand short for a handwriting/letter app. Poetic, nostalgic, deeply human. Six slow-burning scenes at 24fps with paper textures, handwritten typography, and warm ink-and-parchment color grading.

---

## Use Cases

- Brand documentary-style short films
- Emotional connection advertising campaigns
- Kickstarter / crowdfunding story videos
- App or product that addresses personal/emotional needs
- Nonprofit cause awareness videos
- "About Us" brand heritage pieces

---

## Key Techniques

| Technique | Where | Why |
|-----------|-------|-----|
| **Paper grain overlay** | Global, all scenes | SVG `feTurbulence` + `feColorMatrix` creates warm-toned paper texture -- analog, tactile feel |
| **Handwritten font (Caveat)** | Letter excerpts, emotional phrases | Script font at 48-96px simulates real handwriting on aged paper |
| **Clip-path text reveal** | Scene 1, Scene 3 | Left-to-right clip-path reveals simulate writing/drawing -- more organic than fade-in |
| **Ink bleed glow** | Scene 2 | `text-shadow` with warm spread creates ink-on-paper bleeding effect |
| **Ken Burns photo drift** | Scene 3 | Photos slowly scale and pan with `sine.inOut` -- nostalgic documentary feel |
| **Desaturation fade** | Scene 3 | CSS `filter: saturate(1 -> 0.2)` over 5s -- memories fading visual metaphor |
| **Slow crossfades** | All scene transitions | 1.5-2s overlapping dissolves -- meditative pace, never rushed |
| **Vignette** | All scenes | `radial-gradient` darkening edges for cinematic depth |
| **Candle flicker** | Scene 6 | GSAP randomized `opacity` at 0.15s intervals -- organic warmth |
| **24fps film cadence** | Global | Lower frame rate for cinematic, non-video feel |

---

## Customization

1. Replace `"Letters Never Sent"` with your app/brand name
2. Update the tagline `"The words you never wrote. Finally heard."`
3. Swap all scene text (Unsent, quotes, bridge text, sample message) to fit your narrative
4. Adjust colors: `#2B2B2B` (deep ink), `#C4A882` (warm paper), `#E8D5C0` (parchment) -> your palette
5. Modify `{{GRAIN_OPACITY}}` to control texture intensity
6. Replace photo grid references with your own archival imagery

---

## Template Metadata

- **Category**: Cinematic
- **Subcategory**: Emotional Story / Brand Short
- **Format**: 16:9 Horizontal (1920x1080)
- **Duration**: 40s (6 scenes)
- **Frame Rate**: 24fps (film cadence)
- **Difficulty**: Advanced -- requires careful pacing and emotional arc design
- **Animation Engine**: GSAP 3
- **Fonts**: Caveat + Cormorant Garamond + Inter (Google Fonts)
- **Blocks suggested**: `grain-overlay`, `vignette`, `ken-burns`
