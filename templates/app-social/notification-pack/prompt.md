使用 HyperFrames 创建一段带社交平台通知叠加层的宣传视频。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：暗色背景 + 原生平台 UI 卡片

## 背景
- 渐变暗色底：#0D1117 → #161B22
- 微弱网格线漂浮
- 整体氛围：信息流/社区讨论感

## 通知卡片序列

**卡片 1（0-5s）— macOS 通知**
- 右上角滑入 macOS 风格通知横幅
- App 图标：[产品 Logo]，标题："[产品名]"，内容："[通知文案]"
- 入场：translateX(400px)→0，back.out
- 3s 后右滑消失

**卡片 2（4-9s）— Spotify Now Playing**
- 左下角浮现 Spotify 播放卡片
- 专辑封面：[品牌视觉]，曲目："[趣味曲名]"，艺术家："[品牌名]"
- 进度条 0%→100% 在 4s 内
- 入场：scale(0.9) + opacity(0) → scale(1) + opacity(1)

**卡片 3（8-14s）— X（Twitter）Post Card**
- 中心偏上浮现帖子卡片
- 帖子内容："[用户推荐文案]"
- 底部互动数据
- 入场：Y 轴弹入，微旋转 -2°→0°

**卡片 4（12-18s）— Reddit Post Card**
- 左侧滑入 Reddit 帖子
- 标题："[Reddit 风格标题]"
- Upvote 计数器从 0 快速滚动到 [目标数字]
- 入场：translateX(-300px)→0

**卡片 5（16-20s）— 收束 + CTA**
- 所有卡片缩小排列四周
- 中央：[产品名] — [一句话价值]
- 卡片微微浮动

## 转场
- 卡片间用 hard cut
- 卡片 4→5：Cross Warp Morph 吸入中心

## 音效
- 每张卡片配对应平台音效

## 技术注意事项
- 卡片独立 div + 绝对定位
- CSS box-shadow 模拟平台深度
- GSAP timeline 注册到 window.__timelines
