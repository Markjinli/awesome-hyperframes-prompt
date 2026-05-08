# 案例拆解：Vibe Video — 自然语言到 HyperFrames 视频

## 基本信息

- **案例来源**：[agno-agi/vibe-video](https://github.com/agno-agi/vibe-video)（84 stars, Python）
- **视频类型**：自动化视频生产流水线
- **核心理念**：Research → Script → HyperFrames HTML → MP4

## 为什么值得学

这是社区中最成熟的「自然语言 → 完整视频」管线。它证明了 HyperFrames 不只是做宣传片，还可以做**信息密度型内容**——教程、代码讲解、论文解读。

## Workflow 拆解

```
User Prompt ("Explain React Server Components")
    ↓
1. Research Agent — 搜索资料、阅读文档、提取关键点
    ↓
2. Script Generator — 将关键点转化为视频脚本（场景 + 文案 + 视觉描述）
    ↓
3. HyperFrames Generator — 将脚本转化为 index.html
    ↓
4. Render — npx hyperframes render → MP4
```

## 关键设计决策

### 1. 分阶段生成（不一次性生成整个 HTML）
```
Stage 1: 只生成场景结构（骨架 HTML）
Stage 2: 逐步填充每个场景的内容
Stage 3: 统一添加转场和动画
```

**为什么更好**：一次性生成整个 HTML 容易出错，分阶段让每一步都可以review和修正。

### 2. Prompt 中用了结构化约束
```python
# Vibe Video 给 AI 的约束模板
SYSTEM_PROMPT = """
You are a HyperFrames video composition expert.
- Always use semantic data attributes
- Each scene must have data-duration matching its content
- Use GSAP for animations, register via window.__hf_gsap
- Fonts must be from Google Fonts CDN
- Colors must use hex values, not CSS variables
"""
```

### 3. 场景模板化
Vibe Video 预设了 5 种场景类型：

| 场景类型 | 用途 | 默认时长 |
|---------|------|---------|
| `title-card` | 标题/片头 | 3s |
| `content-section` | 主体内容 | 8-15s |
| `code-block` | 代码展示 | 6-10s |
| `diagram` | 图表/架构图 | 8-12s |
| `outro` | 片尾/CTA | 4s |

## 提取的 Prompt 技巧

### 针对「教育/讲解类」视频的专用 Prompt

```markdown
# 视频名称：[Topic] 讲解视频

## 基本信息
- 时长：根据内容自动计算  |  分辨率：1920x1080

## 内容结构
1. 片头 (3s)：标题 "[Topic] Explained"
2. 概念引入 (5s)：为什么需要了解这个？
3. 核心讲解 (10-15s)：3 个关键概念，每个一个场景
4. 代码/实例 (8s)：实际用法展示
5. 总结 + CTA (4s)

## 视觉约束
- 代码块：深色背景 #1E1E1E，JetBrains Mono 14px，语法高亮
- 概念卡片：浅色卡片 + 图标 + 一句话
- 图表：SVG 手绘风或 clean blueprint 风
- 字体：Inter（标题）+ JetBrains Mono（代码）

## 特殊指令
- 每个概念场景包含一个 icon + 标题 + 一句话解释（不超过 15 词）
- 代码块带行号
- 场景间用 light-leak 转场（教育感 > 科技感）
```

## Vibe Video 的局限性（如何在你的模板中改进）

| Vibe Video 的局限 | 改进方向 |
|-------------------|---------|
| 只支持横屏 1920x1080 | 增加竖屏 1080x1920 选项 |
| 转场单一 | 根据内容类型自动选转场（代码→glitch，概念→domain-warp） |
| 没有音频处理 | 集成 TTS（HyperFrames 的 hyperframes-media skill） |
| 输出只有 MP4 | 增加 GIF 预览、关键帧图片 |

## 实践建议

如果你要做类似的教育内容批量生产：
1. 先手动做 3 个高质量模板（不同风格），AI 模仿比从零生成好得多
2. 做一个「风格库」（brand guide 式的约束文件），每次复用
3. 用 git 管理每次生成的 HTML，好版本可以回滚
