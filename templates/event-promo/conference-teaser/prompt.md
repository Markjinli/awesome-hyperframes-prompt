# Conference Teaser -- NeonConf 2026

## 1. Video Specs
- **Duration**: 20s
- **Resolution**: 1920x1080
- **Frame rate**: 30fps
- **Aspect ratio**: 16:9 landscape

## 2. Visual System

### Color Palette
- **Primary Neon Pink**: #FF00FF (magenta, use as glow accent)
- **Secondary Neon Cyan**: #00FFFF (electric blue, use as secondary glow)
- **Background**: #0A0A0A (near-black, with subtle radial gradient)
- **Surface / Card BG**: #111118 (very dark purple-gray)
- **Text white**: #FFFFFF (clean contrast on dark)

### Typography
- **Headlines / Speaker names**: JetBrains Mono Bold or Space Mono Bold, 64-80px, letter-spacing: -1px, neon glow
- **Subhead / Role**: Inter Medium, 18px, letter-spacing: 4px, uppercase, #00FFFF
- **Date / venue reveal**: JetBrains Mono, 48px, #FF00FF
- **Glitch text**: Duplicate offset text layers (pink + cyan) for chromatic aberration glitch

### Atmosphere Keywords
High-energy, cyberpunk, futuristic, neon-noir, electric, urgent, exclusive

### Design Language
- Dark backgrounds with radial glow spots behind key elements
- Neon text glow via `text-shadow` with CSS `box-shadow` on containers
- Glitch/chromatic aberration effects (CSS `text-shadow` offsets)
- Fast cuts (0.3-0.5s scene transitions)
- Grid lines / scanlines in background
- Circuit-board-like thin line decorations
- Speaker photo reveals with neon border glow
- Countdown / date reveal finale

## 3. Event Details
- **Event name**: NeonConf 2026
- **Date**: November 12-14, 2026
- **Venue**: The Venue, San Francisco
- **Theme**: "The Future is Electric"
- **Speakers**: Dr. Aria Chen (AI Ethics, Stanford), Marcus Webb (CEO, SynthWave), Elena Rodriguez (CTO, QuantumLeap), Jay Park (Design Lead, Neuralab)
- **Tagline**: "Three days. Infinite futures."

## 4. Scene Timeline

### Scene 1 -- Logo Sting + Date (0s-2.5s)
- **Visual**: Black screen. NeonConf 2026 logo (text-based, JetBrains Mono Bold) bursts center with a pink-to-cyan gradient glow. Glitch effect on the logo over 0.3s. Date line appears below: "11.12 -- 11.14.26"
- **Animation**: Logo scales in from 0 to 1 with bounce easing, accompanied by a CSS glow pulse. Glitch happens at 0.8s for 0.2s (duplicate layers shift). Date types on below.
- **Audio prompt**: Deep sub-bass hit at 0s. Electronic riser. Glitch stutter sound at 0.8s.

### Scene 2 -- Venue Teaser (2.5s-5s)
- **Visual**: Dark abstract venue visualization -- geometric wireframe architecture, sweeping aerial feel. Overlay text: "SAN FRANCISCO" in cyan. Subtle grid lines recede into perspective. Scan line pass sweeps top to bottom.
- **Animation**: Wireframe draws on via SVG stroke animation over 2s. Text fades in with glow. Scan line sweeps. Crossfade transition in from Scene 1 (0.3s).
- **Audio prompt**: Deep house kick joins. Atmospheric pad. Sweep sound effect with scan line.

### Scene 3 -- Speaker Reveal: Aria Chen (5s-8s)
- **Visual**: Split composition. Left 40%: circular photo placeholder with magenta neon border glow, pulsing gently. Right 60%: speaker name "Dr. Aria Chen" in JetBrains Mono, role "AI ETHICS / STANFORD" in cyan uppercase below. Grid lines background.
- **Animation**: Photo container scales in from center (0.6s). Name slides in from right (0.5s). Glitch flicker at 6.5s for 0.15s. Fast crossfade out at 8s.
- **Audio prompt**: Voice sample snippet "The future of intelligence..." (1s). Electronic snap at name reveal.

