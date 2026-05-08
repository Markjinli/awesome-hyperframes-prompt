# Video Essay Opener — "The Death of the Internet"

> 20-second documentary-style video essay opener. Dark academia aesthetic, archive imagery, provocative questioning. Built with the 6-dimension HyperFrames prompt formula.

---

## 1. Video Specs

- **Duration**: 20 seconds
- **Resolution**: 1920 x 1080 (16:9 landscape)
- **Frame rate**: 24 fps (documentary cadence)
- **Output format**: MP4 (H.264), rendered via `npx hyperframes render`

---

## 2. Visual Style

### Color Palette

| Role       | Hex       | Usage                                          |
|------------|-----------|-------------------------------------------------|
| Obsidian   | `#1A1A1A` | Backgrounds, negative space, deep shadows       |
| Antique Gold | `#D4AF37` | Headlines, key quotes, chapter markers, accent lines |
| Parchment  | `#F5F5F0` | Secondary text, image borders, subtle glows     |
| Charcoal   | `#2C2C2C` | Card surfaces, caption backgrounds              |
| Dust       | `#8A8A80` | Muted labels, faded dates, tertiary text        |

### Typography

- **Primary (Display)**: Playfair Display Bold, 700 weight, 56–88 px, `letter-spacing: 0px` — for provocative questions and chapter titles
- **Secondary (Body)**: Playfair Display Regular, 400 weight, 24–32 px, `line-height: 1.5` — for contextual text
- **Tertiary (Captions)**: Inter Regular, 400 weight, 14–16 px, `letter-spacing: 2px`, uppercase, #8A8A80 — for dates, sources, labels
- **Chapter Cards**: Playfair Display Black, 900 weight, 72px — for chapter numbers

### Atmosphere Keywords

Dark academia, archival, intellectual, contemplative, ominous, scholarly, documentary, textured, analog, historical, provocative, measured

