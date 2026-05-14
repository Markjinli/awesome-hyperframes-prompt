使用 HyperFrames 创建一段音频同步节拍动画。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：高能量、霓虹暗底、现场音乐可视化感
- 音频：「[你的音乐文件路径].mp3」

## 音频频段映射

| 频段 | 频率 | 映射目标 | 效果 | 强度 |
|------|------|---------|------|------|
| Bass | 20-250Hz | `.hero-title` scale | Kick 驱动标题缩放 | 中度（1.0-1.08） |
| Mids | 250-2000Hz | `.accent-shape` rotation | 人声驱动图形旋转 | 微妙（±5°） |
| Treble | 2000-20000Hz | `.glow-layer` opacity | 镲片驱动光晕 | 微妙（0-0.4） |
| Amplitude | 全频段 | `.bg-gradient` brightness | 整体响度驱动亮度 | 中度（0.7-1.0） |

## 视觉设计

**背景层**
- 暗色渐变：#0A0A0A → #1A0A2E
- 响应 Amplitude：安静时 brightness 0.7，大声时 1.0

**主标题 `.hero-title`**
- "[你的标题]"，Inter Black，120px，颜色 #FFFFFF
- 响应 Bass：每个底鼓 scale 1.0 → 1.08，衰减 0.15s
- Bass 峰值时 text-shadow glow 加强

**副标题 `.sub-text`**
- "[副标题]"，48px，颜色 #A0A0B0
- 响应 Mids：微弱 Y 轴跟踪

**强调图形 `.accent-shape`**
- 几何装饰元素，颜色 #FF6B35 / #4ECDC4
- 响应 Mids + Treble 组合

**光晕层 `.glow-layer`**
- 径向渐变，颜色 #FFB800
- 响应 Treble：高频出现时发光

## 动画时间线
- 0-3s：Build Up（背景渐亮、标题浮现、音频渐入）
- 3-16s：Main Drop（全频段映射激活、重拍时 white flash opacity 0.06）
- 16-20s：Outro（映射减弱、标题缩小 fade out、CTA 淡入）

## 转场
- 段落切换：Flash Through White 0.3s 配合重拍

## 技术注意事项
- Web Audio API AnalyserNode，FFT size 256，smoothingTimeConstant 0.4
- 所有 GSAP timeline 注册到 window.__timelines
- 不使用 Math.random()
