# Brand Values Manifesto -- ReForm

## 1. Video Specs
- **Duration**: 30s
- **Resolution**: 1920x1080
- **Frame rate**: 30fps
- **Aspect ratio**: 16:9 landscape

## 2. Visual System

### Color Palette
- **Primary**: #2D4A22 (deep forest green)
- **Secondary**: #8CB369 (sage green)
- **Background**: #FBF7F4 (warm off-white)
- **Accent**: #1A3A14 (dark pine, for text and contrast)

### Typography
- **Single-word value reveals**: Inter Extra Bold, 120px, letter-spacing: -4px, color: #2D4A22
- **Value descriptions**: Inter Regular, 24px, line-height: 1.6, color: #1A3A14, max-width: 600px
- **Impact numbers**: Inter Bold, 80px, color: #8CB369
- **Labels**: Inter Medium, 14px, letter-spacing: 4px, uppercase, color: #8CB369

### Atmosphere Keywords
Clean, minimal, organic, purposeful, honest, modern, grounded

### Design Language
- Split-screen comparisons (before/after, fast fashion vs sustainable)
- Large single-word value reveals dominating center screen
- Subtle organic shape blobs as background accents
- Clean white space (60%+ negative space target)
- Thin 1px dividers in sage green
- Plant-like growth animations for value reveals

## 3. Brand Assets
- **Brand name**: ReForm
- **Tagline**: "Wear the change."
- **Core values**: Sustainability, Transparency, Quality, Community, Future
- **Impact stats**: 78% less water, 62% less carbon, 100% recyclable packaging, 45k+ community members, 2030 net-zero target
- **Logo**: Wordmark in Inter Bold, all lowercase "reform" with the "re" in sage (#8CB369) and "form" in pine (#1A3A14)

## 4. Scene Timeline

### Scene 1 -- Sustainability (0s-6s)
- **Visual**: Split screen. Left side (0-2.5s): fast fashion factory pollution in muted desaturated tones. Right side (0-2.5s): ReForm's solar-powered facility in warm light. At 2.5s, both sides dissolve into a single full-screen reveal of "SUSTAINABILITY" in 120px Extra Bold across the center. Below: "78% less water. 62% less carbon."
- **Animation**: Split divider slides in from the center. Factory side fades down at 2.5s while the clean side expands to fill the frame. Word drops in with a subtle ground-planting bounce. Stats fade up below with a 0.3s stagger.
- **Audio prompt**: Soft ambient pad begins. At 2.5s word reveal, a warm harmonic shift.

### Scene 2 -- Transparency (6s-12s)
- **Visual**: A supply chain journey visual -- animated dotted line travelling from raw material (organic cotton field icon) through factory icon, to finished garment on a minimal hanger. Each node illuminates as the line passes through. Center text: "TRANSPARENCY" appears. Below: "From seed to stitch. Every step visible."
- **Animation**: Dotted line draws on with SVG stroke-dashoffset animation over 3s. Node icons scale up and glow when reached. Word reveal at 9s. Description fades in.
- **Audio prompt**: Gentle marimba-like tones at each node illumination. Pad continues.

### Scene 3 -- Quality (12s-18s)
- **Visual**: Split screen comparison again -- fast fashion tearing after 5 washes vs ReForm garment still pristine after 50 washes (labelled). Macro close-up of fabric weave transitioning from loose/synthetic to tight/organic. Center word: "QUALITY" with description: "Designed to last. Guaranteed for life."
- **Animation**: Left side degrades (desaturates, tears appear via CSS clip-path animation). Right side remains pristine. Macro fabric morphs between textures via crossfade. Word drops at 15s.
- **Audio prompt**: Subtle fabric rustle ASMR. Satisfying "snap" when the word reveals. Warm bass note.

### Scene 4 -- Community (18s-24s)
- **Visual**: Human-centric. A mosaic grid of 16 portrait placeholders (minimal illustrated style, diverse). They populate one by one. Center word: "COMMUNITY" with "45,000+ members and growing." Organic blob shapes pulse gently behind the word.
- **Animation**: Portraits populate in a wave pattern (top-left to bottom-right, stagger 0.08s each). Grid completes, then center word scales in. Blob shapes breathe with a slow sine ease.
- **Audio prompt**: Layered voices (indistinct, warm murmur). Music shifts to a more upbeat, communal feel. Acoustic guitar joins.

### Scene 5 -- Future (24s-30s)
- **Visual**: Full-screen warm off-white. ReForm logo builds center. "FUTURE" appears above the logo. Stats ticker at the bottom: "Net Zero by 2030" / "Circular by Design" / "100% Recyclable Packaging". Final line: "Wear the change." Fade to white.
- **Animation**: Logo draws on (SVG stroke or opacity build). Each stat slides in from right, holds 1.2s, slides left. Final tagline fades in centered. Fade to white over final 0.8s.
- **Audio prompt**: Music resolves. Final held note. Clean silence at 29.8s.

## 5. Technical Preferences

### Animation Engine
- **GSAP 3** (CDN) for timeline, stagger, and counter animations
- **CSS animations** for continuous blob breathing and subtle background movement
- **CSS clip-path** for degradation effects in Scene 3

### HyperFrames Conventions
- Use `data-composition-id` on each scene container
- Use `data-start` and `data-duration` for timeline intent
- Organic blob shapes as absolutely-positioned decorative elements

### Effects
- **Split screen**: Two divs with `width: 50%` and a 2px sage divider
- **Dotted line draw**: SVG `<path>` with `stroke-dasharray` / `stroke-dashoffset` animated by GSAP
- **Blob shapes**: CSS `border-radius` with asymmetric values or inline SVG paths, with slow GSAP morph / scale animation
- **Counters**: GSAP number tween on proxy object, same pattern as company-origin template

## 6. Reference

### Style References
- Allbirds / Everlane brand films -- clean, transparent, modern
- Patagonia "Worn Wear" -- authentic, purpose-driven
- Apple environmental initiative keynotes -- crisp, minimal, data-backed

### Code Reference (sample aesthetic anchor)
```html
<div data-composition-id="value-reveal" style="
  position: absolute; inset: 0;
  background: #FBF7F4;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  gap: 20px;
">
  <h1 style="font: 800 120px 'Inter'; color: #2D4A22; letter-spacing: -4px; margin: 0;">
    SUSTAINABILITY
  </h1>
  <p style="font: 400 24px 'Inter'; color: #1A3A14; margin: 0; text-align: center; max-width: 700px;">
    78% less water. 62% less carbon. 100% more future.
  </p>
  <div style="position: absolute; width: 400px; height: 400px; background: rgba(140,179,105,0.08); border-radius: 60% 40% 70% 30% / 40% 60% 30% 70%; top: -80px; right: -100px; pointer-events: none;"></div>
</div>
```
