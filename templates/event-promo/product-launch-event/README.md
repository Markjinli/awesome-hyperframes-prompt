# Product Launch Event Opener -- Pro X (Apple Keynote Style)

## Effect Overview

A 30-second dramatic product launch event opener in the style of an Apple keynote. A product is revealed entirely through light choreography -- starting as a dark silhouette on a black stage, gradually illuminated with edge glints and metallic sweeps, then surrounded by six spec cards that fly in from the edges in a staggered wave. The climax delivers a bold "Available today." in Apple blue, followed by a clean fade to black. Designed to build anticipation and deliver a premium, polished reveal.

## Use Cases

- **Hardware product launch** keynote opener (phones, laptops, wearables)
- **Software platform** announcement at annual conferences
- **Flagship product reveal** for investor day or press events
- **Brand campaign** cinematic hero video for website or YouTube
- **Internal launch event** opener for company all-hands

## Key Techniques Illustrated

| Technique | Where Used | How It Works |
|-----------|-----------|--------------|
| **Light-driven narrative** | All scenes | A single `radial-gradient` spotlight expands, intensifies, and contracts across scenes to guide the audience's focus |
| **Silhouette suspense** | Scenes 1-2 | Product shown as a dark translucent shape (opacity 0.25-0.6) with only edge glints visible, building anticipation through visual withholding |
| **Metallic sweep** | Scenes 1-2 | A `linear-gradient` stripe sweeps top-to-bottom across the product via GSAP to simulate a studio light panning across a reflective surface |
| **Edge glint** | Scenes 2-3 | Thin 1px `div` elements with vertical gradient simulate light catching polished edges |
| **Spec card fly-in** | Scene 3 | Six glass-morphism cards positioned around the product fly in from their respective corners in a staggered wave (0.5s intervals) |
| **Glass morphism cards** | Scene 3 | `backdrop-filter: blur(20px)` + semi-transparent dark background + 1px silver border creates premium translucent card effect |
| **Product lift + scale** | Scene 4 | Product moves up 50px (y: 40 to y: -20) while scaling to 1.03x, giving it physical presence on stage |
| **back.out easing** | Scene 4 | "Available today." uses `ease: 'back.out(1.6)'` for a satisfying overshoot-and-settle entrance |
| **Spotlight contraction** | Scene 5 | Spotlight shrinks from full-stage illumination back to a point as everything fades, mirroring stage lighting conventions |
| **Legal text** | Scene 5 | Small silver text at bottom edge fades in/out with rest of content, following real keynote conventions |

## Color Palette

| Role | Hex | Usage |
|------|-----|-------|
| True Black | `#000000` | Stage background |
| Off-White | `#F5F5F7` | Primary text, product name |
| Silver | `#86868B` | Secondary text, spec labels, legal text |
| Apple Blue | `#2997FF` | "Available today" CTA, subtle glow on product |
| Surface Gray | `#1D1D1F` | Spec card backgrounds |

## Typography

- **Product name**: Inter ExtraBold, 84px, letter-spacing: -3px, `#F5F5F7`, with subtle `text-shadow` glow
- **Tagline**: Inter Regular, 28px, `#F5F5F7`
- **Spec values**: Inter Bold, 36px, `#F5F5F7`, letter-spacing: -0.5px
- **Spec labels**: Inter Medium, 14px, uppercase, letter-spacing: 1px, `#86868B`
- **"Available today"**: Inter Bold, 52px, `#2997FF`, letter-spacing: -1px
- **Price / CTA**: Inter Regular, 18-24px, `#86868B` / `#2997FF`
- **Legal**: Inter Regular, 11px, `#86868B`

## Scene Breakdown

| # | Time | Scene | Key Visual |
|---|------|-------|-----------|
| 1 | 0s-6s | Darkness + build-up | Spotlight fades on, silhouette emerges, particles drift |
| 2 | 6s-12s | Reveal begins | Metallic sweep, "Pro X" name revealed, tagline appears |
| 3 | 12s-20s | Spec fly-in wave | 6 glass cards fly in from edges in staggered rhythm |
| 4 | 20s-26s | Climax + CTA | Product lifts, "Available today." in blue, price + URL |
| 5 | 26s-30s | Outro | Spotlight contracts, logo holds, fade to black |

## How to Use

1. Copy `prompt.md` into your AI agent conversation
2. Replace `Pro X` with your product name
3. Replace all 6 specs (M4 Ultra, 32-core Neural Engine, etc.) with your product's key features
4. Update price, URL, and tagline
5. Replace the silhouette `<div>` with an actual product render `<img>` for best results
6. Run: `npx hyperframes render`

## Customization Variables

| Variable | Default | Your Value |
|----------|---------|------------|
| Product name | Pro X | _your product_ |
| Tagline | "Power without compromise." | _your tagline_ |
| 6 specs | M4 Ultra, 32-core, 64GB, 18hr, XDR, 1TB | _your key features_ |
| Price | Starting at $1,999 | _your price_ |
| CTA | Order at pro-x.com | _your URL_ |
| Accent color | #2997FF (Apple blue) | _your brand accent_ |

## Pro Tips

- **Replace the silhouette**: The current product silhouette is a CSS-styled `div`. For a real product launch, replace it with an actual product render using `<img>` and adjust the animation to match.
- **Adjust spec timing**: The spec fly-in wave uses staggered intervals. Increase or decrease the gap between cards by modifying the `at` values in the `cardFlyIns` array.
- **Light temperature**: For a warmer reveal (gold/amber), change the spotlight gradient colors from `rgba(255,255,255,...)` to `rgba(255,220,180,...)`.
- **Add audio markers**: The GSAP timeline can trigger audio events via `tl.call()` at key moments -- add your own sound effect triggers.

## Dependencies

- **GSAP 3.12.5** (CDN: `cdnjs.cloudflare.com`)
- **Google Fonts**: Inter (300-900 weights)
- **No other dependencies** -- all effects are pure CSS + GSAP
