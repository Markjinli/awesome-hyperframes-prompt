# App Promo -- PulseFit

> A 15-second vertical-format mobile app promotion for Instagram Reels, TikTok, and YouTube Shorts. Vibrant, high-energy aesthetic with orange/purple gradients.

## Best Use Cases

- Instagram Reels / TikTok app promotion ads
- YouTube Shorts product teasers
- Mobile app launch countdown videos
- App Store / Google Play feature graphics (video variant)
- Social media paid acquisition creative
- Fitness, wellness, or lifestyle app promos
- Consumer app "coming soon" hype videos

## Key Techniques Used

### Vertical-First Design (1080x1920)
The entire composition is designed for 9:16 aspect ratio from the ground up. Key vertical-format considerations:
- Safe zones: critical content kept within 80px of horizontal edges and 120px of vertical edges to avoid platform UI overlays (TikTok's like/comment/share buttons and username bar, Instagram Reels' caption/engagement bar)
- Oversized typography (56-88px) that fills the vertical frame effectively
- Stacked layout (logo -> headline -> tagline -> icons -> CTA) rather than side-by-side
- Phone mockup scaled to 360x640px to fit comfortably within the vertical canvas while remaining readable

### Vibrant Gradient System
- Primary gradient: `linear-gradient(135deg, #FF6B35, #A855F7)` (orange-to-purple diagonal)
- Teal accent (`#00F5D4`) for counters and highlights -- provides strong contrast against the warm gradient
- Animated background blobs: three large blurred circles that slowly drift, creating a dynamic background without distracting from content
- Accent sweep lines: horizontal gradient lines that continuously sweep across the canvas at different vertical positions, each with a different accent color

### Fast-Paced Burst Sequencing (Scene 2)
The features scene uses a "conveyor belt" pattern where three content bursts slide in and out in rapid succession within a single HyperFrames composition:
1. Each burst enters from the bottom (`y: 80 -> 0`, 0.4s) with `power4.out` easing
2. Overlay text scales in with `back.out(1.4)` for punchy, attention-grabbing impact
3. Each burst exits upward (`y: 0 -> -60`, 0.3s) with `power2.in`
4. Next burst immediately follows, creating seamless rapid cuts

This pattern creates the fast-cut feel essential for short-form vertical video while keeping all content within a single composition (avoiding composition-switching overhead for sub-scenes).

