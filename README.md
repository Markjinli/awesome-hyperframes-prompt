# 🎬 Awesome HyperFrames Prompts

> Write HTML. Render video. Built for agents. Now with battle-tested prompts.

**Awesome HyperFrames Prompts** 是一个精选的 HyperFrames Prompt 模板库。每个模板都包含 **Prompt → HTML 成品 → 效果预览** 的完整链路，让你和 AI agent 协作制作视频时开箱即用。

## 为什么需要这个仓库？

HyperFrames 让你用 HTML 制作视频，但你得先告诉 AI agent 你想要什么。90% 的初学者卡在第一步：**"我该怎么描述我想要的那个视频？"**

这个仓库解决的就是这个问题——你不必从零开始设计 prompt，直接拿现成的模板改内容就行。

```
你改好的 Prompt  →  AI Agent  →  HTML 视频源码  →  npx hyperframes render → MP4
      ↑
  这个仓库提供的就是这一步的脚手架
```

## 目录结构

```
awesome-hyperframes-prompt/
├── templates/              # 🎯 核心：Prompt 模板 + HTML 成品
│   ├── product-showcase/   # 产品宣传：科技发布、SaaS 演示、App 推广
│   ├── social-media/       # 社交媒体：短视频、Story、TikTok
│   ├── tutorial-education/ # 教程教育：课程视频、知识科普
│   ├── data-visualization/ # 数据可视化：图表动画、数据叙事
│   ├── brand-story/        # 品牌故事：企业文化、创始人访谈
│   ├── event-promo/        # 活动宣传：大会预告、直播引流
│   ├── cinematic/          # 电影感：创意短片、艺术表达
│   ├── youtube-content/    # YouTube：频道片头、内容解说
│   ├── motion-typography/  # 动态排版：文字动画、标题设计
│   ├── vfx-showcase/       # VFX 特效：液态流体、粒子效果
│   ├── 3d-product/         # 3D 产品：设备360°展示
│   ├── voiceover-explainer/# 语音旁白：TTS 产品介绍
│   ├── audio-reactive/     # 音频同步：节拍驱动动画
│   ├── app-social/         # 社交通知：平台UI叠加层
│   ├── code-workflow/      # 代码工作流：开发者工具发布
│   └── comparison/         # 对比展示：分屏对比
├── techniques/             # 📖 技巧指南
├── case-studies/           # 🔬 深度案例拆解
│   ├── official/           # 官方案例逆向解析
│   └── community/          # 社区优秀案例分析
└── resources/              # 🔗 资源汇总
```

## 快速开始

### 1. 安装 HyperFrames

```bash
npx hyperframes init my-video
cd my-video
```

### 2. 选一个模板

浏览 [`templates/`](./templates/) 目录，找到适合你需求的模板，复制 Prompt 内容。

### 3. 修改 Prompt

替换模板中的占位内容（产品名、品牌色、文案等），改成你自己的。

### 4. 交给 AI Agent

把改好的 Prompt 发给 Claude Code / Cursor / Gemini CLI 等 AI agent，让它生成 `index.html`。

```bash
# 如果你用 Claude Code，直接说：
# "请用 HyperFrames 帮我做一段视频，规格如下：[粘贴你改好的 Prompt]"
```

### 5. 预览 & 渲染

```bash
npx hyperframes preview   # 浏览器实时预览
npx hyperframes render    # 导出 MP4
```

## 渲染预览

每个模板都包含完整渲染的 GIF 预览（可直接播放）和 MP4 下载。共 13 个模板已完成渲染。

### 产品宣传

<p align="center">
  <b>Tech Product Launch</b> · 30s<br>
  <img src="./output/gif/product-showcase--tech-product-launch.gif" width="600"><br>
  <sub><a href="./output/mp4/product-showcase--tech-product-launch.mp4">📥 下载 MP4</a> · <a href="./templates/product-showcase/tech-product-launch/">📂 模板</a></sub>
</p>

<p align="center">
  <b>SaaS Feature Demo</b> · 30s<br>
  <img src="./output/gif/product-showcase--saas-feature-demo.gif" width="600"><br>
  <sub><a href="./output/mp4/product-showcase--saas-feature-demo.mp4">📥 下载 MP4</a> · <a href="./templates/product-showcase/saas-feature-demo/">📂 模板</a></sub>
