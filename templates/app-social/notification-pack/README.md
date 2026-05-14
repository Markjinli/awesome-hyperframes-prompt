# Notification Pack — 社交通知叠加层

> 模拟 macOS 通知、Spotify 播放卡片、Reddit 帖子、X 推文等原生平台 UI，叠加在视频上制造「真实平台」沉浸感。

## 效果

15-25 秒的品牌宣传视频。在动态背景上依次弹出不同平台的 UI 卡片——系统通知、音乐播放器、社交媒体帖子——每个卡片都有平台原生的动画和交互风格。适合社交媒体营销、SaaS 产品宣传、社区推广。

## 适用场景

- 社交媒体营销视频
- 产品"被推荐/分享"的场景还原
- 社区/Meme 营销
- App 功能展示（如 "分享到社交平台" 功能）

## Prompt 模板

````markdown
使用 HyperFrames 创建一段带社交平台通知叠加层的宣传视频。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：暗色背景 + 原生平台 UI 卡片

## 背景
- 渐变暗色底：#0D1117 → #161B22（GitHub 暗色模式感）
- 微弱的网格线或粒子漂浮
- 整体氛围："有人在讨论你的产品"

## 通知卡片序列

**卡片 1（0-5s）— macOS 通知**
- 右上角滑入一个 macOS 风格通知横幅
- App 图标：[你的产品 Logo]
- 标题："[产品名]"
- 内容："[一条简短的通知/提醒文案]"
- 入场动画：从右侧屏外 translateX(400px) → translateX(0)，back.out 缓动
- 3s 后自动向右滑出消失

**卡片 2（4-9s）— Spotify Now Playing**
- 左下角浮现 Spotify 风格播放卡片
- 专辑封面占位 → 替换为 [你的产品/品牌视觉]
- 曲目名："[产品相关的趣味曲名]"
- 艺术家："[你的品牌名]"
- 进度条从 0% → 100%（4s 内完成）
- 入场动画：scale(0.9) + opacity(0) → scale(1) + opacity(1)

**卡片 3（8-14s）— X（Twitter）Post Card**
- 中心偏上浮现一个 X/Twitter 帖子卡片
- 头像 + 用户名 + @handle + 时间戳
- 帖子内容："[用户推荐文案，如 'Just tried @YourProduct and it's insanely good 🔥']"
- 底部：💬 42 · 🔁 128 · ❤️ 1.2K · 📊 89K
- 入场动画：Y 轴从下方弹入，带微旋转（-2° → 0°）

**卡片 4（12-18s）— Reddit Post Card**
- 左侧滑入 Reddit 风格帖子
- r/[subreddit名称] · Posted by u/[username] · [time]h
- 标题："[产品相关的 Reddit 标题]"
- Upvote 计数器从 0 快速滚动到 [目标数字]
- 入场动画：从左侧 translateX(-300px) → 0

**卡片 5（16-20s）— 所有卡片聚拢 + CTA**
- 前 4 张卡片缩小成缩略图，排列在画面四周
- 中央出现产品 Logo + 主 CTA
- "[产品名] — [一句话价值]"
- 所有卡片微微浮动（ambient float animation）

## 转场
- 卡片之间用 hard cut（卡片自己就是视觉焦点，不需要额外转场）
- 卡片 4 → 卡片 5：用 Cross Warp Morph 将所有卡片吸入中心

## 音效设计
- 每张卡片出现时配对应的平台音效：
  - macOS 通知：系统通知音
  - Spotify：微弱的音乐片段
  - X 帖子：轻量的 swoosh
  - Reddit：upvote 音效

## 技术注意事项
- 每个卡片是独立的 div 块，使用绝对定位
- 卡片使用 CSS box-shadow 模拟平台原生深度
- 所有 GSAP timeline 注册到 window.__timelines
- 卡片叠加在统一的背景层之上
````

## 关键技巧

- **平台原生化**：模仿真实平台的圆角、阴影、字体、间距。越像真的，效果越好
- **时间交错**：卡片不是严格顺序，而是有重叠（卡片 1 未消失时卡片 2 已出现），制造「信息流」感
- **数量克制**：4-5 张卡片刚好。超过 6 张观众会累
- **CTA 收束**：最后所有卡片聚拢到中心 CTA，把分散的注意力回归到产品

## 需要安装的 Blocks

```bash
npx hyperframes add spotify-now-playing
npx hyperframes add reddit-post-card
npx hyperframes add x-post-card
npx hyperframes add macos-notification
```

## 自定义方法

1. 替换每个卡片中的文字内容（用户名、帖子内容、曲名等）
2. 替换头像/专辑封面为你的品牌素材
3. 调整卡片出现的时间点和顺序
4. 增加或减少卡片数量（4-6 张最佳）
5. 修改 CTA 文案和 URL
