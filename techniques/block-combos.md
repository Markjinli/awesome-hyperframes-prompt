# HyperFrames Block 组合技巧

HyperFrames 官方提供了 51 个 Blocks + 4 Components + 8 Examples，共 63 个预制资产。掌握它们的组合方式，能让你的视频从 60 分到 95 分。

## 目录

- [快速总览](#快速总览)
- [Block 组合公式](#block-组合公式)
- [按场景推荐组合](#按场景推荐组合)
- [Shader Transitions 选型指南](#shader-transitions-选型指南)
- [Components 增强技巧](#components-增强技巧)

## 快速总览

### 社交覆盖层（Social Overlays）— 8 个
| Block | 时长 | 用途 |
|-------|------|------|
| `instagram-follow` | 4.5s | 片尾引流 IG |
| `tiktok-follow` | 4.5s | 片尾引流 TikTok |
| `yt-lower-third` | 4.5s | 视频中底部订阅提示 |
| `x-post` | 5s | 展示 Twitter/X 帖子 |
| `reddit-post` | 5s | 展示 Reddit 帖子 |
| `spotify-card` | 5s | 音乐推荐卡片 |
| `macos-notification` | 5s | 模拟 macOS 通知 |
| `logo-outro` | 6s | 电影感 Logo 片尾 |

### 数据 & 图表（Data & Diagrams）— 3 个
| Block | 时长 | 用途 |
|-------|------|------|
| `data-chart` | 15s | 柱状图 + 折线图动画 |
| `flowchart` | 12s | 水平决策树动画 |
| `flowchart-vertical` | 12s | 垂直决策树动画 |

### 产品展示（Showcase）— 7 个
| Block | 时长 | 用途 |
|-------|------|------|
| `app-showcase` | 5.5s | App 产品展示（3 台手机） |
| `apple-money-count` | 5s | Apple 风格数字滚动 |
| `vpn-youtube-spot` | 7s | 轻快 App 安装演示 |
| `blue-sweater-intro-video` | 12s | AI 创作者介绍片 |
| `nyc-paris-flight` | 6s | 地图飞行路线动画 |
| `north-korea-locked-down` | 7s | 地图标注 + 区域锁定 |
| `ui-3d-reveal` | 13s | 3D 透视 UI 展示 |

### Shader 转场（Shader Transitions）— 15 个（每组 4s）
| 类别 | Blocks |
|------|--------|
| 故障/数字感 | `glitch`, `chromatic-radial-split` |
| 溶解/融合 | `domain-warp-dissolve`, `cross-warp-morph`, `ridged-burn` |
| 光线/漏光 | `flash-through-white`, `light-leak` |
| 变形/扭曲 | `swirl-vortex`, `thermal-distortion`, `gravitational-lens` |
| 运动/镜头 | `whip-pan`, `cinematic-zoom` |
| 形状/波纹 | `sdf-iris`, `ripple-waves` |

### 转场展示合集（Transition Showcases）— 13 个
按类别：`3d`, `blur`, `cover`, `destruction`, `dissolve`, `distortion`, `grid`, `light`, `mechanical`, `other`, `push`, `radial`, `scale`

### VFX / WebGL（7 个）
| Block | 时长 | 描述 |
|-------|------|------|
| `vfx-text-cursor` | 8s | Canvas 着色器文字光效 |
| `vfx-liquid-background` | 12s | 流体模拟背景 |
| `vfx-iphone-device` | 15s | 真实 3D iPhone + MacBook 模型 |
| `vfx-magnetic` | 15s | WebGL 磁力效果 |
| `vfx-portal` | 10s | WebGL 传送门效果 |
| `vfx-liquid-glass` | 20s | WebGL 液态玻璃 |
| `vfx-shatter` | 12s | WebGL 碎片爆炸 |

### Components（4 个效果组件）
| Component | 用途 |
|-----------|------|
| `grain-overlay` | 胶片颗粒纹理 |
| `shimmer-sweep` | 光泽扫过效果 |
| `grid-pixelate-wipe` | 像素化擦除转场 |
| `texture-mask-text` | 66 种纹理遮罩文字 |

---

## Block 组合公式

### 公式 1：产品发布视频 (25-30s)

```
片头 (0-4s):
  custom: 暗色背景 + Logo 居中，GSAP scale + blur 入场
  
场景 1 (4-8s):
  custom: 问题陈述文字
  
场景 2 (8-16s):
  app-showcase       ← 三台手机展示 App 界面
  (或 ui-3d-reveal)  ← 3D UI 展示（更有冲击力）

场景 3 (16-22s):
  data-chart          ← 增长数据、KPI 展示
  + apple-money-count ← 营收/用户数滚动

片尾 (22-28s):
  logo-outro          ← 电影感 Logo 谢幕

增强层（全局）:
  grain-overlay       ← 胶片质感
  shader transition 作为场景 3→4 的转场
```

### 公式 2：技术教程/讲解视频 (15-20s)

```
片头 (0-3s):
  custom: 标题文字 + 微妙的背景动画

主体 (3-12s):
  flowchart / flowchart-vertical ← 核心逻辑展示（决策树/流程）
  + yt-lower-third              ← 底部订阅提示（第 5s 触发）
  
数据支撑 (12-16s):
  data-chart                     ← 数据佐证
  （如果不需要数据，换成 vfx-text-cursor 做关键代码展示）

片尾 (16-20s):
  logo-outro
  + spotify-card（如果是播客/音频内容）
```

### 公式 3：社交媒体短视频 (10-15s，竖屏 1080x1920)

```
片头 (0-1.5s):
  custom: 大标题直击痛点，快节奏

主体 (1.5-8s):
  instagram-follow 或 tiktok-follow  ← 放在内容高潮处（第 5-6s）
  + app-showcase                     ← 产品功能快展

高潮 (8-11s):
  apple-money-count  ← 关键数字强冲击
  
收尾 (11-13s):
  logo-outro（竖屏版）

转场全部用 glitch 或 whip-pan（快节奏感）
```

### 公式 4：数据报告/年度总结 (30-45s)

```
片头 (0-5s):
  custom: 年份标题 + 氛围

数据序列 (5-25s):
  data-chart × 3-4 次（展示不同维度的数据）
  用不同的转场连接：
  - 场景间用 ripple-waves（正式感）
  - 重点数据前用 cinematic-zoom（强调）

地图展示 (25-32s):
  nyc-paris-flight 或 north-korea-locked-down
  （展示地域分布或市场覆盖）

片尾 (32-38s):
  logo-outro
  全程叠加 grain-overlay 增加质感
```

### 公式 5：品牌故事/创始人访谈 (45-60s)

```
片头 (0-8s):
  custom: 品牌名 + 创始年份
  + vfx-liquid-background（有机背景流动）

故事线 (8-35s):
  blueprint-intro-video 的风格参考
  + flow-chart（展示品牌发展里程碑）
  
产品展示 (35-45s):
  vfx-iphone-device（如果是 App/硬件）
  或 ui-3d-reveal

价值观 (45-52s):
  custom: 大字排版 + 品牌色

片尾 (52-58s):
  logo-outro
  + grain-overlay
  + shimmer-sweep 扫过 Logo

全程使用 cinematic-zoom 或 domain-warp-dissolve 做场景转场（温情感）
```

---

## Shader Transitions 选型指南

选择转场直接影响视频的情绪和风格：

| 视频风格 | 推荐转场 | 原因 |
|---------|---------|------|
| 🤖 科技/硬核 | `glitch` + `chromatic-radial-split` | 数字故障感 = 科技 |
| 🎬 电影感 | `cinematic-zoom` + `light-leak` | 模拟摄影机的光学特性 |
| 💎 高端/奢华 | `domain-warp-dissolve` + `sdf-iris` | 流动溶解显得优雅 |
| ⚡ 快节奏/活力 | `whip-pan` + `flash-through-white` | 快速动感 + 干脆切换 |
| 🎨 创意/艺术 | `swirl-vortex` + `gravitational-lens` | 扭曲变形增加艺术感 |
| 🌊 柔和/自然 | `ripple-waves` + `cross-warp-morph` | 水波/融合 = 柔美 |
| 🔥 激情/冲击 | `ridged-burn` + `thermal-distortion` | 燃烧/热浪 = 冲击力 |

### 转场搭配禁忌

| 不要用 | 原因 |
|--------|------|
| `glitch` + 奢华品牌 | 故障感和高端感互斥 |
| `flash-through-white` + 暗黑风格全程 | 突然的白色闪光会刺眼 |
| 全程用同一个转场 | 观众会审美疲劳 |
| 每个场景用不同转场 | 视觉语言不统一 |

### 转场节奏建议

```
30s 视频的最佳转场分布：
- 2-3 个不同转场类型
- 主转场（70% 场景用）：如 cinematic-zoom
- 强调转场（1-2 个关键时刻）：如 glitch（高潮）+ light-leak（片尾）
- 柔和转场（其余）：如 domain-warp-dissolve
```

---

## Components 增强技巧

### grain-overlay 的妙用

```css
/* 叠加胶片颗粒可以 */
- 让纯色背景更有质感（0.3 透明度）
- 让暗色场景有"电影感"（0.5 透明度）
- 掩盖渲染中的细微 banding 问题

/* 不要用 */
- 在高亮/白色背景上（颗粒感太明显，显脏）
- 透明度超过 0.6（太重，干扰内容）
```

### shimmer-sweep 的应用时机

```
最佳应用点：
- Logo 动画的最后 0.5s（收尾高光）
- "New" / "Featured" 标签上循环
- 数据图表的最高柱子
- CTA 按钮做 hover 效果
```

### grid-pixelate-wipe 的场景

```
最适合用在：
- 从品牌片头过渡到正式内容（"大幕拉开"的感觉）
- 从一段内容过渡到完全不同的主题（像素化 = 视觉重置）
- 游戏/科技相关视频的转场

不适合：
- 温情/柔和风格的视频（像素感太硬）
```

### texture-mask-text 的 66 种纹理

```
纹理类型速查（来自 ambientCG PBR 材质库）：
- 石材纹理：粗粝感标题
- 木材纹理：自然/手作品牌
- 布料纹理：服装/时尚
- 金属纹理：工业/科技
- 有机纹理：健康/自然
```

---

## 常用 Block 的 Prompt 指令

### 安装 Block

```
"先用 npx hyperframes add app-showcase 安装 App 展示 block，
然后把它放在场景 2 中，时间从 5s 到 12s。"
```

### 自定义 Block

```
"logo-outro block 安装好了，但我需要你：
1. 把 Logo 换成我们的 logo.svg
2. Tagline 改成 'Build the Future'
3. URL pill 改成 'example.com'
4. 背景色改为我们的品牌色 #0A0A1A"
```

### 组合多个 Block

```
"场景 2 需要同时展示：
- app-showcase 在左侧（占 60% 宽度）
- data-chart 在右侧（占 40% 宽度）
两者用不同的 track-index，app 在 track 2，chart 在 track 3。
同步展示，都在 5s-15s 时间段。"
```

### 转场放在特定位置

```
"场景 2 结束（第 15s）时，用 glitch transition 过渡到场景 3。
场景 2 的内容在 14.5s 开始做 exit 动画（fade-out），
glitch 在 14.8s 触发，持续到 15.5s，
场景 3 的内容在 15.3s 开始入场。"
```