### Scene 4 -- Speaker Reveal: Marcus Webb (8s-11s)
- **Visual**: Same layout pattern as Scene 3. Faster reveal. Photo left, name "Marcus Webb" right, role "CEO / SYNTWAVE" in cyan. Slightly different glow color -- cyan border this time.
- **Animation**: Photo pops in faster (0.4s). Name slides from bottom (0.4s). Quick glitch at 9.5s.
- **Audio prompt**: Voice sample "Building the platform..." (1s). Bass hit.

### Scene 5 -- Speaker Reveal (Rapid Fire): Elena + Jay (11s-15s)
- **Visual**: Two speakers shown in rapid succession. Elena Rodriguez ("CTO / QUANTUMLEAP") at 11s-13s. Jay Park ("DESIGN LEAD / NEURALAB") at 13s-15s. Each is a fast cut.
- **Animation**: Each speaker gets 2s -- photo scale+bounce in (0.3s), name whip from side (0.25s), quick role reveal, immediate cut to next. Glitch transition between the two at 13s.
- **Audio prompt**: Quick-cut electronic stabs. Voice samples very short (0.5s each).

### Scene 6 -- Countdown + CTA (15s-20s)
- **Visual**: Full screen black. Center countdown: "11.12.26" in giant JetBrains Mono, 140px, magenta glow. Below: "SAN FRANCISCO" in cyan. Below that: "TICKETS AT NEONCONF.IO" with subtle underline animation. Grid and scanlines active. Pulsing glow ring around the date.
- **Animation**: Date scales up from 0.5 to 1 (1.2s, heavy bounce ease). Venue name fades up. CTA types on below. Glow ring pulses 3 times (1s apart). Final glitch at 19.2s. Cut to black at 20s.
- **Audio prompt**: Music peaks. Kick drum builds. Final bass drop at 15s. Fade out over last 2s.

## 5. Technical Preferences

### Animation Engine
- **GSAP 3** (CDN) for scene timeline and all entrance/exit animations
- **CSS @keyframes** for continuous glow pulsing, scanline animation, and grid movement
- **CSS text-shadow** for neon glow and glitch effects

### HyperFrames Conventions
- Use `data-composition-id` on each scene container
- Use `data-start` and `data-duration` for timeline intent
- Fast crossfades between scenes (0.3-0.5s each)

### Effects
- **Neon glow**: Multiple `text-shadow` layers: 0 0 7px, 0 0 10px, 0 0 21px, 0 0 42px, 0 0 82px at various opacities
- **Glitch text**: Pseudo-elements with `text-shadow` offset in pink/cyan, briefly activated via class toggle
- **Scanlines**: CSS `repeating-linear-gradient` overlay animated with `@keyframes`
- **Grid background**: `background-image` with `linear-gradient` for horizontal and vertical lines on a dark surface
- **Glow pulse ring**: CSS `box-shadow` on a circular container, animated scale

## 6. Reference

### Style References
- Cyberpunk 2077 promotional key art -- neon, dark, high contrast
- Blade Runner 2049 title sequences -- bold typography, atmospheric
- Tomorrowland / EDC trailers -- fast cuts, speaker reveals, venue shots
- Google I/O opening sizzle reels -- tech conference energy

### Code Reference (sample glitch text CSS)
```css
.glitch-text {
  position: relative;
  color: #FF00FF;
  text-shadow:
    0 0 7px #FF00FF,
    0 0 10px #FF00FF,
    0 0 21px #FF00FF,
    0 0 42px rgba(255,0,255,0.5);
}
.glitch-text::before,
.glitch-text::after {
  content: attr(data-text);
  position: absolute;
  top: 0; left: 0;
  opacity: 0;
}
.glitch-text.active::before {
  color: #00FFFF;
  text-shadow: 2px 0 #00FFFF, -2px 0 #FF00FF;
  opacity: 0.8;
  animation: glitchSkew 0.2s ease;
}
@keyframes glitchSkew {
  0% { transform: translate(0); }
  25% { transform: translate(-4px, 2px); }
  50% { transform: translate(4px, -1px); }
  75% { transform: translate(-2px, -2px); }
  100% { transform: translate(0); }
}
```
