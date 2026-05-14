# Dev Tool Launch — 开发者工具发布视频

> 展示代码输入 → 视频输出的完整管线。模拟 IDE 界面、终端命令、代码高亮、产品生成的流程可视化。参考 HyperFrames 官方 launch 视频的手法。

## 效果

30-40 秒的开发者工具发布视频。从 IDE/终端界面开始，展示安装命令、代码编写、预览渲染、最终输出的完整工作流。全片保持暗色代码编辑器美学，配合打字机效果、语法高亮、终端光标。

## 适用场景

- 开源项目发布/重大版本更新
- CLI 工具 / SDK / API 产品介绍
- DevTool 众筹/Kickstarter 视频
- 技术博客视频版

## Prompt 模板

````markdown
使用 HyperFrames 创建一段开发者工具发布视频。

## 基础参数
- 时长：35 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：暗色代码编辑器美学 + 现代科技感
- 配色：代码编辑器暗色主题（#1E1E1E 背景）+ 品牌强调色 [#00C3FF]

## 分镜

**Beat 1（0-6s）— Cold Open：安装命令**
- 全屏暗色终端背景
- 一个光标独自闪烁
- 打字机效果逐字出现安装命令：
  ```
  $ npx [tool-name] init my-project
  ```
- 每个字符间隔 35ms
- 命令输入完成后，光标闪烁 2 次
- 终端输出开始滚动（安装进度条、依赖下载、✓ 完成）
- 音效：键盘打字声 + 微弱的终端提示音

**Beat 2（6-12s）— IDE 编辑**
- 画面切换到代码编辑器布局（类似 VS Code 暗色主题）
- 侧边栏：文件树，包含 index.html / styles.css / meta.json
- 编辑区：打开 index.html，展示 HyperFrames 的 HTML 结构
- 关键代码行高亮（data-start / data-duration / GSAP timeline）
- 相机缓慢推进（缩放效果），聚焦在关键属性上
- 音效：轻量的 UI 点击声

**Beat 3（12-18s）— Preview 实时预览**
- 编辑器向右缩小，左侧出现预览窗口
- 预览窗口中：HTML 渲染效果实时可见
- 预览窗口内展示 [你的产品的核心效果]
- 编辑区和预览窗之间有微弱的连线/箭头指示
- 音效：微弱的 swoosh 过渡

**Beat 4（18-24s）— Split Screen：Code vs Output**
- 左右分屏对比
- 左侧：简洁的 HTML 源码（高亮 data-* 属性）
- 右侧：对应的渲染画面
- 中间分隔线缓缓向右移动（画面扩大，代码缩小）
- 传递信息：Less code, more video
- 音效：分隔线移动时的机械滑动声

**Beat 5（24-30s）— Pipeline 流程图**
- 四节点流程从左到右绘制：
  Agent → HTML → Renderer → MP4
- 每个节点一个独立颜色：
  - Agent：#FF6B6B（珊瑚红）
  - HTML：#4ECDC4（青绿）
  - Renderer：#FFE66D（金黄）
  - MP4：#A78BFA（紫）
- 节点间箭头连线依次绘制（stagger 0.3s）
- 每个节点出现时轻微的 scale bounce
- MP4 节点出现后，一个下载图标弹出
- 音效：每节点出现时的上升音阶

**Beat 6（30-35s）— End Card**
- 所有节点收拢到画面中心
- 产品名 "[Tool Name]" 大面积显示
- 下方：Tagline + GitHub URL + install 命令
- 背景保持暗色，微弱的粒子或代码雨
- 音效：最后和弦 + 消散

## 转场
- Beat 1→2：Flash Through White（终端闪白进入 IDE）
- Beat 2→3：Push Slide（编辑器推左，预览从右入）
- Beat 3→4：无转场，分隔线自然滑动
- Beat 4→5：Domain Warp Dissolve（代码溶解成流程图）
- Beat 5→6：Cross Warp Morph（节点融合到 Logo）

## 字体
- 代码：JetBrains Mono（代码编辑器标准）
- UI 文字：Inter（干净无衬线）
- Logo/标题：Inter Black

## 技术注意事项
- 代码语法高亮使用 CSS 类（不要用 JS 库）
- 打字机效果使用 GSAP text plugin 或逐字 span 动画
- 所有 GSAP timeline 注册到 window.__timelines
- IDE 布局使用 CSS Grid 或 Flexbox
- 终端光标：CSS animation（blinking）
````

## 关键技巧

- **打字机节奏**：35ms/字符是代码演示的甜点。25ms 太快看不清，50ms 太慢显拖沓
- **代码高亮用 CSS**：不要引入 highlight.js 等 JS 库。用 span class + CSS color 手动高亮，性能更好
- **Split Screen 的方向感**：分隔线从左往右移 = "代码更少，画面更多"，有叙事方向
- **Pipeline 图用 SVG 画**：节点+箭头用 SVG path，配合 stroke-dashoffset 做绘制动画
- **End Card 的命令行**：最后出现的安装命令是最重要的 CTA，字体要大（48px+），颜色要突出

## 自定义方法

1. 替换 `[tool-name]` 为你的工具/项目名
2. 替换安装命令为你的实际命令
3. 替换代码示例为你的实际用法
4. 修改配色为你的品牌色
5. 调整 Beat 时长以匹配你的内容量

## 灵感来源

参考 HyperFrames 官方 `hyperframes-launch` 和 `website-to-hyperframes` 两个官方 launch 视频的叙事结构。
