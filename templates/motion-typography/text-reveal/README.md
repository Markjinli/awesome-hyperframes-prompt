# Text Reveal Montage — Manifesto / Brand Statement

> 15-second text reveal montage demonstrating 5 distinct animation techniques. Pure typography on black void with a single red accent. No images, no logos -- just text and motion.

---

## Use Cases

- Brand manifesto and values statement videos
- Creative agency and studio showreel openers
- Product philosophy / "why we exist" videos
- Event opening sequences with bold messaging
- Typography-focused design portfolio pieces

---

## Key Techniques

| Technique | Where (Block #) | Why |
|-----------|-----------------|-----|
| **Typewriter** | Block 1 (0-3s) | Character-by-character reveal with 0.06s stagger + blinking red cursor + mechanical keystroke sync |
| **Glitch / Chromatic Aberration** | Block 2 (3-6s) | Three overlapping text layers in different colors with random position jitter, slice displacement, and color channel swaps -- VHS-tracking-error aesthetic |
| **Horizontal Wipe** | Block 3 (6-9s) | Red 2px line sweeps left-to-right revealing text via `clip-path: inset()` driven by GSAP-tweened CSS variable |
| **Scale Rush** | Block 4 (9-12s) | Text rushes from `scale(0.1)` to `scale(1.03)` with `power4.out` deceleration + letter-spacing collapse -- dramatic approach |
| **Layered Echo** | Block 5 (12-15s) | Three layers of the same text (blurred echo, semi-sharp, sharp) stack and peel away -- depth and resolution metaphor |
| **Red accent system** | Throughout | #FF3366 used sparingly for emphasis words, punctuation rules, and the wipe line -- maximum impact from minimal color |

---

## Customization

1. Replace all 5 text blocks with your own manifesto lines
2. Adjust which words get the red accent treatment in each block
3. Modify glitch intensity: jitter ranges, slice frequency, color swap timing
4. Tune wipe speed: 2s sweep can be faster (1.2s) or slower (3s)
5. Adjust scale rush: starting scale (0.1), ending overshoot (1.03), letter-spacing range
6. Change accent color `#FF3366` -> your brand accent
7. Add or remove text blocks by following the same `<div>` + GSAP timeline pattern

---

## Template Metadata

- **Category**: Motion Typography
- **Subcategory**: Text Reveal Montage
- **Format**: 16:9 Horizontal (1920x1080)
- **Duration**: 15s (5 blocks)
- **Difficulty**: Advanced -- requires 5 distinct animation systems in one composition
- **Animation Engine**: GSAP 3
- **Fonts**: Inter + JetBrains Mono (Google Fonts)
- **Blocks suggested**: `text-typewriter`, `text-glitch`, `chromatic-aberration`
