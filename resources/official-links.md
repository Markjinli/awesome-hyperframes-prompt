# 官方资源汇总

## HyperFrames 核心

- [HyperFrames 主仓库](https://github.com/heygen-com/hyperframes) — "Write HTML. Render video. Built for agents."
- [HyperFrames 官方作品集](https://github.com/heygen-com/hyperframes-launches) — HeyGen 产品发布视频的 HyperFrames 源码
- [HyperFrames 发布视频](https://github.com/heygen-com/hyperframes-launch-video) — HyperFrames 自己的发布宣传片

## 官方 Blocks & Components（63 个）

所有 Blocks 都在 [registry/](https://github.com/heygen-com/hyperframes/tree/main/registry) 目录下：

### Social Overlays
- `instagram-follow` — IG 关注卡片（4.5s, 1080x1920）
- `tiktok-follow` — TikTok 关注卡片（4.5s, 1080x1920）
- `yt-lower-third` — YouTube 订阅底部条（4.5s, 1920x1080）
- `x-post` — Twitter/X 帖子卡片（5s, 1920x1080）
- `reddit-post` — Reddit 帖子卡片（5s, 1920x1080）
- `spotify-card` — Spotify 播放卡片（5s, 1080x1920）
- `macos-notification` — macOS 通知样式（5s, 1920x1080）
- `logo-outro` — 电影感 Logo 片尾（6s, 1920x1080）

### Data & Diagrams
- `data-chart` — 柱状+折线图动画（15s, 1920x1080）
- `flowchart` — 水平决策树（12s, 1920x1080）
- `flowchart-vertical` — 垂直决策树（12s, 1440x2560）

### Product Showcases
- `app-showcase` — 三台手机 App 展示（5.5s, 1920x1080）
- `apple-money-count` — Apple 风格数字滚动（5s, 1920x1080）
- `vpn-youtube-spot` — App 安装演示（7s, 1920x1080）
- `blue-sweater-intro-video` — AI 创作者介绍（12s, 1920x1080）
- `nyc-paris-flight` — 地图飞行路线（6s, 1920x1080）
- `north-korea-locked-down` — 地图标注（7s, 1920x1080）
- `ui-3d-reveal` — 3D UI 展示（13s, 1920x1080）

### Shader Transitions（15 种，每组 4s）
- `glitch`, `flash-through-white`, `domain-warp-dissolve`, `ridged-burn`
- `whip-pan`, `sdf-iris`, `ripple-waves`, `gravitational-lens`
- `cinematic-zoom`, `chromatic-radial-split`, `swirl-vortex`
- `thermal-distortion`, `cross-warp-morph`, `light-leak`

### VFX / HTML-in-Canvas
- `vfx-text-cursor` — 着色器文字光效（8s）
- `vfx-liquid-background` — 流体背景（12s）
- `vfx-iphone-device` — 3D iPhone 模型（15s）
- `vfx-magnetic` — 磁力效果（15s）
- `vfx-portal` — 传送门效果（10s）
- `vfx-liquid-glass` — 液态玻璃（20s）
- `vfx-shatter` — 碎片爆炸（12s）

### Components
- `grain-overlay` — 胶片颗粒纹理
- `shimmer-sweep` — 光泽扫过
- `grid-pixelate-wipe` — 像素化擦除
- `texture-mask-text` — 66 种纹理遮罩文字

## 官方 Skills

- `hyperframes` — 核心视频制作技能
- `hyperframes-cli` — CLI 开发循环
- `hyperframes-media` — TTS/转录/去背景
- `hyperframes-registry` — Block 安装管理
- `website-to-hyperframes` — 网页转视频
- `remotion-to-hyperframes` — Remotion 迁移工具
- `gsap` / `animejs` / `css-animations` / `lottie` / `three` / `waapi` — 各动画引擎适配
- `tailwind` — Tailwind CSS v4.2 集成

## 安装命令速查

```bash
# 初始化项目
npx hyperframes init my-video
npx hyperframes init my-video --tailwind    # 带 Tailwind

# 安装 Skills
npx skills add heygen-com/hyperframes

# 安装 Blocks/Components
npx hyperframes add app-showcase
npx hyperframes add data-chart
npx hyperframes add glitch
npx hyperframes add logo-outro
npx hyperframes add grain-overlay

# 开发
npx hyperframes preview
npx hyperframes render

# 工具
npx hyperframes doctor     # 环境诊断
npx hyperframes lint       # 代码检查
npx hyperframes inspect    # 查看 composition 信息
```
