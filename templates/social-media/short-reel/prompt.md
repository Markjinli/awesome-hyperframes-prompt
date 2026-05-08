# Short Reel — Day in the Life Creator Content

> 15-second vertical short video (TikTok / Reels / Shorts), fast-cut creator vlog style.

---

## 1. Video Specs

- **Duration**: 15s
- **Resolution**: 1080 x 1920 (9:16 vertical)
- **Frame rate**: 30fps
- **Orientation**: Portrait / vertical

---

## 2. Visual System

- **Primary**: `#FF6B35` (vibrant orange — energy, warmth, call-to-action accents)
- **Secondary**: `#F7DC6F` (sunny yellow — text highlights, badge backgrounds)
- **Background**: `#1A1A2E` (deep navy — contrast backdrop for overlays) or `#FFFFFF` (clean daytime scenes)
- **Accent**: `#FFFFFF` (white text on dark scenes)
- **Font stack**: `'Inter', system-ui, sans-serif` — titles in 700–900 weight, body in 400–500
- **Vibe keywords**: energetic, authentic, trendy, youthful, fast-paced

---

## 3. Scene Timeline

| Scene | Time   | Visual                                                     | Animation                                     |
|-------|--------|------------------------------------------------------------|-----------------------------------------------|
| 1     | 0–3s   | Bold hook text on vibrant gradient background (#FF6B35 → #1A1A2E). "A DAY IN MY LIFE" in 72px Extrabold, white. Subtle grain overlay. | Text scales from 0.8→1 with overshoot (back.out). Background pulses gently. |
| 2     | 3–7s   | Split-screen or quick-cut montage: 3 vignettes (morning routine / workspace / creative). Each vignette is a rounded card with a short label ("7:00 AM ☀️", "Deep Work 🖥️", "Create ✨"). Cards stacked vertically with 24px gap. | Stagger entrance: cards slide in from right one-by-one, each 0.15s apart. Active card gets a subtle yellow border pulse. |
| 3     | 7–11s  | Bold typography overlay: a short creator tip or quote. Large text (56px) in #F7DC6F on dark background. Below it, a secondary line in smaller white text (28px). | Typewriter stagger reveal on the main line (chars appear 0.03s apart). Subtitle fades up after a 0.3s delay. |
| 4     | 11–15s | Outro: circular profile photo placeholder (180px) centered, handle "@creator" below it in #FF6B35, followed by "Follow for more" CTA with a subtle pulse ring animation. | Photo scales in with elastic ease. Handle fades up. Pulse ring loops on CTA. Fade-to-black at 14.5s. |

---

## 4. Animation Requirements

- **Entrance animations**: Scale-up with overshoot (back.out), slide-in from right/left, fade-up
- **Transitions between scenes**: Quick crossfade (0.3s). Scene N fades out starting 0.15s before scene N+1 fades in.
- **Continuous animations**: Subtle background float, CTA pulse ring (infinite yoyo scale 1→1.04)
- **Text reveals**: GSAP SplitText-style stagger (each character fades in, 0.02–0.03s stagger)
- **Timing principle**: Fast in, settle briefly, cut to next. No scene feels static for more than 0.8s.

---

## 5. Audio Design

- **Background music**: Lo-fi hip-hop or upbeat synth-pop, 90–110 BPM, energetic but not overwhelming
- **Sound effects**: Soft "whoosh" on scene transitions (0.1s), subtle "pop" on each card entrance (scene 2)
- **Voiceover**: None (text-driven content)
- **Music ducking**: BGM volume dips to 30% during scene 3 text reveal so the typography feels prominent

---

## 6. Technical Constraints

- **Animation engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **HyperFrames blocks**: `grain-overlay` (global texture), `logo-outro` (customized for scene 4)
- **HyperFrames data attributes**: Use `data-composition-id`, `data-start`, `data-duration`, `data-track-index`
- **Font loading**: Google Fonts — Inter (weights 400, 600, 700, 900)
- **Responsive**: Clamp-based font sizing where possible, but primary target is 1080×1920
- **Performance**: Animate only `transform` and `opacity`; no layout-triggering properties

---

## 7. Content Variables (replace these)

| Placeholder          | Default               | Your Value |
|----------------------|-----------------------|-------------|
| `{{CREATOR_HANDLE}}` | `@creator`            |             |
| `{{HOOK_TEXT}}`      | `A DAY IN MY LIFE`    |             |
| `{{TIP_TEXT}}`       | `Create every day.`   |             |
| `{{TIP_SUBTEXT}}`    | `Consistency > talent`|             |
| `{{PROFILE_PHOTO}}`  | `https://placehold.co/180x180/FF6B35/white?text=ME` | |

---

## 8. Reference Notes

- **Style reference**: TikTok "day in my life" trends (fast cuts, bold yellow/white text, lo-fi audio)
- **Animation reference**: Apple keynote text reveals for stagger timing; Instagram Reels text overlay pop-ins
- **Avoid**: Slow dissolves, subtle opacity-only transitions — this format rewards snappy, visible motion
