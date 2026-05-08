# Instagram Story Ad — Glow Skin D2C Beauty Brand

> Elegant 15-second Instagram Story advertisement for a direct-to-consumer skincare brand. Soft, premium, product-centric.

---

## Effect Preview

A 15-second vertical Instagram Story (1080x1920) that feels like a deep exhale. Four breathable scenes: an elegant brand intro with shimmering typography, a product hero shot with floating badge callouts, a social-proof review with animated 5-star rating, and a gentle CTA with a pulsing "Shop Now" button. The visual language is warm and premium — blush creams (#F8E8E0), taupe golds (#D4A574), and Playfair Display serifs that evoke Diptyque / Glossier / Rhode beauty aesthetics.

---

## Use Cases

- D2C skincare / beauty brand Instagram Stories
- Cosmetic product launch teasers
- Wellness and self-care brand promotions
- Spa / salon service advertisements
- Luxury e-commerce product spotlights
- Influencer brand collaboration Stories

---

## Key Techniques

| Technique | Where | Why |
|-----------|-------|-----|
| **Slow crossfade** | Between all scenes | 0.6–0.8s crossfades with intentional overlap create a dreamy, editorial blend — the opposite of fast cuts |
| **Gentle float** | Product bottle (scene 2) | A 3s yoyo sine float (y: ±4px) adds life to the product shot without distracting from the bottle's premium feel |
| **Shimmer sweep** | Brand name (scene 1) | A diagonal gloss sweep across "GLOW SKIN" at 2.5s mimics light hitting a product bottle — subtle luxury cue |
| **Staggered star pop** | Review stars (scene 3) | Each star scales in with `back.out` 0.1s apart — satisfying, gamified social proof |
| **Pill badge reveals** | Benefits (scene 2) | Rounded pill containers stagger up from the bottom — clean, readable, very Instagram-native |
| **Serif + sans-serif hierarchy** | Throughout | Playfair Display for brand/emotional text, Inter for functional text — creates clear information hierarchy |
| **Soft glow effects** | Product, CTA button | Box-shadow and pseudo-element glows give depth on light backgrounds without harsh drop shadows |

---

## GSAP Patterns Used

```js
// Scene 1: Elegant fade-up for brand name
gsap.fromTo('#brand-name',
  { opacity: 0, y: 30 },
  { opacity: 1, y: 0, duration: 0.8, ease: 'power3.out' }
);

// Scene 2: Product bottle float loop
gsap.to('#product-bottle', {
  y: -4,
  duration: 3,
  repeat: -1,
  yoyo: true,
  ease: 'sine.inOut'
});

// Scene 3: Star rating sequential pop
gsap.fromTo('.star',
  { scale: 0, opacity: 0 },
  { scale: 1, opacity: 1, duration: 0.3, stagger: 0.1, ease: 'back.out(2)' }
);

// Scene 4: CTA button gentle pulse
gsap.to('#cta-button', {
  scale: 1.03,
  duration: 2,
  repeat: -1,
  yoyo: true,
  ease: 'sine.inOut'
});

// Ornament lines: draw-in effect
gsap.fromTo('.ornament-line',
  { scaleX: 0 },
  { scaleX: 1, duration: 0.6, ease: 'power2.inOut', delay: 0.5 }
);
```

---

## Customization Tips

1. **Swap product image**: Replace `{{PRODUCT_IMAGE}}` with your actual bottle shot. Ensure it has a transparent or cream background to blend with #F8E8E0.
2. **Adjust pacing**: If your product needs more screen time, extend scene 2 from 6s to 8s (shift scenes 3 and 4 forward).
3. **Brand fonts**: If Playfair Display doesn't match your brand, swap to another elegant serif — Cormorant Garamond, Lora, or your custom typeface.
4. **Color harmony**: Keep the cream + gold palette but shift warmth. Cooler brand? Use #EBF0F4 + #7B9EB3. Warmer? Use #FDF0E5 + #C4825A.
5. **Add a product video clip**: Instead of a static bottle, embed a short looping video (pouring, applying texture) behind the text overlays in scene 2.

---

## Instagram Story Considerations

- **Safe zones**: Keep text within 420px from top and bottom edges (IG UI elements overlay these areas)
- **Duration**: 15s is the maximum for a single Story card; for longer content, chain multiple Story cards
- **Sound**: IG Stories autoplay with sound ON by default — your audio design matters
- **Swipe-up**: If you have the swipe-up feature, increase the arrow animation's prominence in scene 4
- **A/B test**: Create 2–3 variants with different product shots or headlines and test engagement

---

## Rendering

```bash
# Preview in browser (check safe zones at 1080x1920)
npx hyperframes preview

# Export to MP4
npx hyperframes render --output ig-story-glow-skin.mp4
```

---

## Template Metadata

- **Category**: Social Media
- **Subcategory**: Instagram Story Ad
- **Format**: 9:16 Vertical (1080x1920)
- **Duration**: 15s
- **Difficulty**: Intermediate — requires careful pacing and aesthetic sensibility
- **Animation Engine**: GSAP 3
- **HyperFrames Version**: Compatible with latest
