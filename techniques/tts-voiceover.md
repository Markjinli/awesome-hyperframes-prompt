# TTS + Voiceover 工作流 — 深度指南

> HyperFrames 内置本地 TTS 引擎（Kokoro），无需 API key。支持多语言、多音色、语速调节。本指南覆盖从脚本到成品的完整流程。

## 为什么用 TTS 而不是真人录音

| 维度 | TTS | 真人录音 |
|------|-----|---------|
| 迭代速度 | 改脚本 → 重新生成（秒级） | 重新录制（小时/天） |
| 一致性 | 音色、语速、情感完全可控 | 受状态、环境、设备影响 |
| 多语言 | 一键切换 | 需要多语种配音演员 |
| 成本 | 免费（本地运行） | 按小时或项目计费 |
| 自然度 | 85-90%（现代 TTS） | 100%（天然优势） |

**结论**：原型/迭代用 TTS，最终交付看预算和场景决定。

## 可用音色

| 音色 ID | 性别 | 风格 | 最适合 |
|---------|------|------|--------|
| `af_heart` | 女声 | 温暖、有感染力 | 品牌故事、产品宣传 |
| `af_nova` | 女声 | 清晰、专业 | 企业宣传、教程 |
| `af_sky` | 女声 | 轻快、有活力 | 社交媒体、营销 |
| `am_adam` | 男声 | 沉稳、可信 | 教程、纪录片 |
| `am_michael` | 男声 | 权威、有力度 | 企业宣传、发布会 |

## 脚本写作原则

### 字数 → 时长换算
```
英语：~150 词/分钟（正常语速），~180 词/分钟（较快）
中文：~200 字/分钟（正常语速），~250 字/分钟（较快）

30 秒视频 ≈ 70-75 英文词 ≈ 100 中文词
60 秒视频 ≈ 140-150 英文词 ≈ 200 中文词
```

### 脚本结构模板

```
[开场 Hook]     — 5-8 词，1 句话，抓注意力
[问题陈述]     — 15-20 词，提出痛点
[解决方案]     — 20-25 词，介绍产品/方法
[关键特性]     — 30-40 词，2-3 个要点
[社会证明]     — 15-20 词，数据/引用
[CTA 行动号召]  — 8-12 词，告诉观众下一步
```

### 写出适合朗读的句子

✅ 好的 VO 脚本：
```
"Imagine you could turn any website into a video. 
Not a screen recording. A real, produced video. 
With motion graphics. Typography. Transitions.
That's HyperFrames."
```

❌ 不适合朗读：
```
"HyperFrames is a comprehensive open-source framework 
that leverages HTML-based composition to facilitate 
the programmatic generation of video content."
```
→ 太长、太密、太多术语。VO 需要短句和呼吸空间。

### Apple 风格节奏

Apple 发布会 VO 的特点：
- 每句 6-12 个词，不超过一行
- 句间停顿 0.5-1.0s（给画面呼吸空间）
- 关键揭示前停顿 1.5-2.0s（build expectation）
- 短句为主，偶尔用长句做变化

```
"Open source."          [pause 0.8s]
"HTML in."              [pause 0.5s]
"Video out."            [pause 1.2s — let it land]
"Anything a browser can render..." [pause 0.3s]
"...can be a frame in your video." [pause 1.0s]
```

## 给 AI Agent 的 TTS Prompt

### 基础生成
```
Generate TTS narration for this script:

"HyperFrames turns HTML into video. 
Write your composition, hit render, and you get an MP4. 
It's open source. It's deterministic. And it's ready for your next project."

Voice: af_heart (warm female)
Speed: 1.0x
Format: Generate one audio file per sentence for precise timeline placement.
```

### 带情感的生成
```
Generate TTS with emotional direction:

[calm, thoughtful] "Imagine you could make videos like this."
[pause 1.5s]
[building excitement] "Your agent already can."
[pause 0.5s]
[confident, direct] "Just give it HyperFrames."

Voice: am_michael
Speed: 0.95x (slightly slower for gravitas)
Add subtle emphasis on "already" and "HyperFrames."
```

### 多音色对话
```
Create a two-voice conversation:

Host (af_nova, 1.0x): "So what exactly does HyperFrames do?"
Expert (am_adam, 0.95x): "It lets you write video like you write code."
Host (af_nova, 1.0x): "HTML becomes MP4?"
Expert (am_adam, 0.95x): "Exactly. Every frame, deterministically rendered."

Each line as a separate audio file with voice label in filename.
```

## 工作流

### 标准流程
```
1. 写脚本 → 2. 用 TTS 生成 VO → 3. 导入 HyperFrames 时间线
       ↓
4. 根据 VO 节奏做画面 → 5. 微调时序 → 6. 渲染
```

### 具体命令
```bash
# 生成 TTS 音频
npx hyperframes tts --text "Your script here" --voice af_heart --output vo/

# 在 HTML 中引用
# <audio id="narration" data-start="0" data-track-index="0" src="vo/narration.wav"></audio>

# 预览（带音频）
npx hyperframes preview

# 调试时序
npx hyperframes inspect  # 查看时间线
```

### 迭代工作流
```
1. 生成初版 TTS
2. 在浏览器中预览（npx hyperframes preview）
3. 发现某句太快/太慢 → 改脚本 → 重新生成那一句
4. 发现某句和画面不同步 → 调整 data-start 偏移
5. 重复 2-4 直到满意
```

## Caption + VO 同步

TTS 生成后，需要让字幕和语音同步：

```
Prompt: "Generate captions synced to the TTS audio.
Each word should appear exactly as it's spoken.
Use per-word timing from the transcript.
Late words are worse than early words — when in doubt, show the word 50ms early."

Style: tutorial/corporate
Caption position: bottom center, max 2 lines
Current word: brighter/highlighted
Spoken words: dimmed slightly
Upcoming words: not yet visible (clean reveal)
```

## 常见问题

| 问题 | 原因 | 解决 |
|------|------|------|
| VO 和画面不同步 | 时间线偏移 | 检查 `data-start`，给 VO 加 -0.1s 偏移 |
| TTS 发音错误 | 生僻词/缩写 | 在脚本中写音译，如 "GSAP → G-Sap" |
| 语速不合适 | 默认 1.0x 不适合内容 | 营销: 1.1x / 教程: 0.95x / 品牌: 0.9x |
| 情感太机械 | TTS 默认平淡 | 在脚本中加方向词 [excited], [calm] |
| 文件太大 | WAV 未压缩 | 用 `--format mp3` 或 `--quality medium` |
