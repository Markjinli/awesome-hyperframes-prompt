使用 HyperFrames 创建一段带 TTS 语音旁白的产品介绍视频。

## 基础参数
- 时长：35 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：现代极简、专业温暖

## TTS 语音设置
- 引擎：HyperFrames 内置 Kokoro TTS
- 音色：af_heart（温暖女声）
- 语速：1.0x
- 脚本：

```
[开场 0-5s]    "Introducing [产品名] — the [一句话定位]."
[问题 5-12s]   "You know how [痛点描述]? It's [痛点影响]."
[方案 12-20s]  "With [产品名], you can [核心功能]. Just [最简操作]."
[特性 20-28s]  "[特性1]. [特性2]. And [特性3]. All in one platform."
[CTA 28-35s]   "[产品名]. [一句话价值]. Available now at [URL]."
```

- 每句独立音频文件，句间停顿 0.5-1.0s

## Caption 字幕
- Corporate 风格：Inter SemiBold，64px，fade + slide-up
- 当前词高亮 #FFFFFF，已读词 #888888
- 底部居中，距底边 100px
- 每个词提前 50ms 显示

## 画面分镜

**场景 1（0-5s）— Logo 揭示**
- Logo blur(20px)→blur(0) + scale(0.9)→(1.0)，1.2s
- 暗色背景，Logo 下方光线扫过

**场景 2（5-12s）— 痛点可视化**
- 三个痛点图标从左侧依次滑入
- translateX(-40px)→0，stagger 0.3s

**场景 3（12-20s）— 产品界面演示**
- 产品 UI 卡片从下方升起
- 关键功能用彩色标注圈出

**场景 4（20-28s）— 三大特性**
- 三分栏：图标+特性名+描述
- 依次弹入，bounce 入场

**场景 5（28-35s）— CTA**
- 品牌色背景，产品名+价值主张居中
- URL 在下方，背景粒子动画

## 转场
- Light Leak 或 Push Slide，每个 0.6-0.8s

## 背景音乐
- Ambient electronic，VO 时 duck 到 20%，无 VO 时 60%

## 技术注意事项
- TTS 音频文件在 audio/ 目录
- 每个 VO 段落独立 <audio>，设置 data-start 和 data-track-index
- GSAP timeline 注册到 window.__timelines
- 字幕使用 per-word timing JSON 数据驱动
