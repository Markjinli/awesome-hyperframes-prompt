# Social Media Ad — CoinFlow Fintech App

> 30-second horizontal social ad for a fintech product. High-energy, data-driven, trust-forward. Built for YouTube pre-roll and in-feed video placements.

---

## Effect Preview

A 30-second horizontal video (1920x1080) that takes viewers through a four-scene narrative: a massive animated user counter hook, a problem-vs-solution comparison with card-flip mechanics, a three-column social-proof section with animated star ratings and trust badges, and a gradient-powered CTA finale. The visual language blends electric violet (#6C3CE1) with mint green (#00D4AA) against deep navy backgrounds — a fintech palette that signals innovation and trust simultaneously.

---

## Use Cases

- Fintech app install ads (YouTube, Facebook, LinkedIn)
- SaaS product launch videos
- Investment / trading platform promotions
- B2B fintech awareness campaigns
- App Store / Google Play acquisition ads
- Conference or pitch-deck intro videos
- Any data-heavy product that needs to build rapid trust

---

## Key Techniques

| Technique | Where | Why |
|-----------|-------|-----|
| **Counter roll-up animation** | Scene 1 | Large number (2.4M+) animates from 0 in 1.8s — social proof feels earned, not just stated. Use GSAP `snap` for clean integer ticks. |
| **Problem → Solution card flip** | Scene 2 | Pain points slide in with red ✕, then a horizontal wipe reveals green ✓ solutions. Clear before/after narrative. |
| **Staggered trust badge reveal** | Scene 3 | Three columns of social proof (ratings, press, security) stagger in 0.15s apart — each badge builds cumulative trust. |
| **Star rating fill** | Scene 3 | Stars fill left to right like a progress bar — gamified social proof that's more engaging than a static "4.8" number. |
| **Gradient CTA with pulse** | Scene 4 | Diagonal brand gradient (#6C3CE1 → #00D4AA) signals climax. CTA button pulses gently — noticeable but not aggressive. |
| **Grid pattern backgrounds** | Scenes 1, 3 | Subtle CSS grid patterns add "data/tech" texture without visual clutter. |

---

## GSAP Patterns Used

```js
// Scene 1: Counter animation from 0 to 2,438,921
gsap.fromTo('#user-counter',
  { textContent: 0 },
  {
    textContent: 2438921,
    duration: 1.8,
    snap: { textContent: 1 },
    ease: 'power2.out',
    onUpdate: function () {
      const el = this.targets()[0];
      el.textContent = Math.round(el.textContent).toLocaleString();
    }
  }
);

// Scene 2: Pain points stagger slide
gsap.fromTo('.pain-point',
  { x: -60, opacity: 0 },
  { x: 0, opacity: 1, duration: 0.4, stagger: 0.12, ease: 'power2.out' }
);

// Scene 3: Trust cards scale-in with stagger
gsap.fromTo('.trust-card',
  { scale: 0.85, opacity: 0 },
  { scale: 1, opacity: 1, duration: 0.5, stagger: 0.15, ease: 'back.out(1.4)' }
);

// Scene 3: Star rating fill (5 stars, left to right)
gsap.fromTo('.star-fill',
  { width: '0%' },
  { width: '100%', duration: 0.4, stagger: 0.08, ease: 'power2.out' }
);

// Scene 4: CTA button infinite pulse
gsap.to('#cta-button', {
  scale: 1.04,
  duration: 1.8,
  repeat: -1,
  yoyo: true,
  ease: 'sine.inOut'
});
```

---

## Customization Tips

1. **Swap counter number**: Update the `USER_COUNT` variable. The GSAP counter code handles `toLocaleString()` formatting automatically.
2. **Adjust pain points**: Replace the 3 pain points with your market's specific friction — finance (fees, speed, UX), health (confusion, access, cost), productivity (complexity, sync, pricing).
3. **Trust badges**: Replace placeholder logos with your actual press mentions, security certifications (SOC2, GDPR), and app store ratings.
4. **Scene 2 pacing**: If your product has more problems to highlight, extend to 12s (shift scenes 3 and 4 forward). For simpler products, cut to 8s.
5. **CTA variations**: A/B test CTA text — "Get Started Free" vs "Try CoinFlow" vs "Join 2M+ Users" — the template supports easy text swapping.
6. **Dark/light mode**: The template alternates dark (scenes 1, 4) and light (scene 3) backgrounds. Adjust the ratio depending on your brand's primary mode.

---

## Platform-Specific Notes

| Platform | Aspect Ratio | Max Duration | Key Concern |
|----------|-------------|--------------|-------------|
| YouTube Pre-roll | 16:9 | 30s (skippable after 5s) | Hook MUST land in first 5s — scene 1 counter is designed for this |
| Facebook Feed | 16:9 or 1:1 | 240 min (but <30s recommended) | Autoplay without sound — text overlays are critical |
| Instagram Feed | 4:5 or 1:1 | 60s | Consider rendering a 1:1 crop version for IG |
| LinkedIn Feed | 16:9 | 30s | Professional tone — reduce pulse/glow intensity slightly |

---

## Rendering

```bash
# Preview the full 30s ad
npx hyperframes preview

# Export horizontal MP4
npx hyperframes render --output coinflow-social-ad.mp4

# (Optional) Render a 1:1 crop for Instagram feed
# Adjust composition dimensions to 1080x1080 and re-render
```

---

## Template Metadata

- **Category**: Social Media
- **Subcategory**: Social Ad / Fintech
- **Format**: 16:9 Horizontal (1920x1080)
- **Duration**: 30s
- **Difficulty**: Intermediate — requires GSAP counter animation and multi-scene orchestration
- **Animation Engine**: GSAP 3
- **HyperFrames Version**: Compatible with latest
