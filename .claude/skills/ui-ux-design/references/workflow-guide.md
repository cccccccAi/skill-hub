# Workflow Guide — 搜索域、技术栈与持久化

## Prerequisites

```bash
python3 --version || python --version
```

macOS: `brew install python3` | Ubuntu: `sudo apt install python3` | Windows: `winget install Python.Python.3.12`

---

## Available Domains

| Domain | Use For | Example Keywords |
|--------|---------|------------------|
| `product` | 产品类型推荐 | SaaS, e-commerce, portfolio, healthcare, beauty |
| `style` | UI 风格、颜色、特效 | glassmorphism, minimalism, dark mode, brutalism |
| `typography` | 字体配对、Google Fonts | elegant, playful, professional, modern |
| `color` | 按产品类型的配色方案 | saas, ecommerce, healthcare, beauty, fintech |
| `landing` | 页面结构、CTA 策略 | hero, hero-centric, testimonial, pricing |
| `chart` | 图表类型、库推荐 | trend, comparison, timeline, funnel, pie |
| `ux` | 最佳实践、反模式 | animation, accessibility, z-index, loading |
| `react` | React/Next.js 性能 | waterfall, bundle, suspense, memo, rerender |
| `web` | Web 界面指南 | aria, focus, keyboard, semantic, virtualize |
| `icons` | 图标推荐 | lucide, heroicons, category, symbol |

## Available Stacks (13)

| Stack | Focus |
|-------|-------|
| `html-tailwind` | Tailwind utilities, responsive, a11y (**DEFAULT**) |
| `react` | State, hooks, performance, patterns |
| `nextjs` | SSR, routing, images, API routes |
| `vue` | Composition API, Pinia, Vue Router |
| `nuxtjs` | Nuxt modules, auto-imports, Nitro |
| `nuxt-ui` | Nuxt UI components, theming |
| `svelte` | Runes, stores, SvelteKit |
| `astro` | Islands, content collections, SSG |
| `swiftui` | Views, State, Navigation, Animation |
| `react-native` | Components, Navigation, Lists |
| `flutter` | Widgets, State, Layout, Theming |
| `shadcn` | shadcn/ui components, theming, forms |
| `jetpack-compose` | Composables, Modifiers, State Hoisting |

---

## Output Formats

```bash
# ASCII box (default) — best for terminal
python3 ./design/engine/scripts/search.py "fintech crypto" --design-system

# Markdown — best for docs
python3 ./design/engine/scripts/search.py "fintech crypto" --design-system -f markdown
```

---

## Persistence: Master + Overrides Pattern

### 保存设计系统

```bash
python3 ./design/engine/scripts/search.py "<query>" --design-system --persist -p "Project Name" -o ./design/output
```

创建：
- `./design/output/project-name/MASTER.md` — 全局设计规则源
- `./design/output/project-name/pages/` — 页面级覆盖目录

### 带页面覆盖

```bash
python3 ./design/engine/scripts/search.py "<query>" --design-system --persist -p "Project Name" --page "dashboard" -o ./design/output
```

额外创建：
- `./design/output/project-name/pages/dashboard.md` — 页面级偏差规则

### 层级检索逻辑

1. 构建某页面（如 "Checkout"）时，先检查 `pages/checkout.md`
2. 如果页面文件存在，其规则**覆盖** Master 文件
3. 如果不存在，仅使用 `MASTER.md`

### 上下文检索提示

```
I am building the [Page Name] page. Please read design-system/MASTER.md.
Also check if design-system/pages/[page-name].md exists.
If the page file exists, prioritize its rules.
If not, use the Master rules exclusively.
Now, generate the code...
```

---

## Example Workflow

**需求**："为美容 SPA 做一个专业的着陆页"

### Step 1: Analyze
- Product type: Beauty/Spa service
- Style: elegant, professional, soft
- Industry: Beauty/Wellness
- Stack: html-tailwind (default)

### Step 2: Generate Design System

```bash
python3 ./design/engine/scripts/search.py "beauty spa wellness service elegant" --design-system -p "Serenity Spa"
```

### Step 3: Supplement Details

```bash
# UX animation & accessibility
python3 ./design/engine/scripts/search.py "animation accessibility" --domain ux

# Alternative typography
python3 ./design/engine/scripts/search.py "elegant luxury serif" --domain typography
```

### Step 4: Stack Guidelines

```bash
python3 ./design/engine/scripts/search.py "layout responsive form" --stack html-tailwind
```

Then synthesize all results and implement.
