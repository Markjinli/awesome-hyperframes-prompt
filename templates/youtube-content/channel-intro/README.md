# YouTube Channel Intro — "DeepTech"

> 15-second high-energy channel intro for a tech review channel. Bold red-and-black aesthetic, rapid product montage, logo explosion, and schedule lockup. MKBHD / LTT energy at 128 BPM.

---

## Use Cases

- YouTube channel intros and bumpers
- Tech / gaming / review channel branding
- Podcast or livestream openers
- Content creator brand identity videos
- Video series title sequences

---

## Key Techniques

| Technique | Where | Why |
|-----------|-------|-----|
| **Rapid-fire product montage** | Scene 1 | 6 products flash in 6 seconds at 128 BPM -- beat-synced cuts with scale bursts and 2-frame white flashes |
| **Diagonal accent slashes** | Scene 1, Scene 3 | 2px #FF0050 lines at 45deg sweep across frame -- aggressive geometric energy |
| **GSAP SplitText stagger** | Scene 2 | Each letter of "DEEPTECH" scales in individually at 0.04s stagger with `elastic.out` -- explosive brand reveal |
| **Logo elastic reveal** | Scene 2 | Scale `0 -> 1.15 -> 1` with `elastic.out(1, 0.4)` + continuous pulse and glow oscillation |
| **Horizontal wipe text** | Scene 3 | "EVERY TUESDAY & FRIDAY" reveals via `clip-path` left-to-right wipe -- bold schedule announcement |
| **Counter roll-up** | Scene 3 | "500K+" subscribers counts up from 0 with GSAP `snap` -- social proof |
| **Background grid** | Global | Subtle grid at `rgba(255,255,255,0.03)` with slow pan -- tech texture |
| **Beat-synced timing** | All scenes | Every cut, stagger, and accent line is mapped to the 128 BPM beat -- maximum energy, zero dead air |

---

## Customization

1. Replace `"DeepTech"` / `"DEEPTECH"` with your channel name
2. Update tagline `"Deeper reviews. Smarter choices."`
3. Swap the 6 product references (Scene 1) with your content niche
4. Change schedule `"EVERY TUESDAY & FRIDAY"` and subscriber count `"500K+"`
5. Update handle `"@deeptech"` and platform badges
6. Adjust brand color: `#FF0050` (brand red) -> your channel's signature color
7. Replace product image references with your own photography or renders

---

## Template Metadata

- **Category**: YouTube Content
- **Subcategory**: Channel Intro / Bumper
- **Format**: 16:9 Horizontal (1920x1080)
- **Duration**: 15s (3 scenes)
- **Difficulty**: Intermediate -- requires SplitText or manual letter-span wrapping
- **Animation Engine**: GSAP 3
- **Fonts**: Inter (Google Fonts)
- **Blocks suggested**: `product-showcase`, `logo-reveal`, `social-overlay`
