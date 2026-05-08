# Creative Intro — 电影感创意开场

## 效果

25 秒的电影感品牌开场序列。从一个微光开始，逐渐揭示品牌名、标语、全称，最后回归寂静。全程胶片颗粒 + 2.35:1 宽银幕比例。

## 适用场景

- 品牌宣传片片头
- 创意工作室/设计公司官网视频背景
- 众筹/Kickstarter 视频开场
- 纪录片片头

## 关键技巧

- **宽银幕比例**：用 CSS letterbox（上下黑边）模拟 2.35:1，不需要改实际分辨率
- **光的叙事**：全片由微光引导视线——在哪里亮起来，观众就看哪里
- **模糊入场**：文字从 blur(30px) → blur(0) 比直接 fade-in 更有「对焦」的电影感
- **胶片颗粒**：用 SVG feTurbulence 做 grain 纹理，不依赖外部资源
- **"最后一口气"**：片尾光点闪烁两次才灭，给观众留 2 秒回味

## 自定义方法

1. 替换所有 `UNCHARTED` / `UNCHARTED STUDIOS` 为你的品牌名
2. 修改 `#C9A96E`（暖金）为你的品牌色（出现在 4 处：spark glow、hero word shadow、streak、final spark）
3. 修改 `CREATIVE STUDIO — EST. 2026` 为你的标语
4. 调整场景时长：修改每个 `data-duration` 值，确保总和 = 目标时长
5. 颗粒强度：`.grain { opacity: 0.25 }` 改大/改小

## 需要安装的 Blocks

```bash
npx hyperframes add grain-overlay
```

## 预期产出

渲染后得到一个呼吸感极强的暗色开场视频，光与文字的交替像是「品牌在黑暗中苏醒」。