### Graphic Language
- Archive photo grid with thin gold borders (1px, #D4AF37, opacity 0.4)
- Chapter cards: large numbers with gold horizontal rule
- Subtle film grain + light leak textures
- Text treated with gravitas — generous whitespace, deliberate isolation
- Vignette on all scenes (radial-gradient, transparent → #1A1A1A at 60%)

---

## 3. Content Structure

- **Essay Title**: The Death of the Internet
- **Subtitle**: "How the open web became a shopping mall — and what we lost."
- **Chapter 1**: The Promise (1995–2005)
- **Chapter 2**: The Capture (2006–2016)
- **Chapter 3**: The Wasteland (2017–now)
- **Guiding Question**: "What happened to the internet we were promised?"

---

## 4. Scene Timeline

### Scene 1 — The Archive Grid (0s – 6s)

- **Visual**: A 3×3 grid of black-and-white or desaturated archive photographs fills the frame. Images depict: early web browsers (Netscape), geocities-style personal pages, USENET diagrams, early blog screenshots, Web 1.0 aesthetics. The images are slightly sepia-toned with uneven borders. A thin gold border outlines each cell. The grid has uneven gaps — some images are slightly rotated (±1deg), creating a scrapbook feel.
- **Animation**: 
  - Grid fades in cell by cell (stagger 0.25s, start from center outward — 5, then 2/4/6/8, then 1/3/7/9)
  - Each cell: scale(0.9) + opacity 0 → scale(1) + opacity 1 (0.6s, power2.out)
  - ~3.5s: All cells slowly begin a Ken Burns drift — some push in (scale 1 → 1.08), others pan (transform-origin shifts). Randomized, organic, subtle.
  - ~5s: Grid begins to fade row by row, starting from the bottom. Cells desaturate further.
- **Audio cue**: The sound of a dial-up modem connecting — an iconic, nostalgic sequence. It begins clean, then distorts slightly under reverb.

### Scene 2 — The Provocative Question (6s – 11s)

- **Visual**: Deep obsidian background (#1A1A1A). The essay's guiding question appears in the center, rendered in Playfair Display, large: "WHAT HAPPENED TO THE INTERNET WE WERE PROMISED?" Text is #F5F5F0 with a faint gold halo. Above and below the question, thin gold horizontal rules (1px, #D4AF37, opacity 0.6) frame the text. The word "PROMISED" is slightly larger and gold-toned.
- **Animation**: 
  - Top rule draws in from left (scaleX 0 → 1, 1.5s, power3.inOut)
  - Question text fades up from darkness (opacity 0 → 1, y: 15px → 0, 2s, power3.out)
  - "PROMISED" receives a delayed highlight — its color transitions from #F5F5F0 to #D4AF37 over 1s (0.5s delay after text appears)
  - Bottom rule draws in from right (scaleX 0 → 1, 1.5s, power3.inOut)
  - Slight continuous breathing scale on text (1 → 1.01, 4s cycle)
- **Audio cue**: The dial-up sound fades. A low, ominous cello drone enters. A single piano key strikes on "PROMISED."

### Scene 3 — The Chapter Cards (11s – 17s)

- **Visual**: Three chapter cards appear in sequence on the obsidian background. Each card is a simple, elegant composition: a large gold chapter number ("I", "II", "III") in Playfair Display Black 900 at 120px, #D4AF37. Beside it, the chapter title in smaller Playfair Display Bold. Below, a one-line description in Playfair Display Regular, #D4AF37 at 60% opacity. Each card occupies the full frame, one at a time.
  - Card 1: "I. THE PROMISE" / "1995–2005"
  - Card 2: "II. THE CAPTURE" / "2006–2016"
  - Card 3: "III. THE WASTELAND" / "2017–now"
- **Animation**: 
  - Each card fades in over 1s, holds for ~2s, fades out over 0.8s (crossfading into the next)
  - Chapter number: fades in first, scale(1.1) → scale(1), 0.8s, power3.out
  - Title: fades up from below (y: 20px → 0, 0.6s, 0.2s delay after number)
  - Description: fades in last, 0.4s delay after title
  - A thin gold vertical line (1px) separates number from title, fading in from top to bottom (scaleY 0 → 1, 0.5s)
- **Audio cue**: Cell drone continues. A soft, rhythmic ticking — like a clock or a typewriter carriage return — marks each chapter transition. On card 3, a subtle distorted undertone creeps in.

### Scene 4 — The Invitation (17s – 20s)

- **Visual**: Return to the archive grid — but now the images are cracked, glitched, fragmented. Digital corruption artifacts overlay the photos. One central image (a hand holding a smartphone, glowing) remains pristine. Above it, the final line: "The internet isn't dead. But it's on life support." in Playfair Display Regular, #F5F5F0. Below: the channel name/essay title "THE DEATH OF THE INTERNET — a video essay" in Inter, uppercase, #8A8A80, 14px, letter-spacing: 4px.
- **Animation**: 
  - Corrupted grid fades in (opacity 0 → 1, 1.5s)
  - Glitch artifacts appear via rapid alternating clip-path shifts (CSS animation, 0.1s intervals)
  - Central image resolves into clarity (filter: blur(8px) → blur(0), 1.5s)
  - Top text fades up (y: 10px → 0, opacity 0 → 1, 1.5s, power3.out)
  - Bottom credit fades in last, 0.5s delay
  - Slow fade to black over final 1s. Last element visible: the smartphone glow.
- **Audio cue**: Drone peaks with distortion. At 18s, a digital "glitch" sound — harsh but brief. The drone cuts at 19.5s. 0.5s of silence before end. The clock ticking stops.

---

## 5. Animation Requirements

- **Engine**: GSAP 3 (CDN: `https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js`)
- **Entrance style**: Fade-up, scale-down-to-1, horizontal rule draws, grid stagger
- **Transitions between scenes**: Slow crossfades (1.2–1.8s overlap). Scene N begins fading in while Scene N-1 is still at 60% opacity. This is a meditative piece — transitions are moments, not gaps.
- **Continuous animations**: Ken Burns drift on photographs, subtle breathing scale on text, film grain
- **Text reveals**: Fade-up (the default for gravitas), horizontal rule draws (framing devices), color transitions (for emphasis)
- **Easing**: `power2.out` for fades, `power3.inOut` for rule draws, `power2.inOut` for Ken Burns
- **Pacing philosophy**: Slow and deliberate. The viewer is being invited to think, not to react. Silence and stillness are tools.

---

## 6. Audio Design

- **Background music**: Minimalist cello drone + sparse piano. Think Johann Johannsson, Hildur Gudnadottir, Max Richter. Somber, intellectual, building tension.
- **Sound effects**: Dial-up modem (scene 1), clock tick / typewriter carriage (scene 3), digital glitch burst (scene 4)
- **Voiceover**: Optional. If used, a calm, measured baritone — think Werner Herzog or a seasoned documentarian. The VO should be recorded separately and mixed under the music.
- **Audio mixing**: BGM at 60% — music is atmosphere, not the star. SFX at 80% for iconic moments (dial-up, glitch). If VO: mixed at center, BGM ducked to 40%.

---

## 7. Technical Constraints

- Use `data-composition-id`, `data-start`, `data-duration`, `data-track-index` on every scene
- Each scene: `<div>` with `position: absolute; inset: 0; width: 1920px; height: 1080px`
- Scene visibility: `opacity` only — crossfades require overlapping opacity
- `will-change: transform, opacity` on animated elements
- Animate `transform` and `opacity` only
- Glitch effect: CSS `@keyframes` with rapid `clip-path` polygon shifts + `transform: translate()` jitter
- Ken Burns: `transform: scale()` + `transform-origin` driven by GSAP
- HyperFrames blocks to consider: `grain-overlay`, `vignette`, `photo-grid`, `chapter-cards`

---

## 8. Content Variables

| Placeholder              | Default                                              | Your Value |
|--------------------------|------------------------------------------------------|------------|
| `{{ESSAY_TITLE}}`        | `The Death of the Internet`                          |            |
| `{{SUBTITLE}}`           | `How the open web became a shopping mall`            |            |
| `{{GUIDING_QUESTION}}`   | `WHAT HAPPENED TO THE INTERNET WE WERE PROMISED?`    |            |
| `{{CHAPTER_1}}`          | `I. THE PROMISE`                                     |            |
| `{{CHAPTER_1_DATES}}`    | `1995–2005`                                          |            |
| `{{CHAPTER_2}}`          | `II. THE CAPTURE`                                    |            |
| `{{CHAPTER_2_DATES}}`    | `2006–2016`                                          |            |
| `{{CHAPTER_3}}`          | `III. THE WASTELAND`                                 |            |
| `{{CHAPTER_3_DATES}}`    | `2017–now`                                           |            |
| `{{CLOSING_LINE}}`       | `The internet isn't dead. But it's on life support.` |            |
| `{{CHANNEL_NAME}}`       | `YOUR CHANNEL NAME`                                  |            |

---

## 9. Reference Notes

- **Style reference**: "The Social Dilemma" (Netflix) opening sequences, "HyperNormalisation" (Adam Curtis), Vox / Nerdwriter video essay openers, "Koyaanisqatsi" (Godfrey Reggio)
- **Animation reference**: "Kurzgesagt" chapter transitions, "The Atlantic" documentary shorts, Johnny Harris video essays
- **Avoid**: Bright colors, fast cuts, playful eases, modern/gradient aesthetics, emoji, anything that feels "designed for retention" — this piece values substance over algorithm
