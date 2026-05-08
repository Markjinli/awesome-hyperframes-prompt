# Tech Product Launch — 科技产品发布

## 效果

30 秒的科技产品发布宣传片。"Nexus AI" 的发布视频，5 个完整场景：Logo 入场 → 痛点 → 功能展示 → 数据验证 → CTA。

## 适用场景

- AI/SaaS 产品发布
- 众筹/Kickstarter 产品视频
- TechCrunch/展会产品展示

## 关键技巧

- **场景间无空隙**：每个场景的 `data-start + data-duration` 精确等于下一个场景的 `data-start`
- **GSAP timeline position 参数**：用 `-=0.2` 让前后动画有重叠，避免"一个播完才播下一个"的生硬感
- **CTA 放在高潮**：social overlay 在数据展示场景触发，不在片尾

## 自定义方法

1. 全局搜索替换 `Nexus AI` → 你的产品名
2. 修改配色：`#6C5CE7` → 你的品牌色（在 CSS 和所有动画中出现）
3. 替换产品图 URL
4. 调整场景时长（修改 `data-duration`，确保总和 = 30s）
5. 替换痛点/功能描述文字

## 需要安装的 Blocks

```bash
npx hyperframes add logo-outro grain-overlay
```
