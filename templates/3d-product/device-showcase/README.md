# 3D Device Showcase — 3D 产品设备展示

> 使用 GLTF 3D 模型 + 360° 旋转展示产品设备，HTML 内容实时渲染到设备屏幕上。

## 效果

20 秒的 3D 产品展示视频。iPhone/MacBook/设备 3D 模型在画面中缓慢旋转（360° turntable），设备屏幕上实时渲染 HTML 内容（App UI、数据面板、网页）。适合硬件产品发布、App Store 预览、SaaS 产品宣传。

## 适用场景

- 硬件产品发布视频
- App Store / Google Play 预览视频
- SaaS 产品官网 Hero
- 设计作品集展示

## Prompt 模板

````markdown
使用 HyperFrames 帮我创建一段 3D 设备产品展示视频。

## 基础参数
- 时长：20 秒
- 分辨率：1920x1080
- 帧率：30fps
- 风格：Apple 产品页风格 — 干净、高光、玻璃反射

## 3D 场景设置
- 使用 Three.js + GLTF 模型
- 设备模型：[iPhone 15 Pro / MacBook Pro / 自定义设备]
- 放置在干净的渐变背景前（#0A0A0A → #1A1A2E）
- 设备材质：真实的玻璃/金属 PBR 材质
- 灯光设置：
  - Key Light：右上方 45°，暖白 #FFFAF0，强度 2.5
  - Fill Light：左下方，冷白 #E0E7FF，强度 0.8
  - Rim Light：背后上方，纯白，强度 1.5，勾出设备轮廓
  - 可选：微弱的点光源缓慢环绕，产生移动的高光反射

## 屏幕内容（HTML-in-Canvas）
设备屏幕上实时渲染 HTML 内容，使用 canvas-draw-element：

**阶段 1（0-8s）— App UI 展示**
- 在设备屏幕上显示 [你的 App/产品 界面]
- 包括：导航栏、主内容区、交互元素
- 配色：[品牌色 #XXXXXX] + 白色背景
- 屏幕内容有微弱的视差滚动效果

**阶段 2（8-16s）— 数据/功能切换**
- 屏幕内容切换到第二个界面：[数据面板/功能页]
- 过渡动画：屏幕内容做一个 micro-interaction（如卡片翻转或页面滑动）
- 关键数据点用彩色标注

**阶段 3（16-20s）— Logo 定格**
- 屏幕内容淡出，显示 [品牌 Logo]
- 设备继续缓慢旋转到最后角度
- 周围出现微弱的镜面高光扫过

## 相机动画
- 0-3s：设备从右侧旋转进入画面（Y 轴旋转：-45° → 0°）
- 3-12s：360° 缓慢旋转展示（Y 轴完整旋转一圈）
- 12-17s：相机缓慢推进（z: 5 → z: 3.5，特写屏幕内容）
- 17-20s：相机拉远到最终构图位置（z: 3.5 → z: 4.5）

## 场景底部的信息条
- 0-20s：底部居中显示产品名称和一句话描述
- 字体：SF Pro Display / Inter，字号 36px
- 颜色：#FFFFFF 80% opacity
- 入场：fade + slide-up（1.0s delay 后出现）

## 技术注意事项
- 使用 @hyperframes/shader-transitions 的场景切换
- GLTF 模型使用 useGLTF hook 加载
- 屏幕内容使用 html-in-canvas 技术
- 所有 GSAP timeline 注册到 window.__timelines
- Three.js 时间驱动注册到 window.__hfThreeTime
````

## 关键技巧

- **灯光是 3D 的灵魂**：不要只打一个环境光。Key + Fill + Rim 三灯组合 + 缓慢移动的点光源产生「摄影棚」质感
- **屏幕内容是焦点**：设备旋转到 45-60° 时屏幕最可见，在这个角度停留最久
- **反射制造真实感**：设备金属边框的高光移动暗示「这是个真实物体」
- **别过度旋转**：一圈 360°（12s）= 30°/s，刚刚好。更快会晕，更慢显拖沓

## 需要安装的 Blocks

```bash
npx hyperframes add vfx-iphone-device
```

## 自定义方法

1. 替换设备模型路径为你的 GLTF 文件
2. 替换屏幕上的 HTML 内容为你的产品界面
3. 修改配色中的品牌色
4. 调整相机动画的时间点和角度
5. 修改底部信息条的文字
