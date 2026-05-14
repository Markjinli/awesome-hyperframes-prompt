# Audio-Reactive 动画 — 深度指南

> 让画面跟随音频节拍、频率、振幅变化。HyperFrames 支持将音频频段映射到 CSS/GSAP 属性，实现真正的「声画同步」。

## 核心概念

HyperFrames 的 audio-reactive 系统将音频频谱分为四个频段，每个频段可映射到不同的视觉属性：

| 音频频段 | 频率范围 | 视觉映射 | 效果描述 |
|---------|---------|---------|---------|
| **Bass（低频）** | 20-250Hz | `scale`, `y` | 元素随鼓点/贝斯脉动缩放 |
| **Mids（中频）** | 250-2000Hz | `shape`, `rotation` | 人声/吉他驱动形态变化 |
| **Treble（高频）** | 2000-20000Hz | `glow`, `opacity` | 镲片/高音驱动闪烁和透明度 |
| **Amplitude（总振幅）** | 全频段 | `opacity`, `blur` | 整体响度驱动呼吸效果 |

## 基础映射公式

给 AI Agent 的描述：

```
Map [audio_band] to [css_property] on [target_element].
Intensity: [subtle|medium|aggressive] ([percentage]% range).
```

### 示例 Prompt 片段

**Bass 驱动标题缩放（音乐视频）**
```
Map bass frequencies to scale on the hero title.
When the kick drum hits, the title pulses from 1.0 → 1.08 → 1.0.
Use a fast decay (0.15s) so it snaps back immediately.
Intensity: medium (8% max scale).
```

**Treble 驱动发光（迷幻/艺术）**
```
Map treble to glow intensity on ".accent-glow" elements.
Higher frequencies = brighter box-shadow and text-shadow.
Range: opacity 0 → 0.6, blur-radius 20px → 60px.
Intensity: subtle — should shimmer, not flash.
```

**Amplitude 驱动呼吸背景（氛围感）**
```
Map overall amplitude to opacity on the background gradient.
Quiet sections = darker background (opacity 0.3).
Loud sections = full brightness (opacity 1.0).
Smooth the transitions over 0.8s to avoid flickering.
```

**Bass + Treble 组合（EDM / 高能量场景）**
```
Dual mapping:
- Bass → scale on ".beat-indicator" (aggressive: 0.85 → 1.15)
- Treble → filter:brightness on ".strobe-layer" (subtle: 1.0 → 1.3)

Both should feel like a live audio visualizer built into the video.
```

## 按场景的推荐策略

### 产品宣传（保守/专业）
```
Map bass to subtle scale (3-5%) on logo and key text.
Keep it barely perceptible — like the graphics are "breathing" with the music.
Audience shouldn't consciously notice, but it makes the video feel more polished.
```

### 社交媒体 Reel（大胆/吸睛）
```
Aggressive bass mapping (10-15%) on all text elements.
Every beat = everything pops.
Combine with whip pan transitions on beat drops.
```

### 品牌故事 / 情感（细腻/温柔）
```
Map mids (not bass) to opacity on ambient background elements.
Use long smoothing (1-2s) to create a slow, organic drift.
Avoid sharp attacks — nothing should feel "triggered."
```

### 音乐可视化（实验/艺术）
```
Full spectrum mapping:
- Bass → scale on geometric shapes
- Mids → hue-rotate on color wash overlay
- Treble → particle density
- Amplitude → overall scene brightness

Go wild — this is the one category where over-the-top is expected.
```

## 与 AI Agent 协作的技术提示

### 必须指定的参数
```
1. 目标元素选择器（".hero-title", "#logo", ".background"）
2. 映射的 CSS 属性（scale, opacity, filter, transform）
3. 强度范围（最小值 → 最大值）
4. 平滑/衰减时间（smoothing in seconds）
```

### 常见问题与修正

| 问题 | 原因 | 修正 Prompt |
|------|------|------------|
| 画面抖动/闪烁 | smoothing 太小 | "increase audio smoothing to 0.3s" |
| 效果太微弱看不见 | intensity 太小 | "increase bass scale intensity to 12%" |
| 元素变形严重 | intensity 太大 | "cap scale at 1.05 instead of 1.2" |
| 不同步/延迟 | 帧率或 buffer 问题 | "use smaller FFT buffer size for lower latency" |
| 只有部分元素响应 | 选择器范围不够 | "apply to ALL elements with class .beat-sync" |

### 调试工作流
```
1. 先用明显的 intensity（15-20%）确认映射生效
2. 验证后降低到实际需要的强度
3. 调整 smoothing 直到感觉自然
4. 确保音频文件和视频在同一目录
```

## 高级技巧

### 频段过滤精确触发
```
Only respond to bass frequencies below 80Hz (sub-bass range).
This isolates the kick drum from the bass guitar.
Use case: you want the pulse ONLY on kick, not on bassline.
```

### 多元素分层响应
```
- ".hero-title" → bass (scale, aggressive)
- ".subtitle" → mids (opacity, subtle)
- ".accent-line" → treble (glow, medium)
- ".background" → amplitude (brightness, subtle)

Each element dances to a different part of the music.
Creates a rich, orchestrated feel rather than everything bouncing together.
```

### 与转场联动
```
When the bass amplitude exceeds 0.7, trigger a glitch transition.
This creates "beat-triggered transitions" — no manual timing needed.
The music itself drives the cut points.
```