### CSS-Drawn Phone Mockup
The phone mockup is built entirely with CSS: rounded rectangle with semi-transparent border, notch at top, and flexbox-based screen content. The interior content changes per burst:
- Burst 1: Workout stats (45 min, 420 kcal, 65% progress)
- Burst 2: Meal plan data (2,200 cal/day, 140g protein, 78% progress with purple gradient)
- Burst 3: Community stats (12.4K steps, #3 rank)

No external images required for the mockup. Replace with real screenshots by swapping interior content for `<img>` tags.

### Animation Patterns Demonstrated

| Pattern | Where Used | Technique |
|---------|-----------|-----------|
| Elastic reveal | Brand name (Scene 1), logo (Scene 3) | `ease: elastic.out(1, 0.3)` and `back.out(1.7)` |
| Bounce entrance | Fitness icons (Scene 1) | `ease: bounce.out` with stagger |
| Conveyor-belt bursts | Feature content (Scene 2) | Sequential `y: 80 -> 0 -> -60` with overlap |
| Scale-pop text | Burst overlay text (Scene 2) | `scale: 0.8 -> 1.05 -> 1` with `back.out` |
| Continuous blob drift | Background (all scenes) | `repeat: -1, yoyo: true` on x/y/scale |
| Accent line sweeps | Background (all scenes) | `x: -100% -> 100%, repeat, ease: none` |
| Slide-up badges | Store badges (Scene 3) | `y: 40 -> 0` with stagger |
| Star rating reveal | Rating row (Scene 3) | `opacity + scale` with `back.out` |
| CSS infinite pulse | Bottom CTA (Scene 3) | `@keyframes` loop on `opacity + scale` |

### Gradient Background Scene Transition
Scene 3 transitions from the dark background to a full-canvas orange-to-purple gradient (`linear-gradient(135deg, #FF6B35, #A855F7)`) baked directly into the composition's CSS. This creates a dramatic energy shift for the CTA without requiring a separate animated overlay element.

## How to Customize

1. **Replace the app name**: Search for "PULSEFIT" and "PulseFit" and replace with your app name. Adjust the `font-size` in `.hook-brand` if your name is significantly shorter or longer.
2. **Change the color gradient**: Update `--gradient-main`, `--primary`, `--secondary`, and `--accent-teal` CSS custom properties. Replace the gradient in `.comp-cta` background. Update blob colors in `.bg-blob-*` classes and accent line colors.
3. **Edit the feature bursts** (Scene 2):
   - Update `.burst-overlay-text` content for each of the three bursts
   - Modify the phone mockup interior content (stat numbers, labels, progress bar widths)
   - Adjust burst timing in the GSAP script (currently 2s per burst: 4-6s, 6-8s, 8-10s)
4. **Replace phone mockup with real screenshots**: Swap the CSS phone interior content for `<img>` tags pointing to your app screenshots. Maintain the 360x640 mockup container.
5. **Update the store badges**: Change "App Store" and "Google Play" text. Optionally replace the styled `<div>` badges with actual App Store / Google Play badge SVG images.
6. **Adjust timing**: The 15-second total is split 0-4s (hook), 4-10s (features), 10-15s (CTA). Adjust `data-start`/`data-duration` and GSAP timing values to match.
7. **Change the social proof**: Update "500K+ COMMUNITY" burst text and the "4.9" rating value in Scene 3.
8. **Swap fonts**: Change the Google Fonts import from Outfit to your brand font. Update all `font-family` references. Outfit works well for consumer/fitness apps; Poppins or Montserrat are good alternatives.
9. **Add platform-specific safe zones**: Adjust padding in compositions if your target platform has different UI overlay requirements than the defaults built in.

## Expected Output

A 15-second, 1080x1920 (vertical) MP4 video with:
- **0-4s**: Dark background with three drifting orange/purple/teal blobs; "INTRODUCING" label fades in with teal color and wide letter-spacing; "PULSEFIT" brand name elastic-scales in with gradient text and glow; "Your AI Fitness Coach" tagline slides up; three fitness icons (weightlifter, heart, flame) bounce in sequence; brand name floats subtly
- **4-10s**: Three fast-cut feature bursts within a single composition:
  - Burst 1 (4-6s): Phone mockup with workout stats slides up from bottom; "200+ WORKOUTS" in orange gradient overlay text scales in with back.out; "From HIIT to Yoga" sub-label
  - Burst 2 (6-8s): Phone mockup transitions to meal plan screen; "MEAL PLANS BY AI" in purple gradient text; "Personalized. Precise. Delicious." sub-label
  - Burst 3 (8-10s): Phone mockup shows community leaderboard; "500K+ COMMUNITY" in teal text; "Challenge friends. Crush goals together." sub-label; accent lines sweep continuously throughout
- **10-15s**: Full-canvas orange-to-purple gradient background; logo elastic-bounces in; "Ready to Move?" headline; App Store and Google Play badge buttons slide up; "4.9" rating with gold star characters; "Download Now" pulsing CTA text at bottom; music fades out from 14-15s

Render with:
```bash
npx hyperframes preview   # View in browser
npx hyperframes render    # Export to MP4
```

## Platform-Specific Export Tips

- **TikTok**: Export at 1080x1920, ensure key text stays within the central 80% of the frame. The right-side engagement buttons (like, comment, share) and bottom username bar can overlay content.
- **Instagram Reels**: Same resolution; the bottom ~150px may be covered by the caption and engagement bar. The hook-label at top and CTA at bottom are positioned with this in mind.
- **YouTube Shorts**: Same resolution; right-side engagement buttons similar to TikTok. The timestamp and channel name overlay at bottom-left.
- **All platforms**: The first 1-2 seconds are critical for retention -- the "INTRODUCING" + brand reveal hook is specifically designed to grab attention before the viewer scrolls past.

## File Structure

```
app-promo/
├── prompt.md       # Structured 6-dimension prompt (copy-paste into AI agent)
├── index.html      # Complete HyperFrames composition (~380 lines, preview + render)
└── README.md       # This file
```
