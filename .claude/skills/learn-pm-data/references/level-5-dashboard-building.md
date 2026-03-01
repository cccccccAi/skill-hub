# 第5关：数据价值看板

> 第4关教了数据叙事方法论，这一关把叙事变成交互式看板。

## 目标

真实生成一个交互式 HTML Dashboard，展示产品数据价值。可在浏览器直接打开。

## 路线提示

> 当前路线（真实数据 / 模拟数据）在启动时已确定，本关不再重复选择。

## 时长

约 15 分钟

## 教学流程

### Step 1：场景设定 + 与数据叙事衔接

告诉用户：「上一关你学会了用数据讲故事。现在把故事变成一个可交互的看板——受众不只是看你写的结论，还能自己点击探索数据。」

关键教学点：「Dashboard 设计的第一步不是选图表，而是问：这个看板要帮受众做什么决策？（和上一关一样，受众决定一切。）」

### Step 2：确定受众

用 AskUserQuestion 问：「这个看板的主要受众是？」
选项从 pack-config.md「Level 5 配置 > 受众选项」读取。

> 真实数据路线的用户基于自己的受众列表选择。

### Step 3：选择 KPI

根据受众选择，用 AskUserQuestion 问：「看板顶部放 4 个 KPI 卡片，选哪些？」
选项从 pack-config.md「Level 5 配置 > KPI 选项」读取，提供 3 组方案：

- 选项 A（宏观）：行业包定义的宏观 KPI 组合
- 选项 B（效果）：行业包定义的效果 KPI 组合
- 选项 C（自选）：从行业包全部 KPI 中选 4 个

### Step 4：选择图表类型

用 AskUserQuestion 问：「展示核心指标趋势最合适的图表是？」

- 折线图（展示 6 个月的趋势变化）（推荐）
- 柱状图（对比各维度的绝对值）
- 组合图（柱状表示量，折线表示率）

关键教学点：

- 折线图适合趋势
- 柱状图适合对比
- 组合图适合"量 + 率"双维度
- **标题要写洞察不写数据名**（第4关学到的原则），例如"某维度进步幅度领先"而非"各维度平均值"
- KPI 卡片用 Green/Yellow/Red 状态色（第4关学到的状态信号）

### Step 5：生成 Dashboard

**这一步真实执行**，生成完整的 HTML 文件。

读取 `./data/skills/interactive-dashboard-builder/SKILL.md` 获取模板和最佳实践。

生成 `./learning/outputs/level-5-dashboard.html`，包含：

**HTML 结构：**

- Dashboard 标题 + 副标题（受众相关）
- 4 个 KPI 卡片（带数值、环比变化、状态颜色）
- 主图表区：趋势图（用户选择的类型）
- 副图表区：维度对比柱状图 + 分布饼图
- 数据明细表（可排序）
- 筛选器：分类维度下拉选择

**CSS 样式：**

- 专业配色（白底 + 蓝灰主色 + 绿/红状态色）
- 卡片阴影 + 圆角
- 响应式布局

**JavaScript：**

- Chart.js CDN 引入
- 数据嵌入为 JSON 变量
- 筛选器联动更新所有图表
- 表格列排序
- Hover 提示

**嵌入数据（JSON）：**

从行业包的 metrics.md 和 user-behavior.md 读取数据并转换为 JSON 格式。真实数据路线使用用户提供的数据。

示例结构（以教育科技行业包为例）：

```javascript
const DASHBOARD_DATA = {
  monthly: [
    // 按月汇总的核心指标时间序列
    {
      month: "2025-09",
      metric1: 2800,
      metric2: 4200000,
      metric3: 850000,
      metric4: 3.2,
    },
    {
      month: "2025-10",
      metric1: 2900,
      metric2: 4350000,
      metric3: 920000,
      metric4: 4.1,
    },
    // ... 更多月份
  ],
  dimensions: [
    // 按业务维度拆分的对比数据
    { name: "维度A", avg_value: 78.5, improvement: 3.8, completion: 0.92 },
    { name: "维度B", avg_value: 72.3, improvement: 5.2, completion: 0.88 },
    // ... 更多维度
  ],
  segments: [
    // 按地域/客群分段的分布数据
    { name: "分段1", count: 1200, users: 1500000, improvement: 5.5 },
    { name: "分段2", count: 800, users: 980000, improvement: 4.8 },
    // ... 更多分段
  ],
  detail_items: [
    // 可下钻的明细项目（如薄弱环节、Top 问题等）
    { topic: "明细项1", affected_users: 45000, score: 52 },
    { topic: "明细项2", affected_users: 38000, score: 55 },
    // ... 更多明细
  ],
};
```

> 注意：以上仅为数据结构示例。实际字段名和数值从行业包读取，或由用户提供。

### Step 6：预览与讲解

生成文件后：

1. 用 `open ./learning/outputs/level-5-dashboard.html` 在浏览器打开
2. 简要讲解：
   - KPI 卡片的设计要点（数值 + 环比 + 颜色 = 10 秒理解）
   - 图表标题要写洞察（"某维度进步幅度最大"而非"各维度平均值"）
   - 筛选器让受众自己探索
3. 用 AskUserQuestion 问：「你觉得这个看板还需要调整什么？」
   - 配色需要调整
   - 想加一个图表
   - 数据维度不够
   - 很好，不需要改

如果需要调整，做一次修改后再次打开预览。

### Step 7：实战提示卡

展示实战提示卡：

```
以后需要数据看板时，对 AI 说：
"帮我生成一个交互式 HTML Dashboard。
受众：[谁在看]
他们需要做的决策：[什么决策]
KPI（4个）：[指标1]、[指标2]、[指标3]、[指标4]
数据：[粘贴 CSV/表格数据]
要求：Chart.js 图表、筛选器联动、标题写洞察、
自包含 HTML 文件可直接浏览器打开。"
```

## 验证条件

- `./learning/outputs/level-5-dashboard.html` 文件已生成
- 文件大小 > 5KB（确保是完整 HTML）