</p>

<p align="center">
  <b>App Promo</b> · 30s<br>
  <img src="./output/gif/product-showcase-app-promo.gif" width="300"><br>
  <sub><a href="./output/mp4/product-showcase-app-promo.mp4">📥 下载 MP4</a> · <a href="./templates/product-showcase/app-promo/">📂 模板</a></sub>
</p>

### 电影感

<p align="center">
  <b>Creative Intro</b> · 12s<br>
  <img src="./output/gif/cinematic--creative-intro.gif" width="600"><br>
  <sub><a href="./output/mp4/cinematic--creative-intro.mp4">📥 下载 MP4</a> · <a href="./templates/cinematic/creative-intro/">📂 模板</a></sub>
</p>

<p align="center">
  <b>Emotional Story</b> · 30s<br>
  <img src="./output/gif/cinematic--emotional-story.gif" width="600"><br>
  <sub><a href="./output/mp4/cinematic--emotional-story.mp4">📥 下载 MP4</a> · <a href="./templates/cinematic/emotional-story/">📂 模板</a></sub>
</p>

### 品牌故事

<p align="center">
  <b>Company Origin</b> · 30s<br>
  <img src="./output/gif/brand-story--company-origin.gif" width="600"><br>
  <sub><a href="./output/mp4/brand-story--company-origin.mp4">📥 下载 MP4</a> · <a href="./templates/brand-story/company-origin/">📂 模板</a></sub>
</p>

<p align="center">
  <b>Brand Values</b> · 30s<br>
  <img src="./output/gif/brand-story--brand-values.gif" width="600"><br>
  <sub><a href="./output/mp4/brand-story--brand-values.mp4">📥 下载 MP4</a> · <a href="./templates/brand-story/brand-values/">📂 模板</a></sub>
</p>

### 社交媒体

<p align="center">
  <b>Social Ad</b> · 30s<br>
  <img src="./output/gif/social-media--social-ad.gif" width="600"><br>
  <sub><a href="./output/mp4/social-media--social-ad.mp4">📥 下载 MP4</a> · <a href="./templates/social-media/social-ad/">📂 模板</a></sub>
</p>

<p align="center">
  <b>Short Reel</b> · 15s<br>
  <img src="./output/gif/social-media--short-reel.gif" width="300"><br>
  <sub><a href="./output/mp4/social-media--short-reel.mp4">📥 下载 MP4</a> · <a href="./templates/social-media/short-reel/">📂 模板</a></sub>
</p>

### 活动宣传

<p align="center">
  <b>Product Launch Event</b> · 30s<br>
  <img src="./output/gif/event-promo--product-launch-event.gif" width="600"><br>
  <sub><a href="./output/mp4/event-promo--product-launch-event.mp4">📥 下载 MP4</a> · <a href="./templates/event-promo/product-launch-event/">📂 模板</a></sub>
</p>

### YouTube

<p align="center">
  <b>Video Essay</b> · 20s<br>
  <img src="./output/gif/youtube-content--video-essay.gif" width="600"><br>
  <sub><a href="./output/mp4/youtube-content--video-essay.mp4">📥 下载 MP4</a> · <a href="./templates/youtube-content/video-essay/">📂 模板</a></sub>
</p>

<p align="center">
  <b>Channel Intro</b> · 10s<br>
  <img src="./output/gif/youtube-content--channel-intro.gif" width="600"><br>
  <sub><a href="./output/mp4/youtube-content--channel-intro.mp4">📥 下载 MP4</a> · <a href="./templates/youtube-content/channel-intro/">📂 模板</a></sub>
</p>

### 动态排版

<p align="center">
  <b>Kinetic Title "MOMENTUM"</b> · 10s<br>
  <img src="./output/gif/motion-typography--kinetic-title.gif" width="600"><br>
  <sub><a href="./output/mp4/motion-typography--kinetic-title.mp4">📥 下载 MP4</a> · <a href="./templates/motion-typography/kinetic-title/">📂 模板</a></sub>
</p>

## 模板速览

