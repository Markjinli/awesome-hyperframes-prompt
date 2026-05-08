# HyperFrames 动画模式指南

## 动画引擎选型

HyperFrames 通过 Frame Adapter 模式支持多种动画引擎。选对引擎是第一位的：

| 引擎 | 适合场景 | 优势 | 劣势 |
|------|---------|------|------|
| **GSAP** | 复杂时序、滚动驱动、路径动画 | 功能最全，社区资源丰富 | 需要额外学习，体积较大 |
| **CSS Animations** | 简单入场、循环动画 | 零依赖，浏览器原生 | 复杂编排困难 |
| **Anime.js** | 轻量级 SVG 动画 | 体积小，API 简洁 | 生态较小 |
| **Lottie** | 设计师交付的 AE 动画 | 设计还原度高 | 文件体积大 |
| **Web Animations API** | 现代浏览器原生支持 | 性能好，JS 可控 | 浏览器兼容性差 |
| **Three.js** | 3D 场景、WebGL 效果 | 3D 表现力强 | 学习曲线陡峭 |

## 核心模式目录

### 1. 入场动画模式

#### Fade & Slide（最常用）

```css
/* CSS 版本 */
.clip {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeSlideUp 0.6s ease-out forwards;
}
@keyframes fadeSlideUp {
  to { opacity: 1; transform: translateY(0); }
}
```

```javascript
// GSAP 版本（推荐用于复杂编排）
gsap.fromTo('.clip', 
  { opacity: 0, y: 30 },
  { opacity: 1, y: 0, duration: 0.6, ease: 'power2.out' }
);
```

**适用**：标题、正文段落、卡片元素（90% 的场景用这个就够了）

#### Scale Reveal（强调型）

```javascript
gsap.fromTo('.hero-title', 
  { opacity: 0, scale: 0.8 },
  { opacity: 1, scale: 1, duration: 0.8, ease: 'back.out(1.7)' }
);
```

**适用**：Logo、核心数据、CTA 按钮

#### Stagger Entrance（列表/网格）

```javascript
// 每个元素依次入场，间隔 0.1s
gsap.fromTo('.feature-card', 
  { opacity: 0, y: 40 },
  { 
    opacity: 1, y: 0, 
    duration: 0.5, 
    stagger: 0.1,
    ease: 'power2.out'
  }
);
```

**适用**：功能列表、团队介绍、产品网格

#### Typewriter（逐字出现）

```javascript
// 用 GSAP SplitText 或手动分割
const chars = document.querySelectorAll('.typewriter .char');
gsap.fromTo(chars, 
  { opacity: 0 },
  { opacity: 1, duration: 0.02, stagger: 0.03 }
);
```

**适用**：片头标语、关键信息强调

### 2. 转场模式

#### Crossfade

```css
.composition-out {
  animation: crossfadeOut 0.5s ease-in forwards;
}
.composition-in {
  opacity: 0;
  animation: crossfadeIn 0.5s ease-out 0.3s forwards;
}
@keyframes crossfadeOut { to { opacity: 0; } }
@keyframes crossfadeIn { to { opacity: 1; } }
```

**适用**：场景间平滑过渡（最安全的选择）

#### Slide Push

```javascript
// 旧场景向左推出，新场景从右滑入
gsap.to('.scene-current', { x: '-100%', duration: 0.5, ease: 'power2.inOut' });
gsap.fromTo('.scene-next', 
  { x: '100%' },
  { x: '0%', duration: 0.5, ease: 'power2.inOut' }
);
```

**适用**：步骤演示、时间线推进

#### Scale & Blur（高级转场）

```javascript
// 旧场景缩小 + 模糊，新场景从中心放大
gsap.to('.scene-current', { 
  scale: 0.9, filter: 'blur(20px)', opacity: 0,
  duration: 0.6, ease: 'power2.in' 
});
gsap.fromTo('.scene-next',
  { scale: 0.8, filter: 'blur(10px)', opacity: 0 },
  { scale: 1, filter: 'blur(0px)', opacity: 1, duration: 0.6, ease: 'power2.out' }
);
```

**适用**：品牌升级、前后对比、概念跳跃

#### Mask Reveal（创意转场）

```javascript
// 用 clip-path 或 mask 做形状转场
gsap.fromTo('.scene-next', 
  { clipPath: 'circle(0% at 50% 50%)' },
  { clipPath: 'circle(100% at 50% 50%)', duration: 0.8, ease: 'power2.inOut' }
);
```

**适用**：创意短片、艺术风格视频

### 3. 持续动画模式

#### Float/Drift（微动效）

```javascript
gsap.to('.floating-element', {
  y: -10,
  duration: 3,
  repeat: -1,
  yoyo: true,
  ease: 'sine.inOut'
});
```

**适用**：保持画面活力，不让静态画面太死板

#### Pulse（心跳强调）

```javascript
gsap.to('.cta-button', {
  scale: 1.05,
  duration: 1.5,
  repeat: -1,
  yoyo: true,
  ease: 'sine.inOut',
  transformOrigin: 'center center'
});
```

**适用**：CTA 按钮、关键数据、倒计时

#### Scroll/Parallax（视差深度）

