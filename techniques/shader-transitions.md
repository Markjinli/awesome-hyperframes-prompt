# Shader Transitions — 深度指南

> HyperFrames 内置 14 种 WebGL Shader 转场。本指南教你何时用、怎么描述、如何与 AI agent 协作。

## 为什么用 Shader 转场

CSS 转场（fade/slide/push）够用，但 Shader 转场能做到 CSS 做不到的事：
- **像素级扭曲**：基于画面内容做变形，不是简单的平移/缩放
- **电影感**：模拟真实镜头光晕、胶片灼烧、热浪扭曲
- **品牌区分度**：观众一眼看出这不是 PPT 动画

## 14 种 Shader 转场速查

| 转场 | 能量 | 情绪 | 适合场景 | Prompt 关键词 |
|------|------|------|---------|-------------|
| **Cross Warp Morph** | 中 | 流动/有机 | 品牌故事、创意短片 | "cross-warp morph between scenes" |
| **Whip Pan** | 高 | 速度/动感 | 社交媒体、运动品牌 | "whip pan to next scene" |
| **Glitch** | 极高 | 数字/赛博 | 科技发布、大会预告 | "glitch transition between clips" |
| **Ridged Burn** | 高 | 灼烧/强度 | 产品发布、高潮段落 | "ridged burn to reveal next shot" |
| **Light Leak** | 低 | 温暖/怀旧 | 品牌故事、婚礼、旅行 | "cinematic light leak transition" |
| **Chromatic Radial Split** | 中 | 迷幻/艺术 | 音乐视频、艺术短片 | "chromatic split radial transition" |
| **Cinematic Zoom** | 中高 | 戏剧化 | 产品特写、关键揭示 | "dramatic zoom blur into scene" |
| **Domain Warp Dissolve** | 低 | 梦幻/漂浮 | 品牌 intro、情感段落 | "fractal noise dissolve" |
| **Flash Through White** | 中 | 干净/利落 | 场景切换、节奏点 | "flash to white transition" |
| **Gravitational Lens** | 中 | 空间/扭曲 | 3D 场景、科技感 | "gravitational lens warp" |
| **Ripple Waves** | 中 | 液态/有机 | 水相关、音乐、冥想 | "ripple wave distortion" |
| **SDF Iris** | 低中 | 优雅/复古 | 开场/结束、经典风格 | "iris reveal with SDF" |
| **Swirl Vortex** | 高 | 吸入/旋转 | 动态开场、动作段落 | "swirl vortex transition" |
| **Thermal Distortion** | 中 | 热浪/炙热 | 运动、速度感 | "heat haze thermal distortion" |

## 给 AI Agent 的描述公式

### 基础公式
```
Use [shader_name] transition between [scene_A] and [scene_B], 
with [duration] seconds, [quality_modifier].
```

### 示例

**Glitch 转场（科技发布）**
```
Between the product intro and spec reveal, use a 0.8s glitch transition.
Make it aggressive — RGB split + scanline artifacts — 
like a CRT monitor losing signal momentarily.
```

**Whip Pan 转场（运动品牌）**
```
Use a 0.4s whip pan right between each athlete clip.
Motion blur should feel like a fast camera pan on a gimbal.
Keep it tight — no easing, constant velocity.
```

**Light Leak 转场（品牌故事）**
```
Between the origin story scenes, use 1.2s light leak transitions.
Warm amber tones, soft bloom at the edges.
Should feel like old 16mm film gate — nostalgic, not dirty.
```

**Ridged Burn 转场（产品发布高潮）**
```
At the big reveal moment (24s mark), use a 1.5s ridged burn transition.
Turbulence should build from the center outward.
Colors go from normal → overexposed → normal as the next scene emerges.
```

**Cross Warp Morph（创意短片）**
```
Use cross-warp morph to transition between abstract shapes.
0.6-0.8s, with the previous shape's edges flowing into the next.
Keep it organic — no hard lines, everything should feel liquid.
```

## 转场组合策略

### 节奏型组合（社交媒体 / TikTok）
```
Hard cut → Hard cut → Whip Pan → Hard cut → Glitch → Hard cut

每 2-3s 一个变化，保持观众注意力
```

### 叙事型组合（品牌故事 / 纪录片）
```
Fade → Cross Warp Morph → Light Leak → Domain Warp Dissolve → Fade

低能量，让观众沉浸在内容中
```

### 高潮型组合（产品发布 / 发布会）
```
Hard cut → Push Slide → Cinematic Zoom → Ridged Burn → Flash Through White → Hard cut

能量逐渐累积，在关键揭示达到顶峰
```

## 技术要点

### 与 AI Agent 协作时的注意事项

1. **Shader 转场需要 `@hyperframes/shader-transitions` 包** — agent 通常会自动安装
2. **转场时长推荐**：0.4s（快节奏）到 1.5s（电影感），超过 2s 会让观众感到拖沓
3. **不要每个场景都用 shader** — 2-4 个关键转场 + 其余用 hard cut 或简单 CSS 转场是最佳比例
4. **转场方向**：whip pan 和 push slide 需要指定方向（left/right/up/down）
5. **音频配合**：转场点通常也是音频的重音点（beat drop、SFX hit）

### 常见错误

- ❌ "用 shader 转场连接所有场景" → 视觉疲劳
- ❌ "glitch 转场 3 秒" → 太长，观众会以为视频坏了
- ❌ "随便加个炫的转场" → agent 可能选不合适的，指定类型更可靠
- ✅ "在第 3、7、12 秒处分别用 glitch、cinematic zoom、cross warp morph"
