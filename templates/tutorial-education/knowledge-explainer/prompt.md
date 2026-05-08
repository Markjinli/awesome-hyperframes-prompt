# HyperFrames Prompt Template: Knowledge Explainer

**Category:** Tutorial / Education
**Template:** knowledge-explainer
**Duration:** 30 seconds
**Resolution:** 1920x1080
**Scenes:** 5

---

## Prompt

```
Create a 30-second HyperFrames educational explainer video titled "How AI Actually Works" at 1920x1080 resolution. The video uses an editorial/explainer visual style with a clean blue-and-white color scheme, diagram-like layouts, and clear typographic hierarchy. The tone is approachable yet authoritative — like a Vox or Kurzgesagt explainer adapted for professional audiences.

---

## Scene 1 — Opening Hook (0s – 5s)
**Purpose:** Frame the topic with an intriguing question that challenges common misconceptions.

- **Background:** Clean white (#FFFFFF) with a subtle blue gradient mesh in the top-right corner.
- **Title Entrance:** The word "Artificial Intelligence" types out character-by-character (50ms per character) in a large, bold font (64px, Inter Extra Bold, #1E40AF). A blinking cursor follows the last character for 1s before disappearing.
- **Subtitle:** "It's not magic. It's math." fades in below (24px, #64748B, Inter Regular) with a 0.5s delay after title completes.
- **Visual Element:** A series of floating geometric shapes (circles, squares, triangles) in varying shades of blue (#3B82F6, #60A5FA, #93C5FD) drift gently across the frame at 30% opacity, creating a sense of systems and patterns.
- **Transition Out:** Floating shapes accelerate outward as the background dissolves to scene 2 over 0.6s.

---

## Scene 2 — What is AI? (5s – 11s)
**Purpose:** Define AI simply and establish the scope of the discussion.

- **Background:** White with a light blue sidebar strip (left 320px, #EFF6FF).
- **Definition Card (center-right, 60% width):**
  - A quote-style card (border-left: 4px solid #3B82F6, padding: 24px 32px, background: #F8FAFC).
  - Text: "Artificial Intelligence is the field of computer science focused on building systems that can perform tasks that typically require human intelligence."
  - Source attribution: "— Definition adapted from Stanford HAI" in small gray text below.
- **Left Sidebar Visual (appears with 0.3s stagger after card):**
  - Three stacked keyword badges: "Learning", "Reasoning", "Perception" — each a pill-shaped tag (background: #DBEAFE, text: #1E40AF, font-weight 600, 18px, border-radius 24px) that stack vertically with 16px gaps.
  - Each badge slides in from left (x: -40px → 0) with a spring animation.
- **Transition Out:** Zoom blur effect on the definition card as scene transitions over 0.5s.

---

## Scene 3 — The Core: Machine Learning (11s – 18s)
**Purpose:** Explain the machine learning paradigm with a visual data-flow diagram.

- **Background:** White with a very faint grid (#F1F5F9 lines, 40x40px grid).
- **Flowchart Diagram (builds sequentially):**
  - **Step A: "Data"** — A rounded rectangle (background: #3B82F6, text: white, label: "Training Data") appears top-left at 11.5s. Arrow connects downward.
  - **Step B: "Learn"** — "Model" rectangle appears center at 12.5s. More arrows connect from Data to Model.
  - **Step C: "Predict"** — "Prediction" rectangle appears right at 13.5s.
  - **Step D: "Improve"** — A feedback loop arrow curves back from Prediction to Model at 14.5s (dashed line, #F59E0B).
  - Each rectangle: 160x80px, border-radius 12px, with a subtle drop shadow.
  - Arrows: 3px strokes, #94A3B8, with arrowheads.
- **Overlay Labels (appear as each step is revealed):**
  - Each step gets a one-line description below: "Millions of examples", "Pattern recognition", "Output generation", "Error correction".
  - Description text: 16px, #64748B, Inter.
- **Transition Out:** Diagram elements collapse toward center and fade over 0.5s.

---

## Scene 4 — Real-World Analogy: Teaching a Child (18s – 24s)
**Purpose:** Make the abstract concept concrete with a relatable analogy.

- **Background:** Split into two panels with a vertical divider line.
  - Left panel (50%): Warm cream (#FFFBEB) background. Label "Human Learning" at top.
  - Right panel (50%): Cool blue (#EFF6FF) background. Label "Machine Learning" at top.
- **Left Panel (Human):**
  - Animating icon: Simple stick-figure style child SVG with a question mark that bounces.
  - Steps list:
    - "Show examples" → "Explain patterns" → "Practice with feedback" → "Mastery"
  - Each step appears with a checkmark icon (green #22C55E) on a rolling stagger (0.2s).
- **Right Panel (Machine):**
  - Steps list (aligned to match left panel):
    - "Feed training data" → "Train the model" → "Evaluate & tune" → "Deploy"
  - Each step appears simultaneously with its left-panel counterpart.
  - Steps use blue checkmarks (#3B82F6).
- **Center Divider:** A 2px gradient line (#E2E8F0 → #CBD5E1) with the text "Same steps, different methods" rotated 90 degrees at center, 14px, #64748B.
- **Transition Out:** Both panels slide outward (left panel slides left, right panel slides right) over 0.5s.

---

## Scene 5 — Key Takeaway + Closing (24s – 30s)
**Purpose:** Summarize the core insight and leave the viewer with a memorable closing thought.

- **Background:** Deep blue gradient (#1E3A5F to #1E40AF) — the only dark scene for visual contrast and memorability.
- **Central Message:**
  - Large text: "AI = Data + Patterns + Iteration" appears centered, one word group at a time with a 0.3s stagger.
  - Each word group gets a different color treatment:
    - "AI" — white, 72px, Extra Bold
    - "=" — #60A5FA, 72px
    - "Data" — #F59E0B, 72px
    - "+ Patterns" — #3B82F6, 72px
    - "+ Iteration" — #93C5FD, 72px
- **Supporting Text (appears 0.5s after equation):** "The more data it sees, the better it gets. That's the whole secret." — white, 20px, Inter, opacity 0.8.
- **End Card Elements (fade in at 28s):**
  - Small logo placeholder (top-left: a circle with "Edu" text, 40x40).
  - Series title in bottom-right: "How Tech Works" / "Episode 1" — #94A3B8, 14px.
- **Final Frame:** Hold for 1s. All text fully visible, slight gentle float animation on the equation text (translateY: -4px → +4px, 3s loop).

---

## Global Settings
- **Font Stack:** Inter (headings), Inter or system sans-serif (body). No monospace needed — this is an editorial/explainer style.
- **Easing:** power3.inOut for diagram builds, power2.out for text entrances, spring for interactive-feeling elements.
- **Color Progression:** The video moves from light/white backgrounds (Scenes 1-4) to a single dark background (Scene 5) for contrast and memorability.
- **Audio Note:** Expect a calm, clear voiceover (approx. 150 words/min). Background music: soft, curious, ambient electronic. Sound effects: subtle "pop" on each diagram element appearance.
```

