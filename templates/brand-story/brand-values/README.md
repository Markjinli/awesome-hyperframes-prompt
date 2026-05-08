# Brand Values Manifesto -- ReForm

## Effect Overview

A 30-second brand values manifesto for a sustainable fashion brand. Five core values are presented with bold single-word reveals, split-screen comparisons, supply-chain animations, and warm organic blob accents. Clean, purpose-driven aesthetic with earth tones and generous negative space communicates authenticity and modern minimalism.

## Use Cases

- **Brand ethos video** for homepage hero sections or About pages
- **Sustainability report** visual summary for investor or stakeholder presentations
- **Recruitment / culture** highlighting company values to attract mission-aligned talent
- **Social media** brand campaign (cut into 5 individual value shorts)
- **Retail / pop-up** in-store looping display

## Key Techniques Illustrated

| Technique | Where Used | How It Works |
|-----------|-----------|--------------|
| **Split-screen comparison** | Scenes 1, 3 | Two flex children share a container; one collapses via `flex` tween to reveal the other full-screen |
| **Organic blob shapes** | All scenes | CSS asymmetric `border-radius` values (`60% 40% 70% 30% / 50% 40% 60% 50%`) create soft decorative shapes |
| **Supply chain animation** | Scene 2 | Sequential `classList.add('lit')` via GSAP `call()` at timed intervals, lighting nodes and connectors along a path |
| **Grid wave reveal** | Scene 4 | Portraits populate in a wave pattern using GSAP `stagger` with `grid: [4, 4]` option, scanning top-to-bottom |
| **Garment degradation** | Scene 3 | `.torn` class toggled via GSAP `call()` applies a pseudo-element with diagonal stripe pattern to simulate wear |
| **Blob breathing** | Scene 4 | Continuous `scale` yoyo tween on blob element creates organic "living" background motion |
| **Back.out easing** | Value reveals | `ease: 'back.out(1.3-1.5)'` on word animations creates a satisfying overshoot-and-settle effect |
| **Pill stagger** | Scene 5 | Stat pills appear sequentially (stagger 0.35s) with clean slide-up fade-in |

## Color Palette

| Role | Hex | Usage |
|------|-----|-------|
| Forest Green | `#2D4A22` | Value words, primary headlines |
| Sage Green | `#8CB369` | Accents, connector lines, stat text, "re" in logo |
| Warm White | `#FBF7F4` | Background, right-side split screen, quality card |
| Dark Pine | `#1A3A14` | Body text, "form" in logo, UI labels |
| Divider | `rgba(140,179,105,0.3)` | 2px thin lines, chain connectors, borders |

## Typography

- **Value reveals**: Inter Extra Bold, 120px, letter-spacing: -4px, `#2D4A22`
- **Descriptions**: Inter Regular, 24px, line-height: 1.6, `#1A3A14`
- **Stats**: Inter Medium, 20px, `#8CB369`
- **Logo**: Inter Bold, 80px, two-tone (sage + pine)
- **Labels**: Inter SemiBold, 13-16px, letter-spacing: 4-6px, uppercase

## Scene Breakdown

| Scene | Time | Value | Visual Highlight |
|-------|------|-------|-----------------|
| 1 | 0s-6s | Sustainability | Split screen: polluted factory vs solar facility |
| 2 | 6s-12s | Transparency | Animated supply chain: seed to customer |
| 3 | 12s-18s | Quality | Wash-test comparison: 5 vs 50 washes |
| 4 | 18s-24s | Community | 16-portrait mosaic grid wave reveal |
| 5 | 24s-30s | Future | Logo, tagline, stat pills, fade to white |

## How to Use

1. Copy `prompt.md` into your AI agent conversation
2. Replace "ReForm" with your brand name
3. Replace the 5 values with your own brand pillars
4. Update stats (water savings, carbon reduction, community size, etc.)
5. Adjust color palette to match your brand identity

```bash
npx hyperframes render
```

## Customization Variables

| Variable | Default | Your Value |
|----------|---------|------------|
| Brand name | ReForm | _your brand_ |
| Tagline | "Wear the change." | _your tagline_ |
| Value words | Sustainability, Transparency, Quality, Community, Future | _your values_ |
| Stats | 78% water, 62% carbon, 45k+ members | _your stats_ |

## Dependencies

- **GSAP 3.12.5** (CDN)
- **Google Fonts**: Inter (300-900 weights)
- **No other dependencies**
