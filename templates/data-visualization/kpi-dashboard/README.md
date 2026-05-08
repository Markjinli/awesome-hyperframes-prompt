# KPI Dashboard — 数据仪表盘动画

## 效果

25 秒的 KPI 仪表盘动画，4 个场景依次展示：营收、增长指标、客户结构、未来展望。深色 Dashboard 风，适合季度/年度业务汇报。

## 适用场景

- 季度/年度业务回顾
- 融资 Pitch Deck 视频化
- 内部 Town Hall 数据展示
- 投资人更新视频

## 关键技巧

- **数字滚动**：可以用 GSAP counter 实现更生动的数字动画
- **Bar Chart**：scaleY + stagger 入场，模拟柱状图生长
- **SVG Donut**：stroke-dasharray 控制每个扇区比例
- **Grid 纹理背景**：`background-image: linear-gradient(...)` 做微妙的网格线

## 自定义方法

1. 修改数值：搜索 `$48.2M`、`142%`、`8.5K` 等替换为你的数据
2. 修改 Donut 比例：调整 `stroke-dasharray` 的三个值
3. 修改颜色：`#38BDF8`（蓝）= 营收、`#4ADE80`（绿）= 利润、`#F59E0B`（黄）= ROI
4. 修改标签：搜索 `Enterprise`、`Mid-Market`、`SMB` 替换为你的客户分类

## 需要安装的 Blocks

```bash
npx hyperframes add data-chart
```
