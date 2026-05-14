# TTS Product Intro — AI 语音产品介绍

> 使用 TTS 生成自然语音旁白 + 同步字幕 + 画面内容的完整产品介绍视频。无需真人录音，全程 AI 驱动。

## 效果

30-45 秒的产品介绍视频。AI 生成的语音旁白（TTS）贯穿全片，字幕逐词高亮同步，画面配合旁白节奏展示产品界面、关键数据、品牌信息。适合需要频繁迭代的产品宣传、SaaS 产品介绍、功能演示。

## 适用场景

- SaaS/科技产品介绍视频
- 新功能发布公告
- 众筹/Kickstarter 视频
- API/SDK 开发者工具介绍

## Prompt 模板

````markdown
使用 HyperFrames 创建一段带 TTS 语音旁白的产品介绍视频。

## 基础参数
- 时长：35 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：现代极简、专业温暖

## TTS 语音设置
- 引擎：HyperFrames 内置 Kokoro TTS
- 音色：af_heart（温暖女声，适合产品宣传）
- 语速：1.0x（正常）
- 脚本：

```
[开场 0-5s]    "Introducing [产品名] — the [一句话定位]."
[问题 5-12s]   "You know how [痛点描述]? It's [痛点影响]."
[方案 12-20s]  "With [产品名], you can [核心功能]. Just [最简操作]."
[特性 20-28s]  "[特性1]. [特性2]. And [特性3]. All in one platform."
[CTA 28-35s]   "[产品名]. [一句话价值]. Available now at [URL]."
```

- 生成方式：按每句生成独立音频文件，便于在时间线上精确定位
- 句间停顿：0.5-1.0s（给画面呼吸空间）

## Caption 字幕
- 风格：Corporate — 干净无衬线，fade + slide-up
- 字体：Inter SemiBold，字号 64px
- 当前词高亮（#FFFFFF），已朗读词变暗（#888888）
- 位置：底部居中，距底边 100px
- Per-word timing：每个词在朗读前 50ms 出现（宁可早不可晚）

## 画面分镜

**场景 1（0-5s）— 产品 Logo 揭示**
- 暗色背景 → Logo 从中心放大浮现
- 配合 VO："Introducing [产品名]"
- 动画：blur(20px) → blur(0) + scale(0.9) → scale(1.0)，1.2s
- Logo 下方渐变光线扫过

**场景 2（5-12s）— 痛点可视化**
- 背景切换为灰蓝调
- 三个痛点图标/文字从左侧依次滑入
- 配合 VO："You know how...?"
- 动画：translateX(-40px) → translateX(0)，stagger 0.3s

**场景 3（12-20s）— 产品界面演示**
- 切换到产品 UI 截图或录屏
- 界面以卡片形式从下方升起
- 关键按钮/功能用彩色标注圈出
- 配合 VO："With [产品名], you can..."

**场景 4（20-28s）— 三大特性**
- 三分栏布局
- 每栏：图标 + 特性名 + 简短描述
- 依次从下方弹入（bounce 入场）
- 配合 VO：逐一介绍特性

**场景 5（28-35s）— CTA**
- 全屏品牌色背景
- 产品名 + 一句话价值主张居中
- URL 在下方
- 微弱的背景粒子动画
- 配合 VO："Available now at..."

## 转场
- 场景间使用 Light Leak（温暖感）或 Push Slide（专业感）
- 每个转场 0.6-0.8s

## 背景音乐
- 轻量 ambient electronic 铺底
- 在 VO 段落降低到 20% volume（ducking）
- 场景 5 CTA 时音量回升到 60%

## 技术注意事项
- TTS 音频文件放在 audio/ 目录
- 每个 VO 段落使用独立的 <audio> 元素，设置 data-start 和 data-track-index
- 所有 GSAP timeline 注册到 window.__timelines
- 字幕使用 per-word timing 数据驱动（JSON 格式）
````

## 关键技巧

- **VO 先行**：先确定 TTS 的节奏，再根据节奏设计画面。而不是先做画面再往里面塞语音
- **Ducking 是细节**：VO 说话时 BGM 降到 20%，不说话时回到 60%。不做的后果是语音和音乐打架
- **字幕宁可早不可晚**：每个词提前 50ms 出现。晚于语音的字幕比没有字幕更让人分心
- **句间留白**：0.5-1.0s 的句间停顿不是浪费，是给观众消化信息的时间

## 自定义方法

1. 修改 TTS 音色（af_heart / am_adam / af_nova 等）
2. 替换脚本中的 `[占位内容]` 为你的产品信息
3. 替换产品 UI 截图路径
4. 调整场景时长以匹配你的 VO 节奏
5. 修改品牌色和字体
