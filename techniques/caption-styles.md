# Caption 风格模式 — 深度指南

> 字幕不是文字的简单叠加，它是视频设计系统的一部分。本指南覆盖 5 种 Caption 风格，每种包含字体、动画、尺寸、色彩的完整方案。

## 5 种 Caption 风格速查

| 风格 | 字体 | 入场动画 | 推荐字号 | 情绪 | 适用场景 |
|------|------|---------|---------|------|---------|
| **Hype** | 粗体无衬线 | scale-pop | 72–96px | 能量/兴奋 | 产品发布、促销、Reels |
| **Corporate** | 干净无衬线 | fade + slide-up | 56–72px | 专业/可信 | B2B、企业宣传、教程 |
| **Tutorial** | 等宽字体 | typewriter | 48–64px | 技术/教学 | 代码演示、操作指引 |
| **Storytelling** | 衬线体 | slow fade | 44–56px | 优雅/叙事 | 品牌故事、纪录片 |
| **Social** | 圆体/趣味 | bounce | 56–80px | 活泼/亲切 | TikTok、IG Story、短视频 |

## Hype 风格 — 高能量标题

```
Font: Inter Black / Montserrat Black / any Heavy weight
Animation: scale(0) → scale(1.15) → scale(1.0), duration 0.4s
Easing: back.out (overshoot for punch)
Color: Bright accent on dark bg, or white with colored shadow
Extra: Add a subtle motion blur during the scale-up phase
```

**Prompt 描述**
```
Use hype-style captions: heavy weight sans-serif, scale-pop entrance with back.out easing.
Each keyword appears with an aggressive scale bounce (0 → 1.15 → 1.0 in 0.35s).
Brand names in #FF6B35, others in white.
Add 2px motion blur during the pop for extra impact.
```

## Corporate 风格 — 专业简洁

```
Font: Inter SemiBold / SF Pro Display / any clean sans-serif
Animation: translateY(20px) + opacity(0) → translateY(0) + opacity(1), 0.5s
Easing: power3.out (smooth deceleration)
Color: Dark gray on light bg, or white on dark
Extra: 4px letter-spacing for uppercase, subtle text-shadow for readability
```

**Prompt 描述**
```
Corporate-style captions: clean sans-serif, fade-in with a gentle 20px slide-up.
Power3.out easing, 0.5s per caption.
Dark mode: #F5F5F5 text on transparent dark overlay strip.
Keep it understated — the words should feel placed, not thrown.
```

## Tutorial 风格 — 代码/教学

```
Font: JetBrains Mono / Fira Code / any monospace
Animation: Typewriter effect — characters appear one by one, 30-40ms per char
Easing: steps() or linear (mechanical feel)
Color: Green terminal text on dark bg, or syntax-highlighted keywords
Extra: Blinking cursor at end of line, line numbers in gutter
```

**Prompt 描述**
```
Tutorial-style captions with monospace typewriter animation.
Each line types out at ~35ms per character, with a blinking █ cursor at the end.
Use syntax highlighting: commands in #50FA7B, arguments in #FF79C6.
Show line numbers (L1, L2…) in a dimmed gutter on the left.
After typing completes, the cursor blinks twice, then the line slides up for the next one.
```

## Storytelling 风格 — 叙事/纪录片

```
Font: Playfair Display / Cormorant Garamond / any elegant serif
Animation: opacity(0) → opacity(1), 1.2s, with a 0.3s delay between lines
Easing: sine.inOut (slow, symmetrical, dreamy)
Color: Warm off-white (#F5F0EB) or cream on dark bg
Extra: Very subtle blur-in (blur(4px) → blur(0)) adds dreaminess
```

**Prompt 描述**
```
Storytelling captions: elegant serif font, slow fade-in over 1.2s with sine easing.
Each line enters with a 0.3s stagger. Add a subtle defocus → focus effect (blur 4px → 0).
Color: #F5F0EB (warm cream) on deep navy background.
The words should feel like they're being remembered, not announced.
```

## Social 风格 — 活泼/平台原生

```
Font: Nunito / Quicksand / any rounded sans-serif
Animation: translateY(30px) + scale(0.8) + rotate(-3deg) → final position, 0.45s
Easing: back.out(1.5) for playful overshoot
Color: Bright, saturated — TikTok red, IG gradient, YouTube red
Extra: Emoji support, colored text backgrounds (highlight strips behind words)
```

**Prompt 描述**
```
Social-style captions with rounded bold font and bouncy entrance.
Each word pops in from below with a slight rotation (-3° → 0°),
scale bounce (0.8 → 1.1 → 1.0), and bright colored highlight strips behind key phrases.
Use back.out(1.5) for extra bounce. Colors: vibrant coral #FF6B6B and electric blue #4ECDC4.
Add relevant emoji that scale in 0.2s after the text lands.
```

## Per-Word 样式覆盖

每句话中的关键词可以用特殊样式突出：

```
"Introducing the REVOLUTIONARY new platform"
                    ↑
            Scale: 1.2x, color: accent, delay: +0.1s
            
"The fastest way to BUILD and SHIP"
                      ↑           ↑
              weight: 900    bounce: yes
```

**Prompt 描述**
```
"Make brand names 20% larger with accent color (#FF6B35)."
"Add bounce to emotional keywords: 'amazing', 'revolutionary', 'game-changer'."
"Highlight numbers differently: bigger, bolder, with a count-up animation from 0."
"All-caps words get +2px letter-spacing and slightly slower entrance."
```

## Caption 布局模式

### 居中底部（最通用）
```
Position: bottom center, 80px from bottom edge
Max width: 80% of viewport
Line limit: 2-3 lines max
Background: optional semi-transparent strip behind text for readability
```

### 左对齐底部（教程/访谈）
```
Position: bottom left, 60px from edges
Max width: 60% of viewport
Line limit: 2 lines
Good for: tutorial voiceover, interview subtitles
```

### 动态跟随（社交媒体）
```
Position: varies per word — words appear near the visual element they relate to
Good for: TikTok-style emphasis, product feature callouts
```

### 全屏大字（抒情/品牌）
```
Position: dead center, single word or short phrase
Font size: 120-200px
Good for: brand anthem, emotional beat, chapter titles
```

## 与 AI Agent 协作技巧

1. **指定字体文件名**："Use Inter-Bold.woff2 from ./fonts/"——不要只说 "bold font"
2. **给具体时序**："Word 3 lands at 1.2s, word 5 at 1.8s"——不要只说 "staggered"
3. **定义色彩角色**：primary = 正文, accent = 品牌词, dim = 介词/连接词
4. **考虑安全区**：在 1080×1920 竖屏中，底部 150px 留给 UI 元素
5. **测试可读性**：在有背景视频时，caption 需要半透明背景条或 text-shadow
