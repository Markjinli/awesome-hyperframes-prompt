# Company Origin Story -- Atlas Coffee

## 1. Video Specs
- **Duration**: 45s
- **Resolution**: 1920x1080
- **Frame rate**: 30fps
- **Aspect ratio**: 16:9 landscape

## 2. Visual System

### Color Palette
- **Primary**: #3C2415 (deep roasted brown)
- **Secondary**: #C68B59 (warm amber)
- **Background**: #F5E6D3 (cream parchment)
- **Accent**: #8B4513 (saddle brown, for emphasis)

### Typography
- **Headlines**: Playfair Display Bold, 64-80px, letter-spacing: -1px
- **Quote overlays**: Playfair Display Italic, 36px, letter-spacing: 0.5px, color: #C68B59
- **Body / dates**: Inter Regular, 20px, letter-spacing: 0, color: #3C2415
- **Scene labels**: Inter Medium, 14px, letter-spacing: 4px, uppercase, color: #C68B59

### Atmosphere Keywords
Warm, nostalgic, handcrafted, honest, timeless, cinematic, intimate

### Texture
- Full-screen film grain overlay (CSS noise + SVG filter)
- Subtle vignette (radial gradient around edges)
- Letterbox aspect ratio wrappers for key frames
- Warm light leaks as transitional moments

## 3. Brand Assets
- **Brand name**: Atlas Coffee
- **Tagline**: "From Garage to Nationwide"
- **Founding year**: 2013
- **Key milestones**: 2013 (founded), 2015 (first cafe), 2018 (roastery), 2020 (national distribution), 2023 (100th store), 2026 (carbon neutral)
- **Logo**: Text-based wordmark in Playfair Display, amber-on-cream or cream-on-dark

## 4. Scene Timeline

### Scene 1 -- The Beginning (0s-8s)
- **Visual**: Vintage photograph aesthetic. A dim garage interior fades on screen -- warm light spills from a single bulb. A close-up of green coffee beans spilling from a burlap sack. The word "2013" fades in subtly.
- **Animation**: Slow Ken Burns push-in on the garage photo (3s). Beans enter from bottom with soft drop-shadow, settle over 1.5s. "2013" fades in last.
- **Audio prompt**: Soft lo-fi guitar picking, warm crackle as if needle drops on vinyl.

### Scene 2 -- The Struggle (8s-15s)
- **Visual**: Timelapse photos of early mornings. A hand-painted sign "Atlas Coffee -- Open". Empty chairs. A calendar with dates crossed off one by one -- persistence. Quote overlay: "We sold 12 cups our first week. We gave away twice that."
- **Animation**: Crossfade transition from Scene 1. Calendar X-marks appear in staggered sequence (0.3s apart). Quote types on letter by letter over 2s.
- **Audio prompt**: Music dips slightly. Subtle clock ticking sound effect under the calendar sequence.

### Scene 3 -- The Breakthrough (15s-22s)
- **Visual**: A local newspaper clipping zooms in -- "Best Coffee in the Valley". Customer line forming outside the shop. Hands pouring latte art. The garage transforms into the first proper cafe storefront.
- **Animation**: Newspaper enters with scale-up + slight rotation (from flat to face-on). Line of people fades in left-to-right. Latte pour cross-dissolves to a bright storefront shot.
- **Audio prompt**: Music swells, adds a soft brushed drum kit. Warm major chord resolution at 19s.

### Scene 4 -- The Community (22s-30s)
- **Visual**: Montage -- baristas laughing, regulars raising cups, a community bulletin board covered in flyers. Map pin drop animation showing new locations spreading outward. Warm, golden-hour lighting throughout.
- **Animation**: Photo montage with staggered fade-in (each photo 1.2s). Map pins drop one by one with a subtle bounce easing (stagger 0.4s). Bulletin board elements enter from edges.
- **Audio prompt**: Music becomes fuller -- acoustic bass and light percussion join. Conversation murmur very low in background.

### Scene 5 -- The Impact (30s-38s)
- **Visual**: Split-screen comparisons -- tiny garage / modern roastery. Big number reveals: "100+ STORES", "50,000+ FARMERS", "1M+ CUPS DAILY". Aerial drone shot of the flagship roastery with solar panels.
- **Animation**: Split-screen divider slides in from left as a warm line. Numbers animate via counter from 0 (GSAP). Aerial shot fades up from black as numbers reach their targets. Film grain intensifies slightly.
- **Audio prompt**: Music reaches emotional peak. Strings swell. Sound effect of coffee pouring at number-reveal moments.

### Scene 6 -- The Future (38s-45s)
- **Visual**: Cream parchment background returns. The Atlas Coffee logo locks center. Tagline "From Garage to Nationwide" fades below. A final line: "The next chapter starts with you." Fade to black with grain.
- **Animation**: Logo scales up gently with ease-out. Tagline types on. Final line fades in after 1.5s pause. Slow fade to black over final 1.5s. Film grain persists to the last frame.
- **Audio prompt**: Music resolves to a single held guitar note. Vinyl crackle continues. Silence at 44.5s before clean cut.

## 5. Technical Preferences

### Animation Engine
- **GSAP 3** (loaded via CDN) for all scene animations and timeline orchestration
- CSS `@keyframes` for film grain and subtle continuous effects
- GSAP ScrollTrigger NOT needed (video timeline, not scroll-driven)

### HyperFrames Conventions
- Use `data-composition-id` on each scene container div
- Use `data-start` and `data-duration` attributes to describe intent (AI agent maps to HyperFrames adapter)
- Use `data-track-index` for z-ordering hint
- Each scene is a `<div>` with `position: absolute; inset: 0; width: 1920px; height: 1080px`

### Effects
- **Film grain**: CSS `repeating-conic-gradient` noise or SVG `<feTurbulence>` overlay
- **Vignette**: `radial-gradient(ellipse at center, transparent 60%, rgba(60,36,21,0.4) 100%)`
- **Ken Burns**: CSS `transform: scale()` + `transform-origin` driven by GSAP
- **Letterbox**: 120px black bars top/bottom during cinematic moments

## 6. Reference

### Style References
- "Chef's Table" opening sequences (Netflix) -- intimate, textured, slow pacing
- Patagonia brand films -- authentic, purpose-driven, natural warmth
- Blue Bottle Coffee origin documentaries

### Code Reference (sample aesthetic anchor)
```html
<div data-composition-id="scene-origin" style="
  position: absolute; inset: 0;
  background: linear-gradient(170deg, #F5E6D3 0%, #E8D5C0 100%);
  display: flex; align-items: center; justify-content: center;
">
  <div style="position: relative; max-width: 1000px; text-align: center;">
    <p style="font: italic 36px 'Playfair Display'; color: #C68B59; margin: 0 0 24px;">
      "We started with a popcorn popper and a dream."
    </p>
    <p style="font: 400 20px 'Inter'; color: #3C2415; letter-spacing: 4px; text-transform: uppercase;">
      Portland, Oregon -- 2013
    </p>
  </div>
</div>
```
