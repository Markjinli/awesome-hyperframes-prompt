# Liquid Background — 液态流体背景

> 使用 vertex displacement + CSS 混合模式创建有机流体背景，文字/内容漂浮在流体之上。

## 效果

15-20 秒的有机流体背景视频。液态色块在画面中缓慢流动、融合、变形，前景文字和 UI 元素稳定地漂浮在流体之上。适合品牌 intro、SaaS 产品宣传、创意短片。

## 适用场景

- SaaS/科技产品首页 Hero 视频背景
- 品牌价值观/愿景视频
- 创意工作室作品集开场
- 音乐节/活动宣传视觉

## Prompt 模板

````markdown
使用 HyperFrames 帮我创建一段液体流动背景的品牌宣传视频。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：有机流体 + 现代极简

## 背景流体层
使用 canvas 或 SVG 创建 3-5 个流体色块（blob），使用 vertex displacement 模拟有机流动：
- 色块配色：[品牌主色 #4F46E5]、[品牌辅色 #7C3AED]、[暖色调 #F59E0B]、[冷色调 #06B6D4]
- 每个 blob 以不同的频率和振幅缓慢变形（使用 simplex noise 驱动顶点位移）
- 色块之间使用 CSS mix-blend-mode: screen 或 soft-light 混合
- 整体运动速度：慢（0.3-0.5x），营造呼吸感和冥想感
- 添加微弱的 CSS blur(40px) 让色块边缘柔和

## 前景内容层
在流体背景之上，放置以下前景内容（不受流体影响）：

**场景 1（0-5s）— Logo 揭示**
- 品牌名 "[你的品牌名]" 从模糊中浮现：blur(20px) → blur(0)，配合 opacity 0 → 1
- 字体：粗体无衬线（如 Inter Black），字号 96px
- 颜色：白色 #FFFFFF
- 入场动画：sine.inOut，1.2s，缓慢优雅

**场景 2（5-12s）— 价值主张**
- 三条价值主张依次从下方淡入：
  1. "[价值主张 1]"（如 "Ship 10x faster"）
  2. "[价值主张 2]"（如 "Zero infrastructure"）
  3. "[价值主张 3]"（如 "Open source forever"）
- 每条间隔 1.5s，使用 power3.out，translateY(30px) → translateY(0)
- 字号：48px，字重：SemiBold
- 颜色：#E2E8F0

**场景 3（12-20s）— CTA + 背景淡出**
- "[你的 CTA 文案]" 居中显示（如 "Start building today"）
- 下方显示 GitHub URL 或产品 URL
- 字号：标题 64px，URL 32px
- 整个前景层的流体色块逐渐减速（从 0.3x → 0.05x）
- 最后 2 秒整体 opacity 降低到 0.3，给人留下余韵

## 转场
- 场景 1 → 2：Cross Warp Morph（画面像液体融合过渡）
- 场景 2 → 3：Domain Warp Dissolve（梦幻溶解）

## 技术注意事项
- 使用 simplex-noise 库（CDN）生成有机运动
- 流体层使用 requestAnimationFrame 驱动
- 所有 GSAP timeline 注册到 window.__timelines
- 不使用 Math.random()，用 seeded PRNG
- 导入 Grain Overlay 组件增加质感

## 音频
- 背景音乐：ambient electronic / chill wave（无歌词）
- 可选：轻量的低频脉冲音效在场景切换时出现
````

## 关键技巧

- **mix-blend-mode 是灵魂**：不是简单的 opacity 叠加，而是色彩混合，产生真正的液体感
- **慢就是快**：流体运动速度控制在 0.3-0.5x，太快像故障，太慢像静止
- **噪声驱动的自然感**：sin/cos 周期运动太机械，simplex noise 才是有机感的来源
- **前景分离**：不要让文字跟着流体变形——前景保持稳定，形成「液体背景 + 稳定前景」的对比

## 需要安装的 Blocks

```bash
npx hyperframes add liquid-background
npx hyperframes add grain-overlay
```

## 自定义方法

1. 替换 `#4F46E5` / `#7C3AED` 等颜色为你的品牌色
2. 替换 `[品牌名]`、`[价值主张]`、`[CTA 文案]`
3. 调整 blob 数量：3 个 = 极简，5 个 = 丰富，7+ 个 = 混乱
4. 调整运动速度：品牌视频 0.3x，社交媒体 0.6x
5. 调整 blur 半径：更模糊 = 更梦幻，更清晰 = 更有形
