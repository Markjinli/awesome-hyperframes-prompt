# HyperFrames Prompt Template: KPI Dashboard

**Category:** Data Visualization
**Template:** kpi-dashboard
**Duration:** 25 seconds
**Resolution:** 1920x1080
**Scenes:** 4

---

## Prompt

```
Create a 25-second HyperFrames animated KPI dashboard video for a quarterly business review at 1920x1080 resolution. The design uses a dark dashboard aesthetic with a deep navy background (#0F172A), sky-blue data accents (#38BDF8), and rose-red highlights (#F43F5E) for negative metrics. The video should feel like a premium SaaS analytics platform — polished, data-dense, and cinematic.

---

## Scene 1 — Revenue Overview (0s – 7s)
**Purpose:** Lead with the top-line revenue number to anchor the quarterly narrative.

- **Background:** Dark navy (#0F172A) with a subtle radial gradient at top-center toward #1E293B (simulating a keylight on a dashboard). Subtle grid lines (#1E293B, 80x80px, opacity 0.4).
- **Header Bar (top, full width):**
  - "Q2 2026 Business Review" in white, 28px, Inter Semi Bold, left-aligned with 60px padding.
  - Quarter selector badge: "Q2 2026" in a pill (bg: rgba(56, 189, 248, 0.15), text: #38BDF8, border-radius 20px, 14px) at top-right.
  - Thin 1px bottom border: rgba(56, 189, 248, 0.1) spanning full width.
- **Hero KPI Card (centered, 55% width):**
  - Large animated counter: "$12.4M" — starts at $0 and counts up over 2.5s to $12.4M using GSAP counter animation.
  - Number styling: 96px, Inter Extra Bold, white, with a subtle text-shadow glow (#38BDF8, 0px 0px 30px at 20% opacity).
  - Subtitle: "Total Revenue" — 18px, #64748B, Inter Regular.
  - Change indicator: "▲ +18.3% vs Q1" in #22C55E (green) with a small up-arrow SVG, 16px, appears 0.5s after counter finishes.
- **Mini Bar Chart (below the KPI, 70% width, centered):**
  - 4 vertical bars representing Q1–Q4 revenue (Q4 projected in lighter/transparent).
  - Bars: #38BDF8 for actual, rgba(56, 189, 248, 0.3) for projected.
  - Bar height animation: grow from 0px to their values over 1.5s (elastic ease, stagger 0.15s).
  - Y-axis labels: "$10M", "$12M", "$14M" in #475569, 12px.
  - Labels below bars: "Q1", "Q2", "Q3", "Q4(P)" in #64748B, 14px.
- **Transition Out:** Counter and bars fade together over 0.4s.

---

## Scene 2 — Growth Metrics (7s – 13s)
**Purpose:** Break down growth drivers with a 2x2 stat card grid.

- **Background:** Same dark dashboard aesthetic.
- **Layout:** 2x2 grid of stat cards, centered, with 32px gaps. Each card: 380x200px.
- **Card Design:**
  - Background: rgba(30, 41, 59, 0.8), border: 1px solid rgba(56, 189, 248, 0.08), border-radius 16px, backdrop-filter blur(8px).
  - Card enters with a stagger animation (0.15s, from y: +40px, opacity 0, power3.out).
- **Card 1 — Top-Left: "ARR Growth"**
  - Icon: Small trending-up SVG chart icon (top-left of card, #38BDF8).
  - Value: "$48.2M" (counter animation, 48px, white, Inter Bold).
  - Label: "Annual Recurring Revenue" (14px, #64748B).
  - Delta: "▲ 22.4% YoY" (#22C55E, 14px).
- **Card 2 — Top-Right: "Net Revenue Retention"**
  - Value: "118%" (48px, white).
  - Label: "NRR" with description "dollar-based" (14px, #64748B).
  - Progress bar: Full-width thin bar (height 6px, border-radius 3px) — background: #1E293B, fill: #38BDF8 at 100% width. Animate width from 0 to 100% over 1.2s.
- **Card 3 — Bottom-Left: "Gross Margin"**
  - Value: "76.2%" (48px, white).
  - Label: "Gross Margin" (14px, #64748B).
  - Delta: "▲ 2.1pp" (#22C55E, 14px).
  - Donut ring: Small SVG donut (80x80) in the card's right area — 76% arc in #38BDF8, remaining in #1E293B. Animate stroke-dashoffset.
- **Card 4 — Bottom-Right: "CAC Payback"**
  - Value: "4.3 mo" (48px, white).
  - Label: "CAC Payback Period" (14px, #64748B).
  - Delta: "▼ 1.2 mo" (#22C55E, 14px) — green because lower is better.
- **Transition Out:** Cards fade individually with a reverse stagger over 0.5s.

---

## Scene 3 — Customer Insights (13s – 19s)
**Purpose:** Show customer base health and expansion.

- **Background:** Same dark dashboard with a slightly adjusted gradient to differentiate the scene.
- **Layout:** Three-panel horizontal layout with connecting visual elements.
- **Left Panel (30% width) — "Customer Count":**
  - Large number: "2,847" (counter animation, 64px, white, Inter Extra Bold).
  - Label: "Active Customers" (16px, #64748B).
  - Delta below: "▲ 312 new this quarter" (#22C55E, 14px).
  - Small spark-line SVG showing upward trend (60px tall, #38BDF8 stroke, 2px width).
- **Center Panel (40% width) — "Customer Tiers":**
  - Stacked horizontal bar chart showing customer breakdown:
    - "Enterprise (500+)": 847 customers, bar fill #38BDF8, 30% width.
    - "Mid-Market (100-499)": 1,200 customers, bar fill #7DD3FC, 42% width.
    - "SMB (<100)": 800 customers, bar fill #BAE6FD, 28% width.
  - Bar animation: each bar grows from 0 width over 1s with 0.2s stagger.
  - Each tier label on the left, customer count on the right end of the bar.
  - Legend below with colored dots.
- **Right Panel (30% width) — "Churn Rate":**
  - Percentage donut SVG chart (120x120):
    - Large arc: 96.8% in #38BDF8 (retention).
    - Small arc: 3.2% in #F43F5E (churn).
    - Center text: "3.2%" in white, 28px, bold, with "Monthly Churn" in 12px #64748B below.
  - Animate the donut arcs drawing over 1.5s (stroke-dasharray animation).
  - Comparison text below: "▼ 0.5pp from last quarter" in #22C55E, 14px.
- **Transition Out:** Panels compress toward center and fade over 0.5s.

---

## Scene 4 — Outlook & Forward Guidance (19s – 25s)
**Purpose:** Close with forward-looking projections and a confident outlook.

- **Background:** Dark navy gradient, slightly elevated (subtle lightening at center to suggest looking forward).
- **Headline:** "Q3 2026 Outlook" — white, 42px, Inter Bold, centered at top with a thin #38BDF8 underline (60px wide, 2px, centered below text).
- **Projection Card (centered, 65% width):**
  - Background: rgba(56, 189, 248, 0.05), border: 1px solid rgba(56, 189, 248, 0.15), border-radius 20px, padding: 40px.
  - Three inline projection metrics (flex row, equal spacing):
    - "Revenue Forecast: $14.1M" (▲ +13.7%)
    - "Target Customers: 3,200" (▲ +12.4%)
    - "Team Growth: +35 hires" (▲ expanding)
  - Each metric: value in white (32px, bold), label in #64748B (14px), arrow in #22C55E.
  - Metrics appear one at a time with 0.25s stagger.
- **Confidence Indicators (below metrics, appears at 22s):**
  - Three small progress bars:
    - "Pipeline Coverage": 92% filled, #38BDF8.
    - "Product Readiness": 100% filled, #22C55E.
    - "Hiring Plan": 78% filled, #F59E0B.
  - Bars are 300px wide, 8px tall, border-radius 4px. Animate fill from 0 over 1s.
- **Footer CTA (bottom 80px):**
  - "Full report available on the internal dashboard →" in #64748B, 14px, right-aligned.
- **Final Frame:** Hold for 1.5s. Subtle pulse on the headline underline.

---

## Global Settings
- **Font Stack:** Inter (all text). Inter Extra Bold for KPI numbers, Inter Semi Bold for headings, Inter Regular for labels.
- **Theme:** Dark dashboard — #0F172A base, #1E293B surfaces, #38BDF8 data accent, #F43F5E negative/warning, #22C55E positive/up, #F59E0B caution.
- **Easing:** power3.inOut for counter animations, elastic.out(1, 0.3) for bar chart entrances, power2.out for card entrances.
- **Grid:** Maintain consistent 60px horizontal padding and 80px vertical padding across all scenes.
- **Audio Note:** Energetic corporate soundtrack with a driving beat. Sound effects: subtle "tick" sounds on counter increments, "whoosh" on scene transitions, soft "pop" on card appearances.
```