```javascript
// 前景移动快，背景移动慢
gsap.to('.fg-layer', { x: -20, duration: 5, ease: 'none' });
gsap.to('.bg-layer', { x: -5, duration: 5, ease: 'none' });
```

**适用**：展示页、品牌故事

#### Counter/Roll（数字滚动）

```javascript
// 数字从 0 滚动到目标值
gsap.fromTo('.stat-number', 
  { textContent: 0 },
  { 
    textContent: 1000000, 
    duration: 1.5, 
    snap: { textContent: 1 },
    ease: 'power2.out',
    onUpdate: function() {
      this.targets()[0].textContent = 
        Math.round(this.targets()[0].textContent).toLocaleString();
    }
  }
);
```

**适用**：数据展示、融资宣布、用户里程碑

### 4. 文字动画模式

#### Split Line（逐行出现）

```javascript
gsap.fromTo('.split-line', 
  { opacity: 0, y: 20 },
  { opacity: 1, y: 0, duration: 0.4, stagger: 0.2 }
);
```

#### Word Highlight（关键词高亮）

```javascript
// 一个词变色 + 放大，然后恢复
const tl = gsap.timeline({ repeat: -1, repeatDelay: 2 });
tl.to('.highlight-word', { color: '#FF6B35', scale: 1.1, duration: 0.4 })
  .to('.highlight-word', { color: 'inherit', scale: 1, duration: 0.4 });
```

#### Text Shuffle（字符洗牌）

```javascript
// 文字从乱码渐变到正确
const finalText = "REVOLUTION";
const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
// 每 50ms 随机替换一个字符，直到全部正确
```

### 5. Logo 动画模式

#### Build Up（品牌标志构建）

```javascript
const tl = gsap.timeline();
tl.fromTo('.logo-mark', { scale: 0, rotation: -180 }, { scale: 1, rotation: 0, duration: 0.8, ease: 'back.out(1.4)' })
  .fromTo('.logo-text', { opacity: 0, x: -20 }, { opacity: 1, x: 0, duration: 0.5 }, '-=0.3');
```

#### Glow Reveal（光效显露）

```javascript
const tl = gsap.timeline();
tl.set('.logo', { filter: 'blur(20px)', opacity: 0 })
  .to('.logo', { filter: 'blur(0px)', opacity: 1, duration: 0.8, ease: 'power2.out' })
  .to('.logo-glow', { opacity: 0.6, duration: 0.3 }, '-=0.2')
  .to('.logo-glow', { opacity: 0, duration: 1 }, '+=0.5');
```

## 时序编排原则

### 黄金节奏公式

```
总时长 = 入场(20%) + 主体内容(50%) + 高潮(20%) + 退场(10%)
```

### 30 秒宣传片节奏模板

```
0-3s:   Logo/标题入场（快）          [ease: power3.out]
3-8s:   核心信息展开（中速）          [ease: power2.out, stagger: 0.1s]
8-20s:  详细内容展示（稳速）          [ease: power1.out, stagger: 0.15s]
20-25s: 关键数据/CTA 强调（加速）     [ease: back.out]
25-30s: Logo 回归 + 联系方式（缓出）  [ease: power2.inOut]
```

### 动效层级管理

| 层级 | 元素 | 动画时长 | 延迟 |
|------|------|---------|------|
| 1（最先） | 背景、氛围元素 | 0.8-1.2s | 0 |
| 2 | 大标题、主视觉 | 0.6-0.8s | +0.2s |
| 3 | 副标题、功能卡片 | 0.4-0.6s | +0.1s |
| 4 | 正文、细节 | 0.3-0.5s | +0.1s |
| 5（最后） | CTA、Logo | 0.4-0.6s | +0.3s |

## HyperFrames 动画最佳实践

### 1. 用 `data-*` 属性驱动动画

```html
<!-- 在 HTML 上标记动画意图，JS 统一读取 -->
<div data-animate="fade-up" data-animate-delay="0.2" data-animate-duration="0.6">
  Product Feature
</div>
```

```javascript
// 统一的动画入口
document.querySelectorAll('[data-animate]').forEach(el => {
  const type = el.dataset.animate;
  const delay = parseFloat(el.dataset.animateDelay) || 0;
  const duration = parseFloat(el.dataset.animateDuration) || 0.5;
  // ... 根据 type 应用对应动画
});
```

### 2. 注册 Frame Adapter

```javascript
// 让 HyperFrames 渲染引擎能控制你的动画
window.__hf_gsap = (composition, currentTime) => {
  // seek 到指定时间点，确保逐帧渲染一致
  gsap.globalTimeline.time(currentTime);
};
```

### 3. 性能优化

- **will-change**：对将要动画的元素加上 `will-change: transform, opacity`
- **避免 layout thrashing**：只动画 `transform` 和 `opacity`，不碰 `width/height/left/top`
- **限制同时动画数**：单帧不超过 20 个动画元素
- **预加载关键帧**：片头 3 秒内用到的资源做 preload

### 4. 响应式动画

```javascript
// 根据画布尺寸调整动画参数
const isVertical = window.innerHeight > window.innerWidth;
const baseDistance = isVertical ? window.innerHeight * 0.1 : window.innerWidth * 0.05;

gsap.fromTo('.slide-element', 
  { y: baseDistance, opacity: 0 },
  { y: 0, opacity: 1, duration: 0.6 }
);
```
