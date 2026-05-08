# HyperFrames Prompt Template: Trend Analysis

**Category:** Data Visualization
**Template:** trend-analysis
**Duration:** 20 seconds
**Resolution:** 1920x1080
**Scenes:** 4 (overlapping)

---

## Prompt

```
Create a 20-second HyperFrames trend analysis video titled "The Rise of Remote Work: 2020–2026" at 1920x1080 resolution. The video uses an editorial data journalism visual style inspired by NYT / Reuters data features — clean white and cream backgrounds, data-forward design, elegant typography, and precise chart animations. The tone is authoritative and insightful, suitable for a professional business audience.

---

## Scene 1 — Title Card & Hook Stat (0s – 5s)
**Purpose:** Establish the topic and hook viewers with the most dramatic headline statistic.

- **Background:** Clean off-white / cream (#FAFAF9) — warm, editorial feel. Very subtle paper texture if possible.
- **Headline (appears from 0s):**
  - "The Rise of Remote Work" in a serif display font (Playfair Display or Georgia, 72px, #1A1A1A, font-weight 700).
  - Subtitle below: "How the global workforce transformed in six years" — Inter, 20px, #6B7280.
  - Headline fades in with a gentle y-shift (+10px → 0, 1s, power3.out).
- **Hero Stat (appears at 2s, right third of the frame):**
  - "4x" — extremely large (120px, Playfair Display Bold, #3B82F6) with a counter animation from 1x to 4x over 1.2s.
  - Label below: "Increase in remote workers worldwide since 2020" — Inter, 16px, #6B7280, max-width 300px.
  - Source line: "Source: Global Workforce Survey, 2026" — 12px, #9CA3AF, italic.
- **Decorative Element:** A thin horizontal rule (#D1D5DB, 1px, 60% width, centered below the headline) extends from 0 width to full width over 1.5s.
- **Transition Out:** Headline and stat fade while the chart axes slide in for Scene 2. Smooth dissolve over 0.6s.

---

## Scene 2 — The Main Trend: Line Chart (5s – 13s)
**Purpose:** Show the core data story with an animated line chart.

- **Background:** Same cream (#FAFAF9) with subtle grid lines for the chart area (#E5E7EB, 1px, 50x50px cells, only within chart bounds).
- **Chart Area:** 1100x550px, centered, with labeled axes.
  - **Y-Axis (left):** "Remote Workers (millions)" — vertical label, 12px, #6B7280. Tick marks at 0, 50M, 100M, 150M, 200M with subtle grid lines.
  - **X-Axis (bottom):** Years 2020 through 2026, 14px labels, #6B7280.
- **Line Chart (SVG, animated):**
  - Data points (millions): 2020=45, 2021=92, 2022=128, 2023=147, 2024=161, 2025=178, 2026=192.
  - Line: 3px stroke, #3B82F6, with a gentle curve (monotone-x interpolation).
  - **Animation:** stroke-dasharray/dashoffset animation — the line draws from left to right over 2.5s (power2.inOut).
  - Data dots: 8px circles at each data point, #3B82F6, with a white 2px stroke. Dots pop in after the line reaches each point (scale 0 → 1.2 → 1, elastic.out).
  - **2020–2021 segment highlight:** A semi-transparent area fill below the line for the steepest growth section (rgba(59, 130, 246, 0.08)) with a subtle pulse animation.
- **Annotations (appear after line draws):**
  - At 2021 data point: "Pandemic acceleration: +104%" — callout label in #F59E0B, 14px, with a thin leader line pointing to the data dot.
  - At 2026 data point: "Stabilizing at 192M globally" — callout label in #3B82F6, 14px.
- **Transition Out:** Chart fades to 30% opacity while Scene 3 milestones overlay on top.

---

## Scene 3 — Key Milestones Overlay (13s – 17s)
**Purpose:** Contextualize the data with real-world events that drove the trend.

- **Background:** The line chart from Scene 2 remains visible at 30% opacity in the background, maintaining context.
- **Milestone Timeline (vertical, left-aligned, 450px wide):**
  - Five milestone cards, each appearing with a 0.2s stagger from top to bottom:
    1. **Mar 2020** — "Global lockdowns begin. 85% of companies mandate remote work overnight." (icon: globe/lock)
    2. **Jun 2021** — "Hybrid work models emerge. 63% of high-growth companies adopt remote-first policies." (icon: building/refresh)
    3. **Sep 2022** — "Return-to-office mandates begin. Tension between employers and employees on flexibility." (icon: opposing arrows)
    4. **Jan 2024** — "Remote work infrastructure matures. VR collaboration tools reach enterprise adoption." (icon: VR headset)
    5. **Mar 2026** — "74% of knowledge workers are hybrid or fully remote. Remote work is the new default." (icon: checkmark/home)
  - Each milestone card:
    - Background: white (#FFFFFF), 1px border (#E5E7EB), border-radius 8px, subtle shadow (0 2px 8px rgba(0,0,0,0.04)), padding: 16px 20px, margin-bottom: 12px.
    - Date: 14px, Inter Semi Bold, #3B82F6.
    - Description: 13px, Inter Regular, #374151, line-height 1.5.
    - A small colored dot (8px, #3B82F6) connects each card to a vertical timeline line (2px, #E5E7EB) on the left edge.
- **Transition Out:** Milestone cards slide left and fade over 0.5s. Chart fully fades out.

---

## Scene 4 — Regional Comparison & Closing (17s – 20s)
**Purpose:** Add geographic context and close with the big-picture takeaway.

- **Background:** Clean white (#FFFFFF) — pure, final, conclusive.
- **Regional Comparison Cards (top 60%, horizontal flex, 3 cards):**
  - Card 1: "North America" — 38% of remote workers globally. Horizontal bar: 38% filled, #3B82F6.
  - Card 2: "Europe" — 31% of remote workers globally. Horizontal bar: 31% filled, #60A5FA.
  - Card 3: "Asia-Pacific" — 22% of remote workers globally. Horizontal bar: 22% filled, #93C5FD.
  - Each card: 280x140px, white background, 1px border (#E5E7EB), border-radius 10px.
  - Bars animate from 0 width over 1s with 0.15s stagger (power3.inOut).
  - Percentage number appears at the end of each bar after it completes.
- **Closing Statement (bottom 40%, centered):**
  - "Remote work isn't the future. It's the present." — Playfair Display, 36px, #1A1A1A, italic.
  - Appears with a typewriter-like reveal (word-by-word, 0.15s stagger) starting at 18.5s.
  - A thin blue underline (#3B82F6, 2px, 200px wide, centered) glides in below the text over 0.6s.
- **Source Footer (bottom 20px):**
  - "Data: Global Workforce Survey (2026), ILO Remote Work Report (2025), McKinsey Future of Work (2025)" — 11px, #9CA3AF, centered.
- **Final Frame:** Hold for 1s. Subtle gentle scale pulse (1 → 1.02 → 1, 3s loop) on the closing statement.

---

## Global Settings
- **Font Stack:** Playfair Display (display/headlines), Inter (body, labels, data). The serif/sans-serif pairing creates the editorial journalism aesthetic.
- **Color Scheme:**
  - Backgrounds: #FAFAF9 (cream), #FFFFFF (white)
  - Primary Data: #3B82F6 (blue)
  - Secondary Data: #60A5FA, #93C5FD (lighter blues for hierarchy)
  - Text: #1A1A1A (headlines), #374151 (body), #6B7280 (labels), #9CA3AF (footnotes)
  - Highlight: #F59E0B (callout annotations)
  - Borders/Lines: #E5E7EB, #D1D5DB
- **Easing:** power3.inOut for chart animations, power2.out for text, elastic.out(1, 0.3) for data point pops.
- **Chart Library Style:** All charts are custom SVG — no third-party charting libraries. Simple, clean, NYT-style graphics.
- **Audio Note:** Calm, thoughtful background music (ambient, data-journalism podcast style). Voiceover pacing at approximately 140 words per minute. Subtle sound effects on data point appearances.
```

