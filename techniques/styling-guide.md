# HyperFrames 视觉风格指南

## 风格体系总览

```
科技风          极简风          奢华风          活力风          暗黑风
───────        ───────        ───────        ───────        ───────
深蓝+紫         白+灰          金+黑           橙+黄          黑+霓虹
Inter/Mono      Inter/SF       Playfair        Poppins         JetBrains
锋利的角        圆角柔和        衬线装饰        圆润饱满        棱角分明
快节奏          沉稳            缓慢优雅        轻快跳动        暗流涌动
```

## 9 大视觉风格详解

### 1. Tech/Dark（科技暗色风）

HyperFrames 的默认舒适区，16k star 的仓库大部分示例都是这个风格。

```
配色：
- 主色：#6C5CE7（紫罗兰）
- 辅色：#00D2FF（电光蓝）
- 背景：#0A0A1A 到 #1A1A2E 的深色渐变
- 强调：#FF6B6B（珊瑚红）

字体：
- 标题：Inter Extra Bold (700-900), 48-96px, letter-spacing: -2px
- 正文：Inter Regular (400), 18-24px, line-height: 1.6
- 代码：JetBrains Mono, 14-16px

视觉元素：
- 微妙的网格线背景
- 光晕/glow 效果（box-shadow: 0 0 60px rgba(108,92,231,0.3)）
- 细线分隔（1px, opacity 0.1 的白色）
- 渐变按钮（135deg 对角线渐变）
- 圆角：8-12px（小元素），16-24px（卡片）

适用：SaaS 产品、开发者工具、Web3、AI 产品
```

### 2. Minimal/Light（极简亮色风）

```
配色：
- 主色：#1A1A1A（几乎黑色，不用纯黑）
- 辅色：#6C5CE7（品牌色点缀）
- 背景：#FFFFFF 或 #FAFAFA
- 强调：品牌色（少量使用）

字体：
- 标题：Inter/SF Pro Display, 300-600 weight, 充裕留白
- 正文：Inter/SF Pro Text, 16-20px
- 大量留白，行距 1.8

视觉元素：
- 大量留白（padding 常用 80-120px）
- 1px 细灰线
- 图片/截图为主的卡片
- 极少使用阴影（用 0 1px 2px 的轻微阴影替代）
- 圆角：4-8px

适用：设计工具、高端 SaaS、生活方式品牌
```

### 3. Luxury/Gold（奢华风）

```
配色：
- 主色：#C9A96E（香槟金）
- 辅色：#2C2C2C（深灰）
- 背景：#0D0D0D 或 #1A1815
- 渐变：金色到玫瑰金

字体：
- 标题：Playfair Display (serif), 400-700 weight
- 副标题：Cormorant Garamond
- 正文：Lato/Inter, light weight
- 字间距要大（letter-spacing: 4-8px 用于小标题）

视觉元素：
- 金色描边线（1-2px）
- 微妙的粒子/光点背景
- 产品图有柔和的金色反光
- 纹理背景（皮革纹理、大理石纹理）
- 圆角：0-4px（偏方正，有质感）

适用：高端消费品、珠宝、豪车、奢侈品、高端酒店
```

### 4. Vibrant/Playful（活力风）

```
配色：
- 主色：#FF6B35（橘色）
- 辅色：#F7DC6F（明黄）
- 背景：大胆的渐变色或纯色
- 强调：#00D2FF（活泼蓝）

字体：
- 标题：Poppins/Outfit Bold, 700-900 weight
- 正文：Poppins Regular, 16-20px
- 大量圆形、曲线

视觉元素：
- 大色块碰撞
- 圆形/椭圆形状
- 大号表情符号/图标
- 粗边框（3-4px）
- 弹跳动画
- 圆角：16-24px 或全圆角

适用：消费 App、教育产品、儿童品牌、社交产品
```

### 5. Cinematic/Epic（电影感）

```
配色：
- 主色：暖橙/金 + 冷蓝/青（经典橙蓝对比）
- 背景：深色渐变，带胶片颗粒
- 画面比例：2.35:1（宽银幕）或 21:9

字体：
- 标题：Bebas Neue / Anton（无衬线大写，极粗）
- 正文：较小的字号（14-18px）
- 巨大的字号对比

视觉元素：
- 21:9 比例或上下黑边（letterbox）
- 粒子、烟雾、光晕
- 慢动作感（文字缓缓飘入）
- 胶片颗粒叠加层
- 戏剧化的明暗对比（chiaroscuro）

适用：品牌大片、游戏预告、电影感宣传片
```

### 6. Editorial/Magazine（编辑风）

```
配色：
- 主色：黑/白 + 一个亮色点缀
- 背景：干净的白色或浅灰
- 强烈对比

字体：
- 标题：Playfair Display / Bodoni (serif, 粗体)
- 正文：Georgia / Merriweather
- 引用：大号斜体 serif

视觉元素：
- 网格系统布局
- 图文穿插（图片被文字切割）
- 大号引用块
- 编号/项目符号作为装饰
- 非对称布局

适用：媒体品牌、内容平台、杂志风格
```

### 7. Glassmorphism（玻璃态）

