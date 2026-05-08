# HyperFrames Prompt 工程技巧

## 核心原理

HyperFrames 的 Prompt 不同于普通 AI 对话——你需要让 AI agent 产出**结构化的 HTML 代码**，而不是自由文本。好的 Prompt = 让 AI 理解"要做什么视频"并把它翻译成 HTML + data 属性。

## 结构化 Prompt 公式

一个高质量的 HyperFrames Prompt 必须包含以下 6 个维度：

```
## 1. 视频规格
- 时长：[X 秒]
- 分辨率：[1920x1080 / 1080x1920 / 1080x1080]
- 帧率：[30fps]

## 2. 视觉风格
- 配色方案：[主色 #hex, 辅色 #hex, 背景色 #hex]
- 字体：[标题字体, 正文字体]
- 整体氛围：[科技感 / 温馨 / 暗黑 / 明亮 / 极简 / 奢华]

## 3. 场景结构
- 场景 1（0-Xs）：[描述画面内容 + 动画效果]
- 场景 2（Xs-Ys）：[描述画面内容 + 动画效果]
- ...

## 4. 动画要求
- 入场动画：[fade-in / slide-up / scale / 自定义]
- 转场效果：[crossfade / slide / zoom / 无]
- 持续动画：[pulse / float / scroll / 自定义]

## 5. 音频设计
- 背景音乐：[风格 / BPM / 情绪]
- 音效：[需要哪些音效点]
- 旁白/配音：[语速 / 语调 / 语言]

## 6. 技术约束
- 使用 HyperFrames blocks：[列出需要的 block 名称]
- 动画引擎：[GSAP / CSS Animations / Anime.js]
- 需要 TTS：[是/否，语言/声音]
```

## 10 条黄金法则

### 1. 场景分段比长描述更重要

❌ 差： "做一个 30 秒的产品介绍视频，展示我们的 App 功能"
✅ 好： "做一个 30 秒的产品视频，分 5 个场景：(1) logo 入场 0-3s (2) 痛点文字 3-8s (3) 功能展示 8-18s (4) 用户好评 18-25s (5) CTA 结尾 25-30s"

**原因**：AI 需要时间锚点来设置 `data-start` 和 `data-duration`。

### 2. 给具体的数值，不要用模糊词

❌ 差： "大标题" "快一点" "好看的颜色"
✅ 好： "72px 标题" "0.5s 入场动画" "背景 #0a0a1a，主色 #6c5ce7"

### 3. 提供品牌资产清单

```
品牌资产：
- Logo URL: https://example.com/logo.svg
- 产品截图：https://example.com/app-preview.png
- 品牌色：主色 #FF6B35, 辅色 #004E89
- 字体：标题用 Inter Bold，正文用 Inter Regular
- 图标集：使用 Lucide Icons
```

### 4. 动画要描述"起止状态"，不只是动效名称

❌ 差： "标题淡入"
✅ 好： "标题从 opacity: 0, y: 30px 动画到 opacity: 1, y: 0，持续 0.6s，ease-out"

### 5. 善用参考影片

```
参考风格：Apple 2023 WWDC 开场视频的节奏感
具体参考：0:15-0:20 那段文字快切的效果
```

AI agent 对"Apple WWDC 开场"有概念，能更准确理解你的审美诉求。

### 6. 音视频同步要显式标注

```
场景 2（3s-8s）：
- 画面：功能图标依次弹出，每个间隔 0.3s
- 音频：每个图标弹出时伴随轻快的 "pop" 音效（用 HyperFrames 的 sfx-pop block 或者自定义音频）
- BGM：从此刻开始 BGM 音量从 80% 降到 40%，突出音效
```

### 7. 使用 HyperFrames 专有名词

AI agent 对框架的术语越熟悉，产出越精准：

- 使用 `data-composition-id` 而非 "视频容器"
- 使用 `data-track-index` 来描述层级关系
- 使用 `data-start` / `data-duration` 来描述时间
- 提到具体 block 名称：`social-overlay`、`shader-transition`、`data-chart`

