# 工具与生态

## 核心工具链

| 工具 | 用途 | 命令 |
|------|------|------|
| **HyperFrames CLI** | 脚手架、预览、渲染 | `npx hyperframes` |
| **HyperFrames Skills** | AI Agent 知识包 | `npx skills add heygen-com/hyperframes` |
| **HyperFrames Blocks** | 预制组件安装 | `npx hyperframes add <name>` |
| **HyperFrames Media** | TTS/转录/去背景 | `npx hyperframes-media` |

## AI Coding Agents

HyperFrames 支持的所有 AI agent：

| Agent | 特点 | 推荐度 |
|-------|------|-------|
| **Claude Code** | 原生支持，Skills 系统深度集成 | ⭐⭐⭐⭐⭐ |
| **Cursor** | 上下文感知强，UI 友好 | ⭐⭐⭐⭐ |
| **Gemini CLI** | Google 生态，免费额度 | ⭐⭐⭐⭐ |
| **Codex (OpenAI)** | GPT 生态 | ⭐⭐⭐ |
| **Qwen CLI** | 开源模型，中文友好 | ⭐⭐⭐ |
| **GitHub Copilot** | IDE 整合 | ⭐⭐⭐ |

## 动画库

| 库 | 适合 | CDN |
|------|------|-----|
| **GSAP 3.12** | 复杂时间线、商业项目 | `cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js` |
| **Anime.js** | 轻量 SVG、独立动画 | `cdnjs.cloudflare.com/ajax/libs/animejs/3.2.2/anime.min.js` |
| **Lottie Web** | AE 导出动画 | `cdnjs.cloudflare.com/ajax/libs/lottie-web/5.12.2/lottie.min.js` |
| **Three.js** | 3D/WebGL | `cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js` |

## 字体 CDN

```html
<!-- Inter (最通用) -->
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900');

<!-- Playfair Display (衬线/高端) -->
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&display=swap');

<!-- Bebas Neue (电影感) -->
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

<!-- JetBrains Mono (代码) -->
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600&display=swap');

<!-- Outfit (现代几何) -->
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;800;900&display=swap');

<!-- Caveat (手写) -->
@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;700&display=swap');

<!-- Poppins (活泼) -->
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;900&display=swap');
```

## 图片/Icon 资源

| 资源 | URL | 用途 |
|------|-----|------|
| **Unsplash** | `https://unsplash.com/` | 免费高质量图片 |
| **Pexels** | `https://www.pexels.com/` | 免费视频素材 |
| **Lucide Icons** | `https://lucide.dev/` | 开源 SVG 图标 |
| **Heroicons** | `https://heroicons.com/` | Tailwind 风格 SVG |
| **Simple Icons** | `https://simpleicons.org/` | 品牌 Logo SVG |

## 音频资源

| 资源 | 用途 |
|------|------|
| **HyperFrames TTS** (`npx hyperframes-media tts`) | 54 种语音的免费 TTS |
| **Pixabay Music** | 免费 BGM |
| **Freesound** | 免费音效 |
| **YouTube Audio Library** | 免费 BGM + 音效 |

## 模板工作流工具

```bash
# 快速开始
npx hyperframes init my-video
cd my-video
npx hyperframes add logo-outro grain-overlay shimmer-sweep

# 用 AI 生成
# "请根据 awesome-hyperframes-prompt/templates/product-showcase/tech-product-launch/prompt.md
#  生成一段视频，把产品名改成我的产品"

# 预览循环
npx hyperframes preview    # 浏览器实时预览

# 渲染输出
npx hyperframes render     # → output.mp4

# 代码检查
npx hyperframes lint        # 验证 data 属性
npx hyperframes inspect     # 查看时间线信息
```
