# Tech Product Launch -- Nexus AI

> A 30-second cinematic product launch video template. Dark tech aesthetic with neon accents, designed for AI/tech product announcements.

## Best Use Cases

- AI / ML product launch videos
- Developer tool or API announcement trailers
- Web3 / blockchain project reveals
- SaaS platform "coming soon" teasers
- Tech conference keynote openers
- Startup fundraising pitch videos

## Key Techniques Used

### 6-Dimension Prompt Structure
The prompt follows the full HyperFrames 6-dimension formula (Video Specs, Visual Style, Scene Structure, Animation, Audio, Technical Constraints) with explicit hex codes, font names, pixel values, and easing curves. This level of specificity gives AI agents precise instructions and produces consistent, predictable output.

### Scene-Driven Timeline Architecture
5 scenes over 30 seconds, each wrapped in a `<div>` with `data-composition-id`, `data-start`, `data-duration`, and `data-track-index` attributes. Scene visibility is driven by `opacity` toggling (not `display: none`) to maintain GSAP timeline integrity. Each scene's `data-start + data-duration` precisely equals the next scene's `data-start` for seamless sequencing.

### GSAP Master Timeline
All animations are orchestrated through a single GSAP `timeline`, enabling frame-accurate seeking via `window.__hf_gsap`. This is the recommended pattern for HyperFrames compositions that need to be scrubbed during preview and rendered frame-by-frame. Animation overlaps are achieved with GSAP's absolute position parameter rather than sequential chaining.

### Dark Tech Visual System
- Background: `#0A0A1A` with CSS grid-line texture (`background-image` with repeating linear gradients at 60px intervals)
- Primary gradient: `#6C5CE7` to `#00D2FF`
- Glassmorphism cards with `backdrop-filter: blur(20px)` and semi-transparent borders
- Inter font family for headlines and body; JetBrains Mono for code/labels
- Vignette overlay for cinematic depth in the outro
- Glow effects via layered `box-shadow` with rgba values

### Animation Patterns Demonstrated

| Pattern | Where Used | Technique |
|---------|-----------|-----------|
| Elastic reveal | Logo dot + mark (Scene 1) | `ease: elastic.out(1,0.4)` |
| Staggered entrance | Problem bullets (Scene 2), feature pillars (Scene 3), stat cards (Scene 4) | `gsap.fromTo` with staggered delays |
| Number counter roll-up | Performance metrics (Scene 4) | GSAP object tween with `onUpdate` callback |
| Bar chart grow | Before/after comparison (Scene 4) | `fromTo` on `width` property |
| Continuous float | Feature icons (Scene 3), background grid | `repeat: -1, yoyo: true` with `sine.inOut` |
| Button pulse | CTA (Scene 5) | `scale` tween with `repeat` and `yoyo` |
| Crossfade transitions | All scene changes | `opacity` 1->0 on outgoing, 0->1 on incoming with 0.2s overlap |

### SVG/CSS Visual Elements (Zero External Assets)
- Hexagonal logo mark using CSS `clip-path: polygon(...)`
- Network node diagram built with absolutely-positioned `<div>` elements
- Gradient text via `-webkit-background-clip: text`
- Glow effects via layered `box-shadow` with rgba
- No external images required -- everything is CSS/HTML

## How to Customize

1. **Replace the product name**: Search for "Nexus AI" and "nexus.ai" and replace with your brand.
2. **Change the color palette**: Update the CSS custom properties (`--primary`, `--secondary`, `--accent`) in `:root` and the corresponding gradient references throughout the HTML and JS.
3. **Edit the pain points** (Scene 2): Modify the three `.problem-bullet` text nodes in the HTML.
4. **Edit the feature pillars** (Scene 3): Update `.pillar-label` and `.pillar-desc` text for each of the three feature columns.
5. **Change the metrics** (Scene 4): Update the `data-counter` attribute values and the bar chart target widths in the JS `counterTargets` and `chartBars` arrays.
6. **Adjust timing**: Modify `data-start` and `data-duration` on each scene, then update the corresponding GSAP time values in the script. The master timeline uses absolute second values that should match.
7. **Update the CTA** (Scene 5): Change the headline text, CTA button label, and footer URL.
8. **Swap fonts**: Replace the Google Fonts `@import` URL and update `font-family` references in CSS.

## Expected Output

A 30-second, 1920x1080 MP4 video with:
- **0-5s**: Pulsing dot expands into hexagonal logo mark, "NEXUS AI" wordmark slides up on dark background with grid texture
- **5-11s**: Split layout showing "Your Data Is Scattered" headline with three pain-point bullets animating in (staggered); network diagram with nodes connecting on the right
- **11-20s**: Glassmorphism hero card scales in at center with three feature pillars (Unified Intelligence, Real-Time Insights, Autonomous Agents) staggering in with continuously floating icons
- **20-26s**: Three stat cards with animated counters (10x, 99.9%, 500K+); horizontal bar chart comparing before/after metrics across three KPIs (Speed, Accuracy, Cost Savings)
- **26-30s**: Logo returns to center, "The Future Is Unified" headline, pulsing "Join the Waitlist" CTA button, vignette darkens canvas edges, footer URL "nexus.ai"

Render with:
```bash
npx hyperframes preview   # View in browser
npx hyperframes render    # Export to MP4
```

## File Structure

```
tech-product-launch/
├── prompt.md       # Structured 6-dimension prompt (copy-paste into AI agent)
├── index.html      # Complete HyperFrames composition (~400 lines, preview + render)
└── README.md       # This file
```