---

## Template Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `topicTitle` | "The Rise of Remote Work: 2020–2026" | Main title of the analysis |
| `heroStat` | "4x" | Hero statistic for the hook scene |
| `heroLabel` | "Increase in remote workers worldwide since 2020" | Label for hero stat |
| `chartData` | [45, 92, 128, 147, 161, 178, 192] | Data points in millions (2020-2026) |
| `chartLabel` | "Remote Workers (millions)" | Y-axis label |
| `milestones` | 5 event objects | Key events with date and description |
| `regions` | 3 region objects | Regional data with name and percentage |
| `closingStatement` | "Remote work isn't the future. It's the present." | Closing takeaway text |
| `sources` | 3 source strings | Data source citations |
| `primaryColor` | #3B82F6 | Primary chart/data color |
| `bgColor` | #FAFAF9 | Primary background color |
| `duration` | 20 | Total video duration in seconds |
| `resolution` | 1920x1080 | Output resolution |

---

## Usage Notes

1. Replace the chart data array with actual numbers from the analysis being presented. The data drives the entire video narrative.
2. The milestone dates and descriptions in Scene 3 should be carefully fact-checked — these are the contextual anchors that make the data meaningful.
3. If the time range changes (e.g., 2015-2025), update the X-axis labels and milestone years accordingly.
4. The line chart curve type (monotone-x) produces a natural-looking smooth line — avoid sharp angles unless the data specifically calls for step changes.
5. Regional comparison cards can be expanded to more regions or replaced with industry verticals, demographic segments, or any other breakdown dimension.
6. The serif display font (Playfair Display) plus sans-serif body (Inter) pairing is central to the editorial aesthetic — do not replace both with sans-serif.
