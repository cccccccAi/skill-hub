---
name: ui-ux-design
description: >-
  UI/UX 设计智能助手。包含 68 种设计风格、96 个配色方案、57 个字体配对、
  99 条 UX 指南、25 种图表类型，覆盖 13 个技术栈。通过 BM25 搜索引擎
  提供优先级驱动的设计建议，从需求分析到设计系统生成全流程辅助。
argument-hint: "[设计需求描述，如：SaaS 仪表盘 深色模式]"
allowed-tools: Read Write Edit Bash(python3) Bash(ls) Bash(mkdir)
---

# UI/UX Design Intelligence

综合设计指南，覆盖 Web 和移动应用。包含 68+ 设计风格、96 个配色方案、57 个字体配对、99 条 UX 指南、25 种图表类型，跨 13 个技术栈。通过 BM25 搜索引擎提供优先级驱动的设计建议。

> 基于 [ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) 集成适配。

## When to Apply

在以下场景参考本技能：
- 设计新 UI 组件或页面
- 选择配色方案和字体
- 审查代码的 UX 问题
- 构建着陆页或仪表盘
- 实现无障碍要求

## Rule Categories by Priority

| Priority | Category | Impact | Domain |
|----------|----------|--------|--------|
| 1 | Accessibility | CRITICAL | `ux` |
| 2 | Touch & Interaction | CRITICAL | `ux` |
| 3 | Performance | HIGH | `ux` |
| 4 | Layout & Responsive | HIGH | `ux` |
| 5 | Typography & Color | MEDIUM | `typography`, `color` |
| 6 | Animation | MEDIUM | `ux` |
| 7 | Style Selection | MEDIUM | `style`, `product` |
| 8 | Charts & Data | LOW | `chart` |

> 各类别详细规则见 `references/quick-reference.md`

---

## How to Use This Skill

### Step 1: Analyze User Requirements

从用户需求中提取：
- **Product type**: SaaS, e-commerce, portfolio, dashboard, landing page
- **Style keywords**: minimal, playful, professional, elegant, dark mode
- **Industry**: healthcare, fintech, gaming, education
- **Stack**: React, Vue, Next.js，默认 `html-tailwind`

### Step 2: Generate Design System (REQUIRED)

**始终先用 `--design-system`** 获取完整设计建议：

```bash
python3 ./design/engine/scripts/search.py "<product_type> <industry> <keywords>" --design-system [-p "Project Name"]
```

该命令会：
1. 并行搜索 5 个域（product, style, color, landing, typography）
2. 应用 `ui-reasoning.csv` 中的 100 条推理规则匹配最佳方案
3. 返回完整设计系统：模式、风格、配色、字体、特效
4. 包含应避免的反模式

**持久化保存**（跨会话复用）：

```bash
python3 ./design/engine/scripts/search.py "<query>" --design-system --persist -p "Project Name" -o ./design/output
```

> 持久化模式的 Master + Overrides 架构详见 `references/workflow-guide.md`

### Step 3: Supplement with Detailed Searches

设计系统生成后，按需搜索特定领域补充细节：

```bash
python3 ./design/engine/scripts/search.py "<keyword>" --domain <domain> [-n <max_results>]
```

| Need | Domain | Example |
|------|--------|---------|
| 更多风格选项 | `style` | `--domain style "glassmorphism dark"` |
| 图表推荐 | `chart` | `--domain chart "real-time dashboard"` |
| UX 最佳实践 | `ux` | `--domain ux "animation accessibility"` |
| 替代字体 | `typography` | `--domain typography "elegant luxury"` |
| 着陆页结构 | `landing` | `--domain landing "hero social-proof"` |

### Step 4: Stack Guidelines

获取特定技术栈的实现指南。未指定时默认 `html-tailwind`：

```bash
python3 ./design/engine/scripts/search.py "<keyword>" --stack html-tailwind
```

> 完整域表和栈列表见 `references/workflow-guide.md`

---

## Common Rules for Professional UI

### Icons & Visual Elements

| Rule | Do | Don't |
|------|----|----- |
| No emoji icons | Use SVG icons (Heroicons, Lucide) | Use emojis as UI icons |
| Stable hover | Use color/opacity transitions | Use scale transforms that shift layout |
| Brand logos | Use official SVG from Simple Icons | Guess or use incorrect paths |
| Icon sizing | Fixed viewBox (24x24) with w-6 h-6 | Mix different sizes randomly |

### Interaction & Cursor

| Rule | Do | Don't |
|------|----|----- |
| Cursor pointer | `cursor-pointer` on all clickable elements | Leave default cursor |
| Hover feedback | Color, shadow, border change | No visual indication |
| Smooth transitions | `transition-colors duration-200` | Instant or >500ms changes |

### Light/Dark Mode Contrast

| Rule | Do | Don't |
|------|----|----- |
| Glass card light mode | `bg-white/80` or higher | `bg-white/10` (too transparent) |
| Text contrast | `#0F172A` (slate-900) for body | `#94A3B8` (slate-400) |
| Border visibility | `border-gray-200` in light mode | `border-white/10` (invisible) |

### Layout & Spacing

| Rule | Do | Don't |
|------|----|----- |
| Floating navbar | `top-4 left-4 right-4` spacing | Stick to `top-0 left-0 right-0` |
| Content padding | Account for fixed navbar height | Content hidden behind fixed elements |
| Consistent width | Same `max-w-6xl` or `max-w-7xl` | Mix different container widths |

---

## Pre-Delivery Checklist

### Visual Quality
- [ ] No emojis used as icons (use SVG)
- [ ] All icons from consistent set (Heroicons/Lucide)
- [ ] Hover states don't cause layout shift
- [ ] Use theme colors directly (bg-primary)

### Interaction
- [ ] All clickable elements have `cursor-pointer`
- [ ] Transitions are smooth (150-300ms)
- [ ] Focus states visible for keyboard navigation

### Light/Dark Mode
- [ ] Light mode text contrast 4.5:1 minimum
- [ ] Glass elements visible in light mode
- [ ] Test both modes before delivery

### Layout
- [ ] Floating elements have spacing from edges
- [ ] Responsive at 375px, 768px, 1024px, 1440px
- [ ] No horizontal scroll on mobile

### Accessibility
- [ ] All images have alt text
- [ ] Form inputs have labels
- [ ] Color is not the only indicator
- [ ] `prefers-reduced-motion` respected
