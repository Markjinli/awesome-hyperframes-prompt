# Creative Intro — 电影感创意开场

## 视频名称
"Uncharted" — 创意工作室品牌开场

## 基本信息
- 时长：25s  |  分辨率：1920x1080  |  帧率：30fps
- 风格路线：Cinematic/Epic

## 视觉系统
- 配色：深黑 #0A0A0A → 暖金 #C9A96E → 烟雾白 #F0EDE8
- 字体：标题 Bebas Neue (400, letter-spacing: 8px) / 副标题 Cormorant Garamond (300 italic)
- 氛围关键词：神秘、宏大、有机、呼吸感、胶片质感
- 画面比例：2.35:1 宽银幕（上下黑边各 90px）

## 场景时间线

| 场景 | 时间 | 画面 | 动画 | 音频 |
|------|------|------|------|------|
| 1 | 0-5s | 全黑画面，中央一粒微光浮现，缓慢脉动，像远处篝火或星火 | 微光从 opacity 0 + blur(20px) 渐变为 opacity 0.8 + blur(0)，伴随极慢的 scale 脉动 0.95→1.05，循环 | 低频环境音渐入，远处风声 |
| 2 | 5-10s | 光粒扩散成光晕，照亮背景中隐约可见的有机纹理（岩石/树皮质感），画面中央出现第一个词："UNCHARTED"，大写，字距极宽 | 光晕 scale + fade，文字从 blur(30px) + opacity 0 过渡到清晰，持续 2s，ease: power3.out | 低频渐强，加入细微的弦乐泛音 |
| 3 | 10-16s | 文字淡出，光晕向右流动，在画面右侧 1/3 处凝聚，照亮一行小字 "CREATIVE STUDIO EST. 2026"，左侧留黑 | 光晕做 path 动画从左到右，文字 stagger 逐字母淡入（每个字母间隔 0.05s），整体持续 1s | 弦乐渐强，加入钢琴单音 |
| 4 | 16-21s | 光晕扩散到整个画面，之前隐约的纹理变得清晰——是有机流动的大理石纹理。画面中央大号工作室全称 "UNCHARTED STUDIOS" 以极慢速度浮现 | 文字从 scale(1.1) + opacity 0 过渡到 scale(1) + opacity 1，持续 2.5s，ease: power2.out。背景纹理做极缓慢的 drift 动画 | 音乐达到情感高点，加入铜管泛音 |
| 5 | 21-25s | 所有文字和光效一起缓慢淡出，画面回归全黑，只剩左上角一个极小的光点，闪烁 2 次后消失 | 全体元素 fade-out 1.5s，光点单独延迟 1s 后闪烁消失 | 音乐渐弱，最后一声钢琴泛音回荡 |

## 技术偏好
- Blocks：grain-overlay（全片叠加，透明度 0.25）、shimmer-sweep（场景 3 的光晕流动）
- 动画引擎：GSAP
- 转场：domain-warp-dissolve（场景 2→3）、light-leak（场景 4→5）
- 宽银幕比例：用 CSS padding-top/bottom 实现 2.35:1 letterbox

## 参考
- 风格参考：Terrence Malick 电影开场、《沙丘》标题序列、A24 工作室片头
- 节奏参考：Nolan 电影片头那种「屏息等待」的节奏感

## 自定义变量
- `{STUDIO_NAME}` = "UNCHARTED" → 改成你的品牌名
- `{TAGLINE}` = "CREATIVE STUDIO EST. 2026" → 改成你的标语
- `{FULL_NAME}` = "UNCHARTED STUDIOS" → 改成完整品牌名
- `{GRAIN_OPACITY}` = 0.25 → 调整胶片颗粒强度（0-1）
- 配色：把暖金 #C9A96E 改成你的品牌色
