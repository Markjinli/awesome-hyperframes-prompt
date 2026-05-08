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
│   └── motion-typography/  # 动态排版：文字动画、标题设计
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

## 模板速览

| 分类 | 模板数量 | 适用场景 |
|------|---------|---------|
| 产品宣传 | WIP | 科技产品发布、SaaS 功能演示、App 介绍 |
| 社交媒体 | WIP | 抖音/TikTok 短视频、Instagram Story/Reel |
| 教程教育 | WIP | 在线课程、知识科普、操作指南 |
| 数据可视化 | WIP | 数据报告、KPI 展示、趋势分析 |
| 品牌故事 | WIP | 企业文化、创始人访谈、品牌纪录片 |
| 活动宣传 | WIP | 大会预告、直播预热、促销活动 |
| 电影感 | WIP | 创意短片、情绪表达、艺术实验 |
| YouTube | WIP | 频道片头、视频解说、内容回顾 |
| 动态排版 | WIP | 文字动画、标题序列、转场设计 |

> 持续更新中，欢迎 PR 贡献你的模板！

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