---

## Template Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `reviewPeriod` | "Q2 2026" | Quarter label shown throughout |
| `revenueTotal` | "$12.4M" | Hero revenue number |
| `revenueGrowth` | "+18.3%" | Revenue growth percentage |
| `arrValue` | "$48.2M" | Annual recurring revenue |
| `nrrValue` | "118%" | Net revenue retention |
| `grossMargin` | "76.2%" | Gross margin percentage |
| `cacPayback` | "4.3 mo" | CAC payback period |
| `customerCount` | "2,847" | Total active customers |
| `churnRate` | "3.2%" | Monthly churn rate |
| `forecastRevenue` | "$14.1M" | Q3 forecast revenue |
| `bgColor` | #0F172A | Dashboard background |
| `dataColor` | #38BDF8 | Primary data accent |
| `negativeColor` | #F43F5E | Negative/warning accent |
| `positiveColor` | #22C55E | Positive/up indicator |
| `duration` | 25 | Total video duration in seconds |
| `resolution` | 1920x1080 | Output resolution |

---

## Usage Notes

1. The revenue counter in Scene 1 is the hero element — ensure the counting animation is smooth and the final number lands precisely at the right timing for voiceover.
2. Scene 2's 2x2 grid should maintain equal card dimensions regardless of content length — use consistent padding.
3. All donut/ring charts use SVG stroke-dasharray animation — precalculate the dash values based on percentages.
4. Delta indicators use green (#22C55E) for favorable movements and rose (#F43F5E) for unfavorable ones, even when "down" is good (like churn or CAC).
5. The outlook scene should feel aspirational — use slightly elevated brightness and more glow effects compared to the historical data scenes.
6. Replace all placeholder metric values with actual data from the business review.
