# Short Reel — Day in the Life

> TikTok / Reels / Shorts vertical video template. Fast-paced creator vlog style with bold typography and vibrant social-media aesthetic.

---

## Effect Preview

A 15-second vertical video (1080x1920) in the "day in my life" creator format. Four rapid scenes: an attention-grabbing hook title, a staggered card montage showing daily vignettes, a bold typography quote reveal, and a CTA outro with profile photo and follow prompt. The visual language uses vibrant orange (#FF6B35) and sunny yellow (#F7DC6F) against deep navy backgrounds, with fast cuts and GSAP-powered stagger text reveals.

---

## Use Cases

- Personal brand / creator daily vlogs
- TikTok "day in the life" trends
- Instagram Reels for lifestyle influencers
- YouTube Shorts intro sequences
- Behind-the-scenes content teasers
- Event recap highlights (3–4 key moments)

---

## Key Techniques

| Technique | Where | Why |
|-----------|-------|-----|
| **Stagger text reveal** | Scene 3 (quote), Scene 1 (hook chars) | Creates that "typewriter" social media feel — each character pops in, matching trending audio beats |
| **Scale overshoot** | Scene 1 title, Scene 4 profile photo | `back.out` easing adds energy and makes entries feel "alive" rather than mechanical |
| **Fast crossfade transitions** | Between all scenes | 0.3s crossfades keep the pace snappy — the social media audience has short attention spans |
| **Vertical card layout** | Scene 2 vignette cards | Stacked cards with 24px gap match the 9:16 phone-screen browsing pattern |
| **Pulse ring CTA** | Scene 4 | Subtle infinite pulse keeps the follow CTA "breathing" without being distracting |
| **Bold high-contrast typography** | Throughout | 72px Extrabold headlines on dark backgrounds ensure readability even when autoplaying without sound |

---

## GSAP Patterns Used

```js
// Scene 1: Title scale entrance with overshoot
gsap.fromTo('#scene1-title', 
  { scale: 0.8, opacity: 0 },
  { scale: 1, opacity: 1, duration: 0.7, ease: 'back.out(1.7)' }
);

// Scene 2: Staggered card slide-in
gsap.fromTo('.vignette-card',
  { x: 80, opacity: 0 },
  { x: 0, opacity: 1, duration: 0.4, stagger: 0.15, ease: 'power2.out' }
);

// Scene 3: Character-by-character typewriter
gsap.fromTo('#quote-text .char',
  { opacity: 0, color: '#F7DC6F' },
  { opacity: 1, duration: 0.02, stagger: 0.03 }
);

// Scene 4: Infinite CTA pulse
gsap.to('#cta-pulse', {
  scale: 1.04,
  duration: 1.5,
  repeat: -1,
  yoyo: true,
  ease: 'sine.inOut'
});
```

---

## Customization Tips

1. **Swap the hook text** for your niche: fitness → "MY 5AM WORKOUT", coding → "BUILDING A STARTUP", food → "WHAT I EAT IN A DAY"
2. **Replace vignette cards** with your actual daily-moment screenshots or short video clips
3. **Match the audio BPM** — if your trending track is faster (>120 BPM), tighten scene durations (scene 1: 0–2s, scene 2: 2–6s, scene 3: 6–10s, scene 4: 10–15s)
4. **Adjust brand colors** in the `:root` variables at the top of index.html — keep high contrast for readability

---

## Rendering

```bash
# Preview in browser
npx hyperframes preview

# Export to MP4
npx hyperframes render --output short-reel.mp4
```

---

## Template Metadata

- **Category**: Social Media
- **Subcategory**: Short Reel / TikTok
- **Format**: 9:16 Vertical
- **Duration**: 15s
- **Difficulty**: Beginner — good first HyperFrames project
- **Animation Engine**: GSAP 3
- **HyperFrames Version**: Compatible with latest
