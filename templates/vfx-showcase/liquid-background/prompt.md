使用 HyperFrames 帮我创建一段液体流动背景的品牌宣传视频。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：有机流体 + 现代极简

## 背景流体层
使用 canvas 创建 4 个流体色块（blob），使用 vertex displacement 模拟有机流动：
- 色块配色：#4F46E5（品牌主色）、#7C3AED（辅色）、#F59E0B（暖色点缀）、#06B6D4（冷色点缀）
- 每个 blob 以不同的频率和振幅缓慢变形（使用 simplex noise 驱动顶点位移）
- 色块之间使用 CSS mix-blend-mode: screen 混合
- 整体运动速度：慢（0.3x），营造呼吸感和冥想感
- 添加 CSS blur(40px) 让色块边缘柔和

## 前景内容层
在流体背景之上，放置以下前景内容（不受流体影响）：

**场景 1（0-5s）— Logo 揭示**
- 品牌名 "[你的品牌名]" 从模糊中浮现：blur(20px) → blur(0)，配合 opacity 0 → 1
- 字体：Inter Black，字号 96px，颜色 #FFFFFF
- 入场动画：sine.inOut，1.2s

**场景 2（5-12s）— 价值主张**
- 三条价值主张依次从下方淡入，每条间隔 1.5s：
  1. "[价值主张 1]"
  2. "[价值主张 2]"
  3. "[价值主张 3]"
- power3.out，translateY(30px) → translateY(0)
- 字号 48px，字重 SemiBold，颜色 #E2E8F0

**场景 3（12-20s）— CTA + 背景淡出**
- "[你的 CTA 文案]" 居中显示，字号 64px
- 下方 URL，字号 32px
- 流体色块逐渐减速 0.3x → 0.05x
- 最后 2 秒整体降暗到 opacity 0.3

## 转场
- 场景 1 → 2：Cross Warp Morph（1.0s）
- 场景 2 → 3：Domain Warp Dissolve（1.2s）

## 技术注意事项
- 使用 simplex-noise CDN 库生成有机运动
- 所有 GSAP timeline 注册到 window.__timelines
- 不使用 Math.random()，用 seeded PRNG
- 添加 Grain Overlay 增加质感
