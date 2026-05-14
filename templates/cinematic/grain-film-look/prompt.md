使用 HyperFrames 创建一段模拟胶片质感的品牌视频。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：24fps（电影帧率）
- 风格：16mm 胶片模拟 — 颗粒、暖调、2.35:1 宽银幕

## 胶片质感层（全程叠加）

**颗粒纹理**
- SVG feTurbulence 生成胶片颗粒
- opacity：0.15
- 每帧种子变化，模拟真实胶片随机分布

**宽银幕遮幅**
- 上下黑条：各 140px
- 入场：黑条从中央向外展开

**色彩偏移**
- 全局：暖色 +5%，绿色 -2%
- 高光：微黄偏移
- 阴影：微青偏移（胶片暗部冷调）

**对焦呼吸**
- 场景切换时：blur(12px) → blur(0)，0.8s
- 模拟镜头对焦，只在情感转折点使用

## 场景内容

**场景 1（0-6s）— 标题浮现**
- 暗底，品牌名从完全模糊中「对焦」
- blur(30px)→blur(0)，sine.inOut，1.5s
- 字体：Playfair Display Bold，96px，颜色 #F5F0EB
- 暖金色光晕在文字后方扩散
- 颗粒和遮幅在 0.5s 内淡入

**场景 2（6-14s）— 品牌叙述**
- 温暖抽象背景（渐变 + 柔焦光斑）
- 两段文案依次浮现：
  1. "[品牌理念第一句]"
  2. "[品牌理念第二句]"
- blur(8px)→blur(0)，每段停留 3s
- 字体：Cormorant Garamond Regular，48px，颜色 #FFF8F0
- 行间距 1.6

**场景 3（14-20s）— 闭幕**
- 所有文字淡出
- 遮幅从外向内闭合
- 中央小字：[brand.com]
- 最后 1s：全黑 + 颗粒在暗处闪烁

## 字体
- 标题：Playfair Display Bold
- 正文：Cormorant Garamond Regular
- 启用 font-variant-ligatures

## 调色参考（Kodak Portra 400 感）
- 高光：偏暖 #FFF8F0
- 阴影：偏冷 #1A1A2E + 微青

## 音频
- Ambient cinematic drone（无节奏纯氛围）
- 可选：微弱胶片投影仪声

## 技术注意事项
- 颗粒用 SVG feTurbulence filter，不依赖外部资源
- 24fps 渲染（不是 30fps）
- GSAP timeline 注册到 window.__timelines
- 颗粒种子用 frameIndex 计算，不用 Math.random()
