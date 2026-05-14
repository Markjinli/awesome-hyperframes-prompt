# Beat Sync — 音频同步节拍动画

> Bass 驱动缩放、Treble 驱动发光、Amplitude 驱动呼吸——画面和音乐合二为一。

## 效果

15-20 秒的高能量音频同步动画。画面中的文字、图形、背景随着音乐节拍脉动。低频驱动大元素的缩放，高频驱动光泽和粒子，整体振幅驱动背景亮度。适合音乐推广、活动预告、社交媒体 Reel。

## 适用场景

- 音乐节/活动宣传
- 产品发布高潮段落
- 社交媒体高能量内容
- DJ/音乐人视觉

## Prompt 模板

````markdown
使用 HyperFrames 创建一段音频同步节拍动画。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080（或 1080x1920 竖屏）
- 帧率：30fps
- 风格：高能量、霓虹暗底、现场音乐可视化感
- 音频：「[你的音乐文件路径].mp3」

## 音频频段映射
将音频的四个频段映射到视觉元素：

| 频段 | 频率范围 | 映射目标 | 效果 | 强度 |
|------|---------|---------|------|------|
| Bass | 20-250Hz | `.hero-title` scale | Kick drum 驱动标题缩放 | 中度（1.0-1.08） |
| Mids | 250-2000Hz | `.accent-shape` rotation | 人声/贝斯驱动图形旋转 | 微妙（±5°） |
| Treble | 2000-20000Hz | `.glow-layer` opacity | 镲片驱动光晕闪烁 | 微妙（0-0.4） |
| Amplitude | 全频段 | `.bg-gradient` brightness | 整体响度驱动背景呼吸 | 中度（0.7-1.0） |

## 视觉设计

**背景层**
- 暗色渐变底：#0A0A0A → #1A0A2E
- 响应 Amplitude：安静时暗（brightness 0.7），大声时亮（1.0）
- 可选的粒子/vu 表效果

**主标题（`.hero-title`）**
- 文字：「[你的标题，如 "UNLEASH"]」
- 字体：Inter Black / Montserrat Black，字号 120px
- 响应 Bass：每个底鼓 hit 时缩放 1.0 → 1.08 → 1.0
- 衰减时间：0.15s（快速回弹）
- 颜色：#FFFFFF，Bass 峰值时 text-shadow glow 加强

**副标题（`.sub-text`）**
- 文字：「[副标题，如 "The new standard"]」
- 字号：48px，字重：Regular
- 响应 Mids：微弱的 Y 轴平移跟踪人声节奏
- 颜色：#A0A0B0

**强调图形（`.accent-shape`）**
- 2-3 个几何装饰元素（圆形、菱形、线条）
- 响应 Mids + Treble 组合
- 颜色：品牌强调色 [#FF6B35 / #4ECDC4]

**光晕层（`.glow-layer`）**
- 绝对定位的径向渐变
- 响应 Treble：高频出现时发光
- 颜色：暖金色 #FFB800

## 动画时间线

**0-3s：Build Up**
- 背景从全暗逐渐亮起
- 标题从模糊中浮现（blur 20px → 0）
- 音频渐入（volume: 0 → 1）

**3-16s：Main Drop**
- 全频段映射激活
- 标题全力响应 Bass
- 每次副歌/重拍时，所有元素同步缩放 + 光晕闪现
- 强拍：额外的 0.15s white flash（opacity 0 → 0.06 → 0）

**16-20s：Outro**
- 音乐渐弱，视觉映射强度逐渐降低（1.0x → 0.3x）
- 标题做最后一次放大，然后缩小到 0.85x 并 fade out
- Logo / CTA 淡入

## 转场策略
- 段落切换点用 Flash Through White（0.3s，配合重拍）
- 强拍之间用 hard cut

## 技术注意事项
- 使用 Web Audio API 的 AnalyserNode 获取频段数据
- FFT size: 256（低延迟，适合节拍检测）
- smoothingTimeConstant: 0.4（平衡响应速度和稳定性）
- 所有 GSAP timeline 注册到 window.__timelines
- 不使用 Math.random()
````

## 关键技巧

- **频段分工明确**：Bass→Scale, Treble→Glow, Amplitude→Brightness。不要把所有效果都绑在 Bass 上
- **衰减要快**：0.15-0.2s 的衰减让元素在鼓点后立即回弹，产生「punchy」感
- **弱拍也有呼吸**：quiet 时 background 暗一点（0.7），形成呼吸节奏
- **White Flash 是秘密武器**：重拍时一个 0.15s 微弱的白色闪现（opacity 6%），观众不会意识到但能感觉到

## 自定义方法

1. 替换音频文件路径
2. 替换所有 `{占位文字}` 为你的内容
3. 调整频段映射强度（subtle/medium/aggressive）
4. 改为竖屏：分辨率 1080×1920，标题字号调整为 80px
5. 添加歌词 caption 同步显示
