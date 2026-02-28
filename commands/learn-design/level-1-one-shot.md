# 第1关：一键出图 vs 一段话

## 目标

让用户亲眼看到"需求描述质量"对 AI 输出的巨大影响。建立 baseline（粗稿 v0），后续关卡在此基础上逐步精炼。

## 教学流程

### Step 1 — 选择案例项目

用 AskUserQuestion 让用户选择贯穿 5 关的案例项目：

- **本地咖啡品牌官网** — 温暖、手工、文艺青年
- **健身 App 着陆页** — 活力、专业、运动感
- **独立设计师作品集** — 个性、创意、极简
- 自定义（Other）

记录用户选择，后续所有关卡复用。

### Step 2 — 第一次搜索：模糊需求

告诉用户："我们先用最简单的方式试一下，看看 AI 能给出什么。"

执行：

```bash
python3 ./design/engine/scripts/search.py "做个网站" --design-system
```

展示输出时：

1. 先说一句概括："AI 给了一套设计系统，包含页面模式、风格、配色、字体等。"
2. 让用户选择是否看完整输出
3. 标记这个结果为"**粗稿 v0**"

### Step 3 — 讲解需求描述 4 要素

简短讲解（不超过 8 行）：

> AI 设计工具的输出质量，90% 取决于你给的需求描述。
> 好的需求包含 4 个要素：
>
> 1. **产品类型** — 官网、App、仪表盘、着陆页
> 2. **行业/场景** — 咖啡、健身、设计、医疗
> 3. **风格关键词** — warm、minimal、elegant、playful
> 4. **目标受众** — 文艺青年、专业人士、运动爱好者

### Step 4 — 第二次搜索：精准需求

根据用户选的案例，构造精准搜索词。

**案例对应搜索词**：

- 咖啡品牌 → `"local coffee brand website warm artisan cozy"`
- 健身 App → `"fitness app landing page energetic professional sporty"`
- 设计师作品集 → `"designer portfolio minimal creative personal"`
- 自定义 → 引导用户用英文写出 4 要素

执行：

```bash
python3 ./design/engine/scripts/search.py "<精准关键词>" --design-system -p "<项目名>"
```

### Step 5 — 对比两次结果

简要对比（不超过 10 行），突出关键差异：

- 风格匹配度
- 配色是否符合行业特征
- 字体搭配是否合适

**核心金句**：同一个工具，需求描述不同，输出天差地别。

### Step 6 — 保存进度

将案例项目信息和进度保存到 `./design/output/learn-progress.md`。

## 验证条件

- `./design/output/` 下有设计系统输出

## 未通过处理

如果搜索命令执行失败：

- 检查 Python 是否安装
- 检查 `./design/engine/data/styles.csv` 是否存在
- 给出具体修复建议