---

## Template Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `topicTitle` | "How AI Actually Works" | Main topic title |
| `hookQuestion` | "It's not magic. It's math." | Subtitle / hook phrase |
| `definitionText` | "Artificial Intelligence is the field..." | Core definition displayed in Scene 2 |
| `flowchartSteps` | ["Data", "Learn", "Predict", "Improve"] | Steps in the ML flowchart (Scene 3) |
| `analogyTitleLeft` | "Human Learning" | Left panel label (Scene 4) |
| `analogyTitleRight` | "Machine Learning" | Right panel label (Scene 4) |
| `closingEquation` | "AI = Data + Patterns + Iteration" | Key takeaway equation (Scene 5) |
| `accentColor` | #3B82F6 | Primary accent / blue color |
| `highlightColor` | #F59E0B | Highlight / contrast color |
| `bgLight` | #FFFFFF | Light background color |
| `bgDark` | #1E3A5F | Dark background for closing scene |
| `duration` | 30 | Total video duration in seconds |
| `resolution` | 1920x1080 | Output resolution |

---

## Usage Notes

1. The flowchart in Scene 3 is the visual centerpiece — ensure diagram elements are properly aligned and spaced for clarity.
2. Scene 4's side-by-side analogy works best when both panels build simultaneously; synchronize the stagger animations.
3. The single dark scene (Scene 5) should feel like a dramatic but earned contrast — avoid using dark backgrounds earlier in the video.
4. If the topic changes from AI, update the flowchart steps and analogy content to match the new domain.
5. The typing animation in Scene 1 should use a monospace-adjacent timing even if the font is proportional — consistent 50ms per character.
