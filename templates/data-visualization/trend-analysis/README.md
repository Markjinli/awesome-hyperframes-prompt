# Trend Analysis — 趋势分析视频

## 效果

28 秒的数据趋势分析视频，NYT/Reuters 编辑风格。从标题页 → 关键数据 → 时间线里程碑 → 区域对比。干净、优雅、数据优先。

## 适用场景

- 行业趋势报告
- 市场研究展示
- 白皮书视频摘要
- 数据新闻内容

## 关键技巧

- **Playfair Display**：衬线标题字体 + 数据新闻风天然匹配
- **SVG 折线图**：stroke-dasharray + stroke-dashoffset 动画模拟绘制过程
- **时间线**：单线 + dot 标记的横向时间线，比纵向的更省空间
- **区域对比卡片**：2x2 grid，简洁的白色卡片 + 国旗 emoji 区分区域

## 自定义方法

1. 替换主题：所有 `Remote Work` 文本 → 你的主题
2. 替换数据点：修改 milestone 年份和百分比
3. 修改折线图：调整 SVG polyline 的 points 坐标
4. 替换区域：修改 4 张 region card 的内容
5. 修改色板：`#2563EB` → 你的品牌色，`#FBFBF9` → 你的背景色
