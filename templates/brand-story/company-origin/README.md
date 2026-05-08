# Company Origin Story -- Atlas Coffee

## Effect Overview

A 45-second cinematic brand origin story tracing a coffee company's journey from a garage roastery to a nationwide brand. Slow, intimate pacing with film grain textures, Ken Burns-style photo movements, and warm amber-and-cream color grading evoke a nostalgic documentary feel. Designed to build emotional connection through a six-scene narrative arc.

## Use Cases

- **Brand documentary** opener for company websites or YouTube channels
- **Investor pitch** storytelling segment that humanizes the brand
- **Recruitment / culture** video showcasing company roots and values
- **Store / cafe** in-location looping display (silent version)
- **Social media** long-form cut for brand anniversary campaigns

## Key Techniques Illustrated

| Technique | Where Used | How It Works |
|-----------|-----------|--------------|
| **Film grain overlay** | Global, all scenes | SVG `feTurbulence` noise + CSS animation creates organic film texture |
| **Ken Burns effect** | Scene 1 | Slow GSAP-driven `scale` transform with controlled `transformOrigin` on the garage photo |
| **Vignette** | Global | `radial-gradient` with warm brown falloff darkens edges for cinematic depth |
| **Letterbox bars** | Scenes 1, 5, 6 | 100px black bars fade in/out to signal "cinematic mode" shifts |
| **Stagger reveal** | Scenes 2, 4 | Calendar X-marks and map pins appear sequentially via GSAP `stagger` |
| **Counter animation** | Scene 5 | GSAP tween on a proxy object drives `textContent` updates for number roll-up |
| **Quote overlay** | Scene 2 | Large italic serif quote types on over dark background with `textShadow` for readability |
| **Light leak transitions** | Scene transitions | `radial-gradient` overlay fades in/out as a warm optical bridge between compositions |
| **Crossfade composition** | All scene changes | Helper function toggles opacity between consecutive `.composition` divs |

## Color Palette

| Role | Hex | Usage |
|------|-----|-------|
| Deep Brown | `#3C2415` | Primary text, dark backgrounds, vignette falloff |
| Warm Amber | `#C68B59` | Accent text, highlights, light bulb glow |
| Cream Parchment | `#F5E6D3` | Light backgrounds, photo mats, calendar surface |
| Saddle Brown | `#8B4513` | Map pins, emphasis elements |

## Typography

- **Headlines / logo**: Playfair Display Bold, 64-96px, letter-spacing: -1px to -2px
- **Quotes**: Playfair Display Italic, 36-38px, `#C68B59` or `#F5E6D3`
- **Body / labels**: Inter Regular/Medium, 14-22px, uppercase labels at 4-6px letter-spacing
- **Numbers (impact)**: Playfair Display Black, 72px

## Scene Breakdown

| Scene | Time | Duration | Mood |
|-------|------|----------|------|
| The Beginning | 0s-8s | 8s | Nostalgic, quiet wonder |
| The Struggle | 8s-15s | 7s | Gritty, honest, determined |
| The Breakthrough | 15s-22s | 7s | Hopeful, validating |
| The Community | 22s-30s | 8s | Warm, human, connected |
| The Impact | 30s-38s | 8s | Proud, celebratory, expansive |
| The Future | 38s-45s | 7s | Reflective, forward-looking |

## How to Use

1. Copy `prompt.md` into your AI agent conversation
2. Replace `Atlas Coffee` with your brand name and details
3. Replace milestone dates, numbers, and quotes with your own
4. Adjust color palette to match your brand
5. Have the AI agent generate the HTML, then run:

```bash
npx hyperframes render
```

## Customization Variables

Search and replace these in both `prompt.md` and `index.html`:

| Variable | Default | Your Value |
|----------|---------|------------|
| Brand name | Atlas Coffee | _your brand_ |
| Tagline | "From Garage to Nationwide" | _your tagline_ |
| Founding year | 2013 | _your year_ |
| Key milestones | 2015, 2018, 2020, 2023, 2026 | _your milestones_ |
| Impact numbers | 100+ stores, 50,000+ farmers, 1M+ cups | _your stats_ |

## Dependencies

- **GSAP 3.12.5** (CDN: `cdnjs.cloudflare.com`)
- **Google Fonts**: Playfair Display + Inter
- **No other dependencies** -- pure HTML/CSS/JS, render-ready in HyperFrames
