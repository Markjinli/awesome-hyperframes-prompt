# 案例拆解：HeyGen HyperFrames 发布视频

## 基本信息

- **案例来源**：[hyperframes-launch-video](https://github.com/heygen-com/hyperframes-launch-video)（开源）
- **视频类型**：产品发布宣传片
- **时长**：约 60s
- **分辨率**：1920x1080
- **难度**：⭐⭐⭐⭐（高级）
- **代码行数**：~500+ 行 HTML

## 这个案例为什么值得学

这是 HyperFrames 团队自己做的发布视频——用 HyperFrames 做 HyperFrames 的发布片，等于官方教你「正确用法」。视频展示了框架几乎所有关键特性：

1. **多场景编排**：8+ 个场景无缝切换
2. **GSAP 复杂时间线**：嵌套 timeline、position 参数、stagger
3. **Shader 转场**：glitch、domain-warp-dissolve、light-leak 等
4. **动态排版**：大字标题 + 细字正文的强烈对比
5. **社交覆盖层集成**：片尾的 X/Twitter follow card
6. **媒体预处理**：TTS 旁白、BGM 配乐

## 场景拆解

### 场景 1：Hook（0-8s）
```
"Write HTML. Render video."
大字居中，纯黑背景。逐字 typewriter 效果出现。
```

**技巧**：
- 极简开场，一句话讲完产品价值——不废话
- 逐字出现用了 GSAP SplitText 或 stagger per-character
- 每个字间隔 ~0.03s，刚好让人能读完

**提取的 Prompt 模式**：
```
"开场用纯黑背景，居中大字 'Write HTML. Render video.'，
逐字出现，每个字间隔 0.03s，字体 Inter Black 72px 白色。
第一行出现完后 0.5s，第二行开始出现。"
```

### 场景 2：问题陈述（8-18s）
```
传统视频制作的痛点展示——Premiere、DaVinci、After Effects 的图标
被打叉划过，暗示旧工具的复杂。
```

**技巧**：
- 借代——不直接说"我们的产品好"，而是说"旧方式好痛苦"
- 图标 + 叉号比纯文字更有视觉冲击力
- stagger 动画让每个图标依次出现，最后 X 划过

**提取的 Prompt 模式**：
```
"展示 3 个传统视频工具的图标（PR、AE、达芬奇），
每个间隔 0.3s 依次从下方滑入，
然后一个红色 X 依次划过每个图标（0.2s 间隔），
最后停留在第三个图标上 0.5s。"
```

### 场景 3：解决方案（18-35s）
```
HyperFrames 的界面录屏 + 关键功能文字标注。
展示 init → preview → render 三步骤。
```

**技巧**：
- 三步骤用数字 1/2/3 标记，视觉引导清晰
- 每一步有对应的屏幕截图/GIF
- 转场用 cross-warp-morph，暗示「变革」

**提取的 Prompt 模式**：
```
"展示 3 个步骤，每步包含：大号数字（96px, opacity 0.1 作为背景）、
步骤标题（28px 白色）、对应的界面截图。
步骤之间用 cross-warp-morph 转场。
Step 1 (0-4s): 'npx hyperframes init' + 终端截图
Step 2 (4-8s): 'Write HTML' + 代码编辑器截图  
Step 3 (8-12s): 'npx hyperframes render' + 渲染进度截图
"
```

### 场景 4：社交验证（35-50s）
```
社区统计数据：GitHub Stars、下载量、贡献者数量。
数字滚动 + 柱状图脉冲。Bottom 叠加 X follow card。
```

**技巧**：
- 数据用 counter 动画（0 滚动到目标值）
- 多个数据点 stagger 出现
- 社交覆盖层不在片尾而在高潮时出现（聪明——利用观众情绪高点做 CTA）

**提取的 Prompt 模式**：
```
"Stagger 展示 3 个关键数据，每个包含：
大号数字（64px, 使用 GSAP counter 从 0 滚动）、
标签文字（18px, opacity 0.6）、
数字和标签依次入场，间隔 0.4s。
第一个数字出现后 1s，从底部滑入 X/Twitter follow 卡片。
"
```

### 场景 5：CTA 片尾（50-60s）
```
Logo + slogan + URL。
shimmer-sweep 扫过 Logo，grain-overlay 全程叠加。
最后 3 秒逐渐变暗。
```

**技巧**：
- 片尾就是 logo-outro block 的自定义版本
- shimmer-sweep 给 Logo 「高级感」
- 最后 3s 黑屏 + 微小 URL，让观众有时间截图

## 核心技巧提炼

### 1. 「一句讲完」开场法则
不要铺垫，第一句就告诉观众这个视频讲什么。

### 2. 问题→解决→验证 三段论
几乎所有优秀的产品视频都遵循这个节奏。

### 3. 转场不是装饰，是叙事工具
```
glitch → 暗示「颠覆/打破常规」
domain-warp-dissolve → 暗示「变革/转变」
light-leak → 暗示「灵感/新开始」
```
每个转场的选择都有叙事含义。

### 4. CTA 放在高潮，不是结尾
观众注意力曲线：开头高 → 中间低 → 结尾中等。CTA 应该放在注意力最高的时刻。

### 5. 最后 3 秒留给「截图」
永远在视频最后放 URL/联系方式，方便观众截图保存。

## 在你的模板中应用

```markdown
# 基于此案例的产品视频 Prompt 模板

## 视频名称：[产品名] 发布宣传片

## 场景时间线
| 场景 | 时间 | 内容 | 转场 |
|------|------|------|------|
| Hook | 0-6s | 一句讲完核心价值，逐字出现 | — |
| 痛点 | 6-14s | 旧方式的 3 个痛点，stagger + X 划过 | cross-warp-morph |
| 方案 | 14-28s | 3 步使用流程，数字标记 | 各步间 cross-warp-morph |
| 验证 | 28-38s | 3 个关键数据，counter 动画 + social overlay | glitch |
| 行动 | 38-45s | Logo + slogan + URL，shimmer sweep | light-leak |

## 关键技巧
- 全程 grain-overlay（opacity 0.2）
- 数字用 `gsap.to(el, { textContent: N, snap: { textContent: 1 } })` 做滚动
- CTA 的 x-post block 在数据高潮时触发，不等到片尾
```