| 分类 | 模板数量 | 已渲染 | 适用场景 |
|------|---------|--------|---------|
| 产品宣传 | 3 | ✅ 3 | 科技产品发布、SaaS 功能演示、App 介绍 |
| 社交媒体 | 2 | ✅ 2 | 短视频、社交广告 |
| 教程教育 | 2 | ⏳ | 在线课程、知识科普 |
| 数据可视化 | 2 | ⏳ | 数据报告、KPI 展示、趋势分析 |
| 品牌故事 | 2 | ✅ 2 | 企业文化、创始人访谈 |
| 活动宣传 | 2 | ✅ 1 | 大会预告、直播预热 |
| 电影感 | 3 | ✅ 2 | 创意短片、情绪表达、胶片质感 |
| YouTube | 2 | ✅ 2 | 频道片头、视频解说 |
| 动态排版 | 2 | ✅ 1 | 文字动画、标题序列 |
| VFX 特效 | 1 | 🆕 | 液态流体背景 |
| 3D 产品 | 1 | 🆕 | 设备 360° 展示 |
| 语音旁白 | 1 | 🆕 | TTS 驱动产品介绍 |
| 音频同步 | 1 | 🆕 | 节拍驱动的视觉动画 |
| 社交通知 | 1 | 🆕 | 平台 UI 卡片叠加 |
| 代码工作流 | 1 | 🆕 | 开发者工具发布视频 |
| 对比展示 | 1 | 🆕 | 分屏对比 / 之前 vs 之后 |

> 共 28 个模板，持续更新中。🆕 标记为本次新增的 8 个模板。

## 每个模板包含什么

```
templates/product-showcase/tech-product-launch/
├── README.md       # 效果说明 + 适用场景 + 关键技巧
├── prompt.md       # 可直接复用的 Prompt 模板（含占位变量）
└── index.html      # 该 Prompt 生成的 HTML 成品（可直接渲染）
```

## 技巧指南

| 文档 | 内容 |
|------|------|
| [Prompt 工程技巧](./techniques/prompt-engineering.md) | 如何写出高质量视频描述、结构化 Prompt 公式 |
| [动画模式](./techniques/animation-patterns.md) | GSAP / CSS Animations 在 HyperFrames 中的最佳实践 |
| [视觉风格指南](./techniques/styling-guide.md) | 配色、排版、构图的审美原则 |
| [Block 组合技巧](./techniques/block-combos.md) | 50+ 官方 Block 的高效组合方式 |
| [Agent 协作工作流](./techniques/agent-workflow.md) | 多轮迭代、版本管理、团队协作流程 |
| [Shader 转场深度指南](./techniques/shader-transitions.md) | 14 种 WebGL Shader 转场的选择与调参 |
| [音频同步动画](./techniques/audio-reactive.md) | Bass/Treble/Amplitude 频段映射到视觉属性 |
| [Caption 风格模式](./techniques/caption-styles.md) | 5 种字幕风格（Hype/Corporate/Tutorial/Storytelling/Social）|
| [TTS + Voiceover 工作流](./techniques/tts-voiceover.md) | 脚本写作 → TTS 生成 → 时间线同步全流程 |

## 贡献指南

1. Fork 本仓库
2. 在 `templates/` 下选择分类，创建你的模板目录
3. 每个模板目录必须包含 `prompt.md`(Prompt 模板) + `index.html`(HTML 成品) + `README.md`(效果说明)
4. 提交 PR

模板审核标准：
- ✅ Prompt 结构化，有明确的占位变量
- ✅ HTML 可直接在 HyperFrames 中渲染
- ✅ 成品具有足够的审美质量
- ✅ 说明文档清晰完整

## 相关资源

- [HyperFrames 官方](https://github.com/heygen-com/hyperframes)
- [HyperFrames 官方作品集](https://github.com/heygen-com/hyperframes-launches)
- [HyperFrames 学生工具包](https://github.com/nateherkai/hyperframes-student-kit)
- [HyperFrames Helper](https://github.com/robonuggets/hyperframes-helper)

## 致谢

本项目受 [awesome](https://github.com/topics/awesome) 系列启发，致力于降低 HyperFrames 的使用门槛，让更多人能做出审美在线的 AI 视频。

## License

MIT
