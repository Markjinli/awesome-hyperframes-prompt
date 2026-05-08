# SaaS Feature Demo -- FlowBoard

> A 20-second SaaS feature walkthrough video. Clean, minimal aesthetic with blue accents. Product UI mockups and data charts take center stage.

## Best Use Cases

- SaaS product feature announcements
- Product Hunt launch videos
- Landing page hero videos
- Investor demo / pitch deck videos
- Customer onboarding "what's new" videos
- B2B product explainers
- Feature comparison videos

## Key Techniques Used

### Clean Minimal Visual System
Inspired by Linear, Notion, and Stripe design sensibilities:
- Light background: `#F8FAFC` with subtle radial gradient washes in blue and indigo
- Primary blue: `#3B82F6`, secondary indigo: `#6366F1`, accent green: `#10B981`
- Near-black text (`#0F172A`) instead of pure black for visual softness
- Generous white space with 60-100px padding blocks
- Cards with soft shadows (`box-shadow: 0 1px 3px rgba(0,0,0,0.06)`)
- Switzer/Inter font pairing for modern SaaS typography

### CSS-Drawn Product Mockups
Instead of requiring external screenshot images, the FlowBoard kanban board is built entirely with CSS -- colored cards in columns with tags (Design, Dev, Bug, Done). This makes the template self-contained and immediately previewable without asset dependencies. Replace with real product screenshots by swapping the mockup `<div>` for an `<img>` tag.

### Data Visualization Without External Libraries
All charts are built with inline SVG (donut chart) and CSS-styled `<div>` elements (bar chart):
- **Donut chart**: SVG `<circle>` with `stroke-dasharray`/`stroke-dashoffset` animation to draw the arc from empty to 94%
- **Bar chart**: CSS `height` tweens via GSAP for bar growth, comparing Industry Avg vs FlowBoard across 4 quarters
- **KPI counter**: GSAP object tween with `toFixed(1)` formatting for the "2.3x" productivity boost number
- Uses `font-variant-numeric: tabular-nums` to prevent layout shift during number animations

### Card Focus Cycling Pattern
Scene 2 demonstrates a "feature highlight carousel" pattern where cards receive focus one at a time:
1. All three feature cards stagger in from below
2. At 6.5s, card 1 gets a blue glow shadow and its accent strip brightens; dot indicator 1 activates
3. At 7.8s, focus shifts to card 2 with the same treatment
4. At 9.1s, focus shifts to card 3
5. Dot indicators update to match the currently focused card

This pattern is excellent for product tours where you want to draw attention to individual features sequentially without cutting between scenes.

### Animation Patterns Demonstrated

| Pattern | Where Used | Technique |
|---------|-----------|-----------|
| Slide from right | Hero screenshot (Scene 1) | `x: 60 -> 0` with `scale: 0.95 -> 1` |
| Fade-up stagger | Feature cards (Scene 2) | `y: 40 -> 0, stagger: 0.2s` |
| Card focus glow | Feature cards (Scene 2) | Dynamic `boxShadow` tween + class toggle |
| Donut arc draw | On-time delivery (Scene 3) | SVG `strokeDashoffset` from full circumference to target |
| Number counter | Donut % and KPI (Scene 3) | GSAP object `onUpdate` with `Math.round()` |
| Bar chart growth | Quarterly comparison (Scene 3) | `fromTo` on `height` with staggered delays |
| Crossfade + blur | All scene transitions | `opacity` + `filter: blur(4px)` |
| Button pulse | CTA (Scene 4) | `scale: 1 -> 1.03, repeat, yoyo` |
| Badge stagger | Trust badges (Scene 4) | `opacity + y` with staggered delays |

## How to Customize

1. **Replace the product name**: Search for "FlowBoard" and replace with your product name. Update the logo mark letter ("F") in both HTML locations (hero and outro).
2. **Swap product screenshots**: Replace the CSS kanban mockup with `<img>` tags pointing to your actual product screenshots. Maintain the same container dimensions for consistent layout.
3. **Edit the feature cards** (Scene 2): Update `.feature-card-title` and `.feature-card-desc` text for each of the three cards. Adjust `focusCard()` timing calls in JS to match your desired focus pacing.
4. **Change the data metrics** (Scene 3):
   - Donut chart: Update the `targetOffset` calculation (change `0.94` to your percentage as a decimal)
   - Bar chart: Modify `industryHeights` and `flowboardHeights` arrays (values are pixels, max ~50px)
   - KPI counter: Change the `val: 2.3` target in the `kpiObj` tween
5. **Update the CTA** (Scene 4): Change the headline text, button label, caption, and trust badge labels (SOC 2, GDPR, SLA).
6. **Adjust timing**: Modify `data-start`/`data-duration` on each scene and update corresponding GSAP time values.
7. **Customize the color scheme**: Replace the CSS custom properties in `:root` (`--primary`, `--primary-dark`, `--secondary`, `--accent-green`).
8. **Swap fonts**: Change the Google Fonts import from Inter to your brand font. Update all `font-family` references.

## Expected Output

A 20-second, 1920x1080 MP4 video with:
- **0-5s**: Split layout with FlowBoard logo, "Projects That Flow" headline with gradient highlight, subheading, CTA button on the left; kanban board product mockup with colored cards sliding in from the right
- **5-12s**: Three feature cards (Kanban & Timeline, AI Sprint Planning, Real-Time Collab) staggering in; auto-cycling focus with blue glow highlights and dot indicators at the bottom
- **12-17s**: "Teams Using FlowBoard Ship 40% Faster" headline; animated donut chart showing 94% on-time delivery, quarterly bar chart comparing Industry Avg vs FlowBoard teams, and "2.3x" productivity boost KPI counter
- **17-20s**: Centered outro with logo, "Start Flowing Today" headline with gradient underline decoration, "Get Started Free" CTA with pulse animation, "No credit card required" caption, three trust badges (SOC 2 Certified, GDPR Compliant, 99.9% Uptime SLA)

Render with:
```bash
npx hyperframes preview   # View in browser
npx hyperframes render    # Export to MP4
```

## File Structure

```
saas-feature-demo/
├── prompt.md       # Structured 6-dimension prompt (copy-paste into AI agent)
├── index.html      # Complete HyperFrames composition (~420 lines, preview + render)
└── README.md       # This file
```
