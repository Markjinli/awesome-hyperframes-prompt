# HyperFrames × AI Agent 协作工作流

## 核心理念

HyperFrames 是为 AI agent 设计的——框架假设你的主要协作对象是 AI，不是人类开发者。掌握正确的协作模式，效率提升 10 倍。

## 三阶段工作流

### 阶段 1：初始化（5 分钟）

```bash
# 用 AI agent 初始化项目
npx hyperframes init my-video
npx hyperframes skills add    # 给 agent 装上 HyperFrames 技能包
```

然后给 agent 看框架文档：

```
"请阅读 node_modules/hyperframes 下的 README 和 skills 文档，
了解 data-composition-id、data-start、data-duration、data-track-index 的用法。

可用的 blocks 列表在 blocks/ 目录下。

理解后回复 'Ready'。"
```

### 阶段 2：创作迭代（主要时间）

```
第 1 轮：生成骨架
"用 HyperFrames 创建一个 [描述] 的视频，先只做场景结构，
每个场景用纯色背景 + 标题文字即可，不用精细动画。"

第 2 轮：逐场景细化
"场景 1 现在只有标题，帮我加入：
- 背景渐变
- Logo 入场动画（GSAP，scale + fade）
- 副标题在标题后 0.5s 淡入"

第 3 轮：动画打磨
"把所有 fade-in 改成更有趣的入场方式：
- 标题用 scale-up + blur-out
- 卡片用 stagger 依次弹出
- CTA 按钮加 pulse 循环动画"

第 4 轮：转场
"场景之间的切换太平淡了，
场景 1→2 用 slide-left 推出
场景 2→3 用 scale-blur 转场
场景 3→4 用 mask circle reveal"

第 5 轮：音频和收尾
"添加音频轨道、微调时间线、检查 data-duration 总和是否等于目标时长"
```

### 阶段 3：渲染输出

```bash
npx hyperframes preview    # agent 可以帮你打开浏览器实时预览
npx hyperframes render     # 输出 MP4
```

## 多 Agent 协作模式

### 模式 A：导演 + 执行者

```
Agent 1（导演）：
"你负责整体视频结构和节奏把控，决定场景划分和过渡时机。
输出每一步的修改要求，交给 Agent 2 执行。"

Agent 2（执行者）：
"你负责根据导演的要求，修改 index.html 的具体代码。
专注于代码质量和动画实现。"
```

### 模式 B：场景并行开发

```
1. 先用一个 agent 做出场景骨架和时间线分配
2. 把 index.html 拆成多个片段
3. 用 3-5 个 agent 各自负责不同场景的细化和动画
4. 最后一个 agent 负责合并、调整转场、统一风格
```

### 模式 C：专家分工

```
Agent A（视觉设计）：负责配色、排版、构图
Agent B（动画专家）：负责 GSAP 动画、时间线编排
Agent C（音频专家）：负责 BGM 选择、音效标记、TTS 配置
Agent D（技术审核）：检查 data 属性正确性、性能、渲染兼容性
```

## 迭代指令模板

### 修改特定元素

```
"找到 data-id='hero-title' 的元素，
将它的入场动画从 fade-up 改为：
从 scale(0.8) + blur(10px) 过渡到 scale(1) + blur(0)，
持续时间 0.8s，ease: power3.out"
```

### 调整时间线

```
"将场景 2 的所有元素整体前移 0.5s，
场景 2 原本是 3s-10s，改成 2.5s-9.5s。
注意：不要影响场景 1 和场景 3 的时间。"
```

### 全局风格调整

```
"将所有场景的背景色暗度降低 10%（所有 #0A0A1A 改成 #1A1A2A），
所有卡片的圆角从 12px 改成 16px，
所有标题从 Inter 改成 Switzer（如果能用的话）。"
```

## 常见故障排查

| 问题 | 原因 | 对话指令 |
|------|------|---------|
| 视频渲染后动画不流畅 | 动画用了 wall-clock time 而非 seek | "请确保所有 GSAP 动画都注册了 __hf 适配器，支持确定性 seek" |
| 元素在错误的层级 | track-index 设置不对 | "背景应该用 track-index=0，前景内容用 track-index 往上递增" |
| 场景之间有空隙 | data-start + data-duration 没有无缝衔接 | "检查所有 data-start 和 data-duration，确保场景 X 结束时间 = 场景 X+1 开始时间" |
| 字体在渲染视频中不显示 | 用了系统未安装的字体 | "所有字体改用 Google Fonts CDN 或 @import，不要依赖系统字体" |
| 动画在最后一帧卡住 | GSAP timeline 没有正常结束 | "在所有 timeline 末尾加 .time(99999) 确保超出视频时长" |

## 版本管理

### .gitignore 推荐

```gitignore
node_modules/
output/
*.mp4
.hyperframes/
```

### Commit 习惯

```bash
# 每次成功的场景迭代后 commit
git add index.html && git commit -m "Scene 1: logo animation done"
git add index.html && git commit -m "Scene 2-3: feature cards + transitions"
git add index.html && git commit -m "Global: unified color scheme, polish animations"
```

这让你在 AI 改坏时可以 `git checkout index.html` 回退到上一个好版本。

## 从 Figma/设计稿到 HyperFrames

如果你有 Figma 设计稿：

```
"我会上传设计稿的截图。请分析：
1. 配色方案（提取所有 hex 值）
2. 字体系统（识别字体、字号、粗细）
3. 布局结构（元素位置、间距、对齐方式）
4. 然后把这些转化为 HyperFrames HTML + CSS

[上传 Figma 截图]"
```

## 从参考视频到 HyperFrames

```
"参考这个视频的第 5-15 秒：[链接或描述]
我需要类似的效果，但不是复制它。
具体提取：
- 节奏感：文字每隔 1.5s 切换一次
- 转场风格：快速的缩放模糊转场
- 配色：暗色背景 + 霓虹强调色
用这些元素做一个我们自己的版本。"
```

## 效率技巧汇总

1. **先骨架后血脉**：先让 AI 搭场景 + 纯色背景，确认时间线合理后再加动画
2. **每次只改一个维度**：一轮只改配色，一轮只改动画，一轮只改文字——避免 AI 一次改太多出错
3. **保留满意的片段**：把好场景的 HTML 片段存到 `snippets/` 目录，以后复用
4. **用 git diff 审阅**：AI 改完代码后，`git diff` 看具体改了什么，比重新读整个文件快
5. **设定 AI 的"人设"**："你现在是一位世界级的动态图形设计师，擅长 Apple 风格的极简动画..."——这会影响代码质量的审美
