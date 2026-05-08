# Product Launch Event Opener -- Keynote Style

## 1. Video Specs
- **Duration**: 30s
- **Resolution**: 1920x1080
- **Frame rate**: 30fps
- **Aspect ratio**: 16:9 landscape

## 2. Visual System

### Color Palette
- **Background**: #000000 (true black stage)
- **Primary white**: #F5F5F7 (Apple-style off-white text)
- **Accent silver**: #86868B (secondary text, subtle details)
- **Accent glow**: #2997FF (Apple blue, sparing use for key highlights)
- **Surface**: #1D1D1F (dark gray for spec cards)

### Typography
- **Hero headline**: Inter Extra Bold, 80-100px, letter-spacing: -3px, color: #F5F5F7
- **Product name**: Inter Bold, 60px, letter-spacing: -1px
- **Spec callouts**: Inter SemiBold, 44px, letter-spacing: -0.5px, color: #F5F5F7
- **Spec labels**: Inter Regular, 18px, letter-spacing: 1px, uppercase, color: #86868B
- **Body / taglines**: Inter Regular, 28-32px, color: #F5F5F7, letter-spacing: -0.5px
- **"Available today"**: Inter Bold, 48px, color: #2997FF

### Atmosphere Keywords
Dramatic, premium, suspenseful, sleek, powerful, revealing, Apple-keynote-style

### Design Language
- True black stage with dramatic single-source lighting
- Product silhouette-to-reveal sequence (dark shape gradually illuminated)
- Spec cards with staggered fly-in animations
- Generous negative space (50%+)
- Thin 1px silver dividers
- Tight tracking on all text (-1px to -3px)
- Building intensity through animation timing (scenes get progressively faster)

## 3. Brand / Product Assets
- **Product name**: "Pro X"
- **Category**: Professional creative tool
- **Key specs**:
  - M4 Ultra chip
  - 32-core Neural Engine
  - 64GB unified memory
  - 18-hour battery
  - Liquid Retina XDR display
  - 1TB storage
- **Tagline**: "Power without compromise."
- **Reveal tagline**: "Available today."

## 4. Scene Timeline

### Scene 1 -- Darkness + Build-Up (0s-6s)
- **Visual**: Total black screen. A single point of light (small radial gradient, cool white) appears center-top at 1s, slowly expanding downward like a spotlight powering on. By 3s, the light reveals a dark silhouette of the product (rounded rectangle with metallic edge glints). Subtle particles float in the light beam.
- **Animation**: Spotlight expands from center-top over 2s. Silhouette fades from 0 to 0.3 opacity. Particles drift slowly upward. Text at 4.5s: "Something big is coming." (small, silver).
- **Audio prompt**: Deep sub-bass rumble. Single piano note at 3s. Soft atmospheric pad builds.

### Scene 2 -- The Reveal Begins (6s-12s)
- **Visual**: Silhouette starts to illuminate from left to right, revealing the product's edge profile. Light widens. Product name "Pro X" appears above in 80px white. Silhouette now at 0.7 opacity.
- **Animation**: Product illumination via clip-path reveal (left-to-right). "Pro X" cascades in letter by letter. Spotlight widens to 40% of frame. Tagline "Power without compromise." fades up.
- **Audio prompt**: Music begins. "Pro X" reveal coincides with first kick drum hit.

### Scene 3 -- Spec Fly-In Wave (12s-20s)
- **Visual**: Fully-revealed product at center-bottom. Six spec cards fly in from edges in staggered wave. Each card has glass-morphism treatment (semi-transparent dark bg, 1px silver border).
- **Animation**: Cards fly in from edge positions with 0.5s ease-out, staggered 0.5s apart. Spec value (bold, large) enters first; label follows 0.2s later. Cards have subtle float after landing.
- **Audio prompt**: Electronic click at each card arrival. Music builds with layered percussion.

### Scene 4 -- Climax + CTA (20s-26s)
- **Visual**: Spec cards dissolve. Product shifts upward. Spotlight fills 80% of screen. "Available today." in Apple blue (#2997FF), 48px. "Starting at $1,999" in silver. CTA URL below.
- **Animation**: Product shifts up (y: -30px) while scaling to 1.05x. Cards dissolve. "Available today." scales in with gentle bounce. Price and CTA fade up sequentially.
- **Audio prompt**: Music peaks and resolves. Triumphant chord. Single held note.

### Scene 5 -- Outro (26s-30s)
- **Visual**: Product fades. Spotlight shrinks to center point. Logo remains. Background fades to black. Legal line at bottom edge (tiny text).
- **Animation**: Product dissolves over 1s. Spotlight contracts over 1.5s. Logo holds 1s. Everything fades to black over final 0.8s.
- **Audio prompt**: Music fades to silence. Final note decays. Clean silence at 29.8s.

## 5. Technical Preferences

### Animation Engine
- **GSAP 3** (CDN) for all timeline, stagger, and fly-in animations
- **CSS transitions** for spotlight gradient animations
- **CSS `clip-path`** for the silhouette reveal

### HyperFrames Conventions
- Use `data-composition-id` on each scene container
- Use `data-start` and `data-duration` on every scene
- Tight 0.5s crossfades between compositions

### Effects
- **Spotlight**: Large `radial-gradient` animated with GSAP on size/position
- **Silhouette reveal**: `clip-path: inset()` animated left-to-right
- **Glass spec cards**: `background: rgba(29,29,31,0.7); backdrop-filter: blur(20px); border: 1px solid rgba(255,255,255,0.1)`
- **Light particles**: Multiple small `div` elements animated with random GSAP tweens
- **Metallic glint**: CSS `linear-gradient` with white-to-transparent stripe sweeping across product

## 6. Reference

### Style References
- Apple WWDC / iPhone keynote openers -- dramatic lighting, silhouette reveals, spec fly-ins
- Tesla Cybertruck reveal -- dark stage, dramatic spotlight
- Nothing (Nothing.tech) product launch events -- minimalist, clean

### Code Reference (sample spotlight + silhouette)
```html
<div data-composition-id="product-reveal" style="
  position: absolute; inset: 0;
  background: radial-gradient(ellipse 600px 400px at 50% 20%, rgba(255,255,255,0.08) 0%, transparent 70%),
              #000000;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  gap: 30px;
">
  <div style="
    width: 500px; height: 320px;
    background: linear-gradient(180deg, rgba(255,255,255,0.06) 0%, rgba(255,255,255,0.02) 100%);
    border-radius: 24px;
    border: 1px solid rgba(255,255,255,0.08);
    box-shadow: 0 0 120px rgba(41,151,255,0.15);
  "></div>
  <h1 style="font: 800 80px 'Inter'; color: #F5F5F7; letter-spacing: -3px;">
    Pro X
  </h1>
</div>
```
