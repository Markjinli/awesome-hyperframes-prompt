# HyperFrames Prompt Template: Course Intro

**Category:** Tutorial / Education
**Template:** course-intro
**Duration:** 20 seconds
**Resolution:** 1920x1080
**Scenes:** 4

---

## Prompt

```
Create a 20-second HyperFrames course introduction video for "Mastering React 2026" at 1920x1080 resolution. The video uses a warm educational aesthetic with a dark navy background (#1E293B), electric blue accents (#3B82F6), and amber highlights (#F59E0B). The design should feel modern and code-forward, blending developer tools aesthetics with polished online learning production values.

---

## Scene 1 — Hook Question (0s – 5s)
**Purpose:** Capture attention with a provocative question that resonates with the target audience (web developers).

- **Background:** Dark navy (#1E293B) with subtle grid pattern (developer tool / code editor aesthetic).
- **Text Animation:** The words "Still writing class components?" fade in, centered, one word at a time with a 0.15s stagger. Each word scales from 1.15 to 1.0 as it fades in (spring ease).
- **Font:** Fira Code or JetBrains Mono — monospace for the code-forward feel. White text (#F8FAFC), bold, 64px.
- **Accent Line:** A thin 2px amber (#F59E0B) horizontal line slides in from left to right below the text over 0.6s, 0.3s after the last word appears.
- **Transition Out:** Everything scales down slightly (0.95) and fades over 0.4s.

---

## Scene 2 — Course Overview (5s – 11s)
**Purpose:** Show the curriculum at a glance, communicating comprehensive value.

- **Background:** Same dark navy, with the grid pattern now animated (slow diagonal drift to suggest an IDE).
- **Layout:** A 3x2 CSS Grid of curriculum cards (6 cards) that stagger in from the bottom (y: +60px → 0, opacity 0 → 1, stagger 0.12s, each with a power3.out ease).
- **Card Design:**
  - Semi-transparent cards: background rgba(59, 130, 246, 0.08), border 1px solid rgba(59, 130, 246, 0.2), border-radius 12px.
  - Each card: module number badge (small circle, #3B82F6), module title (white, 20px, Inter or system sans-serif), and a one-line description (slate-400, 14px).
- **Modules displayed:**
  1. React Fundamentals Refresh
  2. Hooks Deep Dive
  3. Server Components & RSC
  4. State Management in 2026
  5. Performance & Suspense
  6. Full-Stack Next.js
- **Headline:** "Everything You Need to Master React in 2026" fades in above the grid at 6s mark, white, 48px, font-weight 700.
- **Transition Out:** Cards slide out left/right in alternating directions over 0.5s.

---

## Scene 3 — Instructor Introduction (11s – 16s)
**Purpose:** Build trust and personal connection with the instructor.

- **Layout:** Two-column split — left side (40%) instructor photo placeholder, right side (60%) text content.
- **Instructor Card:**
  - Circular photo area (200x200, border-radius 50%, border 3px solid #3B82F6) with a subtle pulsing ring animation (scale 1 → 1.05 → 1, repeating every 2s).
  - Photo area shows a dark silhouette placeholder with initials "SK" in the center.
- **Text Content (slides in from right, 0.6s, power3.out):**
  - Instructor name: "Sarah Kim" — white, 40px, font-weight 700.
  - Title: "Senior Frontend Engineer & React Core Contributor" — #94A3B8, 20px.
  - Stats row (appears with stagger): "12+ Years Experience", "50+ Talks", "20K+ Students" — each in a small pill badge (bg: rgba(245, 158, 11, 0.15), text: #F59E0B, border-radius 20px).
- **Transition Out:** Fade out both columns over 0.5s.

---

## Scene 4 — Call to Action (16s – 20s)
**Purpose:** Drive enrollment with a clear, compelling CTA.

- **Background:** A subtle gradient overlay — dark navy to slightly lighter blue at center.
- **Central CTA Button:**
  - Large prominent button: "Enroll Now — Early Bird Pricing" centered on screen.
  - Background: #3B82F6, text: white, font-weight 700, padding: 20px 48px, border-radius: 12px, font-size 24px.
  - Hover/pulse animation: box-shadow glow that pulses from 0px 0px 0px rgba(59,130,246,0) to 0px 0px 40px rgba(59,130,246,0.6) on a 1.5s loop.
- **Urgency Text (above button):** "Launch Day Price — 40% Off" in amber (#F59E0B), 28px, with a subtle shake animation every 2s.
- **Footer:** Course URL "react2026.dev" in monospace, #64748B, 16px at the bottom.
- **Final Frame:** Hold the CTA for the last 1s. All elements remain fully visible.

---

## Global Settings
- **Font Stack:** Primary — Inter (headings, body), Secondary — Fira Code (code-like elements).
- **Easing:** power3.inOut for entrances, power2.out for exits.
- **Stagger Default:** 0.12s between sibling elements unless specified otherwise.
- **Audio Note:** Leave space in timing for background music (modern, energetic instrumental) and voiceover sync points at each scene boundary.
```

---

## Template Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `courseName` | "Mastering React 2026" | Course title used throughout |
| `instructorName` | "Sarah Kim" | Instructor's full name |
| `instructorTitle` | "Senior Frontend Engineer" | Instructor's professional title |
| `moduleCount` | 6 | Number of curriculum modules in the grid |
| `ctaText` | "Enroll Now — Early Bird Pricing" | Call to action button text |
| `discountText` | "Launch Day Price — 40% Off" | Urgency / discount message |
| `courseUrl` | "react2026.dev" | Course landing page URL |
| `bgColor` | #1E293B | Primary background color |
| `accentColor` | #3B82F6 | Primary accent / brand color |
| `highlightColor` | #F59E0B | Highlight / emphasis color |
| `duration` | 20 | Total video duration in seconds |
| `resolution` | 1920x1080 | Output resolution |

---

## Usage Notes

1. Replace placeholder values (instructor name, course URL, pricing) with actual course details.
2. The module list in Scene 2 should reflect the actual curriculum — replace the 6 entries.
3. Scene 3 requires an actual instructor photo — replace the placeholder description with a real image asset reference.
4. Adjust Scene 1 hook question text to match the target audience's current pain point.
5. Timing markers assume voiceover pacing of approximately 150 words per minute. Adjust scene durations if VO script is significantly different.