### 8. 迭代修改用 diff 式指令

当你已有第一版 HTML，要修改时：

❌ 差： "把标题改大一点"
✅ 好： "把 data-id='hero-title' 的 font-size 从 48px 改为 72px，入场动画从 fade-in 改为 scale-up + fade-in 组合"

### 9. 复杂度分层控制

不同用途的视频，Prompt 详细度不同：

| 用途 | Prompt 长度 | 重点 |
|------|------------|------|
| 快速 Demo | 100-200 字 | 只描述核心场景和配色 |
| 正式宣传片 | 500-800 字 | 完整 6 维度 + 参考影片 |
| 批量生产 | 200-300 字 | 模板化 prompt，只改变内容变量 |
| 创意实验 | 300-500 字 | 强调风格探索空间，给 AI 更多自由度 |

### 10. 给 AI 看"好样本"

在 Prompt 末尾附上一段好的 HTML 片段作为风格锚定：

```
风格参考代码片段（这是你之前生成的效果参考，不是本次的内容）：
```html
<div data-composition-id="title-slide" style="
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  display: flex; align-items: center; justify-content: center;
">
  <h1 style="font: 800 64px 'Inter'; color: white; letter-spacing: -2px;">
    The Future is Here
  </h1>
</div>
```

## 常见错误与纠正

| 错误 | 为什么不行 | 纠正方式 |
|------|-----------|---------|
| "做一个很酷的视频" | AI 不知道"酷"是什么 | 描述具体视觉元素：暗色背景 + 霓虹光效 + 快速剪辑 |
| 不指定时长 | AI 会随意安排节奏 | 每个场景标注起止时间 |
| 不指定分辨率 | 可能生成 1080x1920 但你想要横屏 | 第一条就写清楚分辨率 |
| 一次性描述太长 | 超过 1500 字的 prompt，AI 容易遗漏细节 | 分场景写，或者在迭代中逐步细化 |
| 忽略 Block 复用 | 重复造轮子，重新写已有的组件 | 先用 `npx hyperframes add <block>` 查看可用 block |

## 进阶技巧

### Few-shot 模板法

给你最满意的 3 个历史视频的 Prompt+HTML 作为 few-shot 样例：

```
以下是我之前用过的 3 个 Prompt 和它们的 HTML 产出，请你学习它们的风格和代码质量：

[粘贴 3 组 Prompt + HTML]

现在，基于以上风格，帮我做一个新的视频：[新 Prompt]
```

### 风格一致性约束

当制作系列视频时：

```
风格约束：
- 片头和片尾使用与 [之前视频名] 完全一致的动画和时长
- 配色方案保持不变
- 转场统一使用 crossfade 0.5s
- 字体层级：场景标题 64px / 正文 24px / 注释 16px
```

### 多模态输入

将设计稿截图或参考图片丢给 AI：

```
[上传品牌 VI 手册截图]
[上传竞品视频的关键帧截图]
按照以上视觉标准，制作一个...
```

## 终极模板公式

```markdown
# 视频名称：[一句话概括]

## 基本信息
- 时长：[Xs]  |  分辨率：[WxH]  |  帧率：[N]fps

## 视觉系统
- 配色：[主色] + [辅色] + [背景] + [强调色]
- 字体：[标题字体名 + 粗细 + 大小范围] / [正文字体]
- 氛围关键词：[3-5 个形容词]

## 场景时间线
| 场景 | 时间 | 画面 | 动画 | 音频 |
|------|------|------|------|------|
| 1    | 0-Ns | ...  | ...  | ...  |
| 2    | ...  | ...  | ...  | ...  |

## 技术偏好
- Blocks：[列出]
- 动画引擎：[GSAP / CSS]
- 其他：[TTS / 字幕 / 特效]

## 参考
- 风格参考：[链接或描述]
- 代码参考：[可选，粘贴优秀 HTML 片段]
```
