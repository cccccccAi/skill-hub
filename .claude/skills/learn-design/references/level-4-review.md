# 第4关：设计评审找问题

## 目标

学会用设计规则"审查"一个页面，而不只是"生成"。设计系统不只是起点，也是终点的检查标准。

## 教学流程

### Step 1 — 生成"有问题的页面"

读取 `./design/output/learn-progress.md` 获取案例项目和 v0 粗稿信息。

基于第 1 关的粗稿 v0（AI 全自动的那个版本），生成一个简单的 HTML 页面，保存到 `./design/output/bad-page.html`。

**关键：故意埋入 5-6 个常见设计问题**：

参考 [bad-page-template.md](bad-page-template.md) 中的模板，根据用户的案例项目定制内容，但保留所有预设问题。

生成完成后告诉用户：
> 我根据第 1 关的设计系统生成了一个页面。这个页面看起来"差不多"，但里面藏了一些专业设计师一眼就能发现的问题。

### Step 2 — 用户"找茬"

展示页面中有问题的 6 个区域的文字描述（因为终端不能渲染 HTML，用文字描述关键特征）。

用 AskUserQuestion（multiSelect: true）让用户勾选发现的问题：

- 按钮和链接用了 emoji（🎨 ☕ 🏋️）当作图标
- 浅色背景上的浅灰色文字看不清
- 手机上的按钮太小，不好点
- 鼠标移到按钮上没有任何变化
- 有些动画太慢了（超过 1 秒）
- 在手机上内容超出屏幕宽度需要左右滑

**计分**：
- 发现 5-6 个 → "火眼金睛！你已经有设计评审的直觉了。"
- 发现 3-4 个 → "不错！你抓住了主要问题。"
- 发现 1-2 个 → "好的开始！让我们一起看看还有哪些隐藏问题。"
- 0 个 → "别担心，设计评审是需要练习的技能。让我们一个个看。"

### Step 3 — 揭晓 + 搜索验证

逐个揭晓 6 个问题，对每个问题：
1. 说明问题是什么（1 行）
2. 用搜索引擎查对应规则：

```bash
python3 ./design/engine/scripts/search.py "<规则关键词>" --domain ux --max-results 1
```

3. 展示规则的 **Do / Don't / Severity**（3 行）

每展示 2 个问题后用 AskUserQuestion 过渡（控制输出量）。

**6 个问题与对应搜索**：

| 问题 | 搜索词 | 规则 | 严重程度 |
|------|--------|------|---------|
| emoji 当图标 | `"emoji icon svg"` (domain: ux) | no-emoji-icons | MEDIUM |
| 文字对比度不足 | `"color contrast ratio"` (domain: ux) | color-contrast | CRITICAL |
| 点击区域太小 | `"touch target size"` (domain: ux) | touch-target-size | CRITICAL |
| 无 hover 反馈 | `"cursor pointer hover"` (domain: ux) | cursor-pointer | MEDIUM |
| 动画过慢 | `"animation duration timing"` (domain: ux) | duration-timing | MEDIUM |
| 水平滚动 | `"horizontal scroll viewport"` (domain: ux) | horizontal-scroll | HIGH |

### Step 4 — 修复演示

选 2-3 个最重要的问题（CRITICAL 优先），展示修复前后的关键代码差异：

```
❌ 修复前：<span style="color: #94A3B8">浅灰色文字</span>
✅ 修复后：<span style="color: #0F172A">深色文字（对比度 > 4.5:1）</span>

❌ 修复前：<button style="padding: 4px 8px">太小的按钮</button>
✅ 修复后：<button style="padding: 12px 24px; min-height: 44px">合适的按钮</button>
```

### Step 5 — 通关总结

**核心教学点**：设计系统不只是"生成"工具，更是"审查"工具。专业设计师的价值不在于让 AI 生成得更花哨，而在于能发现 AI 输出中的问题。

## 验证条件

- 用户完成了"找茬"练习（AskUserQuestion 已回答）
- 至少发现了 3 个问题

## 未通过处理

如果用户发现不到 3 个问题，不要阻止通关——这关的重点是学习评审方法，不是考试。揭晓完所有问题后即可通关。