```
配色：
- 背景：鲜明的彩色渐变（作为透过玻璃看到的底色）
- 表面：rgba(255,255,255,0.1-0.2) + backdrop-filter: blur(20px)
- 边框：rgba(255,255,255,0.2)
- 阴影：0 8px 32px rgba(0,0,0,0.1)

字体：
- SF Pro / Inter, 中等粗细
- 白色或半透明白色

视觉元素：
- 玻璃卡片悬浮在彩色背景上
- 多层玻璃叠加
- 微妙的光线折射感
- 圆角：16-24px

适用：AI 产品、操作系统级别 UI、未来感设计
```

### 8. Retro/Vaporwave（复古蒸汽波）

```
配色：
- 主色：#FF6EC7（热粉）
- 辅色：#7B2FBE（紫）
- 背景：#0D0221（深紫黑）到 #FF6EC7 的渐变
- 加上 #00F0FF（赛博青）点缀

字体：
- 标题：Press Start 2P / VT323（像素风）
- 或：巨大的无衬线体 + 粗边框
- 日文假名作为装饰元素

视觉元素：
- 80 年代网格线（透视网格）
- 太阳/落日图形
- 扫描线叠加
- 色差效果（text-shadow 偏移）
- 霓虹光效

适用：游戏、音乐、创意品牌、复古主题
```

### 9. Nature/Organic（自然有机风）

```
配色：
- 主色：#4CAF50（森林绿）或 #8BC34A
- 辅色：#795548（大地棕）
- 背景：#F1F8E9（浅绿白）或米色

字体：
- 标题：Lora / DM Serif (有机感的衬线体)
- 正文：Nunito / Rubik (圆润无衬线)
- 柔和的圆形字体

视觉元素：
- 柔和的有机形状（blob shapes）
- 叶子、水波、自然纹理
- 柔光效果
- 渐变中有机的曲线
- 圆角：12-24px

适用：健康品牌、环保、瑜伽、有机食品
```

## 配色速查表

### 科技公司配色参考

| 品牌风格 | 主色 | 辅色 | 背景 |
|---------|------|------|------|
| Stripe 风 | #635BFF | #00D4FF | #0A0F1A |
| Linear 风 | #5E6AD2 | #F7F8F9 | #FFFFFF |
| Vercel 风 | #000000 | #0070F3 | #FAFBFC |
| OpenAI 风 | #10A37F | #202123 | #343541 |
| Apple 风 | #1D1D1F | #86868B | #F5F5F7 |

### 情绪配色

| 情绪 | 主色 | 搭配 |
|------|------|------|
| 信任/专业 | #2563EB | #1E40AF + #DBEAFE |
| 活力/年轻 | #F43F5E | #E11D48 + #FFE4E6 |
| 自然/平静 | #059669 | #047857 + #ECFDF5 |
| 奢华/高端 | #D4AF37 | #B8960C + #FFFDE7 |
| 温暖/亲切 | #F97316 | #EA580C + #FFF7ED |

## 排版系统

### 字号层级（1920x1080）

```
Hero 大标题：64-96px, weight 800-900, letter-spacing: -2px 到 -3px
场景标题：  48-64px, weight 700-800, letter-spacing: -1px 到 -2px
副标题：    28-36px, weight 500-600, letter-spacing: 0
正文：      20-24px, weight 400, line-height: 1.6-1.8
注释/标签： 14-16px, weight 400-500, letter-spacing: 0.5px
```

### 字体组合推荐

```
科技产品：    Inter (标题) + Inter (正文)         [全 Inter 体系]
高端品牌：    Playfair Display + Lato             [衬线 + 无衬线]
现代 SaaS：   Switzer + Inter                     [几何 + 人文]
创意/设计：   Clash Display + Satoshi             [夸张 + 中性]
开发者工具：  JetBrains Mono + Inter              [等宽 + 无衬线]
中文场景：    思源黑体 Bold + 思源黑体 Regular     [统一字体家族]
```

## 构图原则

### 三分法

将 1920x1080 画布三等分：
- 左 1/3：标题/文字
- 右 2/3：产品图/视觉

或将关键元素放在四个交叉点上。

### 视觉重量平衡

```
重元素（大图、粗标题）
    ↓
轻元素（正文、Logo、CTA）
    ↓
负空间（留白，给眼睛休息）
```

### 引导视线

```
左上 → 右上 → 左下 → 右下（Z 型阅读路径）
或
中心 → 四周（放射型）
或
上 → 下（垂直滚动感）
```

## 超实用 Prompt 片段

### 快速风格 Prompt

```
"视觉风格采用 Tech/Dark 路线：
- 背景：深色渐变 #0A0A1A → #1A1A2E，有微妙的网格线纹理
- 主色调：紫蓝渐变，标题用 #6C5CE7 到 #00D2FF 的渐变文字
- 卡片：半透明深色卡片，1px 白色边框 opacity 0.1，圆角 16px
- 字体：Inter，标题 800 weight 64px，正文 400 weight 22px
- 光效：标题区域有柔和的紫色光晕（box-shadow: 0 0 80px rgba(108,92,231,0.25)）"
```

### 快速排版 Prompt

```
"排版系统：
- Hero：'The Future of AI' 居中，96px, Inter Extra Bold, letter-spacing: -3px
- 渐变文字：linear-gradient(135deg, #6C5CE7, #00D2FF)
- 副标题：22px, Inter Regular, opacity 0.7, 居中
- 场景标题：左上角，48px, Inter Bold, #FFFFFF
- 正文：左侧对齐，20px, line-height: 1.8, 最大宽度 600px"
```
