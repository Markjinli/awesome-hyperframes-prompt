使用 HyperFrames 创建一段开发者工具发布视频。

## 基础参数
- 时长：35 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：暗色代码编辑器美学 + 现代科技感
- 配色：#1E1E1E 背景 + 品牌强调色 [#00C3FF]

## 分镜

**Beat 1（0-6s）— Cold Open：安装命令**
- 全屏暗色终端，光标闪烁
- 打字机效果逐字输入：`$ npx [tool-name] init my-project`（35ms/字符）
- 回车后终端输出滚动（安装进度 → ✓ 完成）
- 音效：键盘打字声

**Beat 2（6-12s）— IDE 编辑**
- VS Code 风格编辑器布局
- 侧边栏文件树，编辑区打开 index.html
- 关键 data-* 属性代码行高亮
- 相机缓慢推进聚焦

**Beat 3（12-18s）— 实时预览**
- 编辑器左缩，右侧出现预览窗
- 预览窗展示产品核心效果
- 编辑区和预览窗之间连线指示

**Beat 4（18-24s）— Split Screen 代码 vs 输出**
- 左右分屏：左侧源码，右侧渲染画面
- 分隔线从左往右移动（画面扩大）
- 信息：Less code, more video

**Beat 5（24-30s）— Pipeline 流程图**
- 四节点从左到右：Agent → HTML → Renderer → MP4
- 各节点独立颜色，箭头依次绘制（stagger 0.3s）
- MP4 节点出现后下载图标弹出

**Beat 6（30-35s）— End Card**
- 节点收拢，产品名大面积显示
- Tagline + GitHub URL + install 命令
- 暗色背景 + 微弱代码雨

## 转场
- Beat 1→2：Flash Through White
- Beat 2→3：Push Slide
- Beat 3→4：分隔线自然滑动
- Beat 4→5：Domain Warp Dissolve
- Beat 5→6：Cross Warp Morph

## 字体
- 代码：JetBrains Mono
- UI 文字：Inter
- 标题：Inter Black

## 技术注意事项
- 代码语法高亮使用 CSS class（不用 JS 库）
- 打字机效果使用 GSAP text plugin
- IDE 布局使用 CSS Grid/Flexbox
- 终端光标使用 CSS animation（blinking）
- Pipeline 节点和箭头用 SVG，stroke-dashoffset 做绘制动画
- 所有 GSAP timeline 注册到 window.__timelines
