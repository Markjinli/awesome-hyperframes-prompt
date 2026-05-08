# Conference Teaser -- NeonConf 2026

## Effect Overview

A 20-second high-energy tech conference teaser with a cyberpunk/neon-noir aesthetic. Fast cuts, glitch text effects, speaker name reveals with glowing photo frames, a wireframe venue teaser, and a dramatic countdown finale. Dark backgrounds with magenta (#FF00FF) and cyan (#00FFFF) neon accents create an urgent, futuristic atmosphere perfect for tech event promotion.

## Use Cases

- **Tech conference** promo for social media (YouTube, X, LinkedIn)
- **Hackathon** or developer summit teaser trailer
- **Product keynote** opening sizzle reel
- **Event countdown** post (cut into 5s, 10s, and full 20s versions)
- **Speaker announcement** series (each speaker scene can be isolated)

## Key Techniques Illustrated

| Technique | Where Used | How It Works |
|-----------|-----------|--------------|
| **Neon glow text** | All scenes | Multi-layered `text-shadow` with increasing blur radii and opacity creates neon tube effect |
| **Glitch/chromatic aberration** | Logo, speaker names, finale | `::before`/`::after` pseudo-elements with offset `text-shadow` and `clip-path` slices, toggled via `.active` class |
| **Scanline overlay** | Global | `repeating-linear-gradient` (2px pattern) at 6% opacity across entire canvas |
| **Grid background** | All scenes | Dual `linear-gradient` (horizontal + vertical) with `mask-image: radial-gradient` fading edges |
| **Scan sweep** | Scene 2 | Absolutely-positioned 4px bar with neon glow travels top-to-bottom via GSAP |
| **Speaker photo glow** | Scenes 3-5 | `box-shadow` with 3-layer spread (15px, 40px, 80px) on circular container with neon border |
| **Flash transitions** | Between scenes | Full-screen white overlay with rapid fade (0.06-0.3s) simulates camera flash cut |
| **Glow ring** | Scene 6 | Circular `div` with neon `border` + glowing `box-shadow` pulsates 3 times |
| **Back.out easing** | Logo, photo reveals | Heavy overshoot (`back.out(1.5-2.2)`) creates energetic "pop" on element entrances |
| **Glitch transition** | Between speaker scenes | Rapid class toggle on text elements creates brief distortion as a transition device |

## Color Palette

| Role | Hex | Usage |
|------|-----|-------|
| Neon Pink | `#FF00FF` | Primary glow, logo, speaker photo borders, date text |
| Neon Cyan | `#00FFFF` | Secondary glow, role text, venue label, alternate photo borders |
| Background | `#0A0A0A` | Canvas base |
| Surface Dark | `#111118` | Cards, photo insets |
| White | `#FFFFFF` | Speaker names, CTA text |

## Typography

- **Headlines / logos**: JetBrains Mono Bold/ExtraBold, 56-130px, neon glow
- **Speaker names**: JetBrains Mono Bold, 56px, white with subtle white glow
- **Roles**: Inter SemiBold, 16px, letter-spacing: 5px, uppercase, neon cyan
- **Date**: JetBrains Mono, 28-130px (grows in finale)
- **CTA**: Inter Medium, 20px, letter-spacing: 3px, uppercase, white

## Scene Breakdown

| # | Time | Scene | Duration |
|---|------|-------|----------|
| 1 | 0s-2.5s | Logo sting with glitch, date reveal | 2.5s |
| 2 | 2.5s-5s | Venue wireframe, San Francisco label, scan sweep | 2.5s |
| 3 | 5s-8s | Speaker: Dr. Aria Chen (AI Ethics / Stanford) | 3s |
| 4 | 8s-11s | Speaker: Marcus Webb (CEO / SynthWave) | 3s |
| 5 | 11s-15s | Rapid fire: Elena Rodriguez + Jay Park (2s each) | 4s |
| 6 | 15s-20s | Countdown date, venue, CTA, glow pulse, cut to black | 5s |

## How to Use

1. Copy `prompt.md` into your AI agent conversation
2. Replace event name, date, venue, and speaker details
3. Adjust neon colors if needed (keep high contrast on dark)
4. Add actual speaker photos via `<img>` tags instead of emoji placeholders
5. Run: `npx hyperframes render`

## Customization Variables

| Variable | Default | Your Value |
|----------|---------|------------|
| Event name | NeonConf 2026 | _your event_ |
| Date | November 12-14, 2026 (11.12.26) | _your dates_ |
| Venue | San Francisco | _your venue_ |
| Speakers | Chen, Webb, Rodriguez, Park | _your speakers_ |
| CTA | Tickets at NEONCONF.IO | _your CTA + URL_ |
| Neon primary | #FF00FF | _your accent_ |
| Neon secondary | #00FFFF | _your secondary accent_ |

## Dependencies

- **GSAP 3.12.5** (CDN)
- **Google Fonts**: JetBrains Mono (400, 700, 800) + Inter (400-700)
- **No other dependencies** -- all effects are pure CSS/JS
