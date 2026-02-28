# 第3关：配色与字体的人工选择

## 目标

体验"AI 推荐 vs 人工选择"的差异——AI 按数据匹配，人按品牌和情感选择。完成后形成"精稿 v1"。

## 教学流程

### Step 1 — 配色选择

读取 `./design/output/learn-progress.md` 获取案例关键词。

搜索 3 套候选配色方案：

```bash
python3 ./design/engine/scripts/search.py "<案例关键词>" --domain color --max-results 3
```

展示每套方案时，重点突出：

- 色值（Primary / Secondary / CTA / Background / Text）
- **Notes 字段**（配色背后的心理学和设计理由）

用 AskUserQuestion 让用户选择：

- 方案 A — [展示色值 + 一句话描述]
- 方案 B — [展示色值 + 一句话描述]
- 方案 C — [展示色值 + 一句话描述]
- 都不满意，我想搜索其他方向

**关键讲解**（选择后，2 行）：

> AI 按"产品类型"匹配配色——咖啡品牌就推荐棕色系。但你可能知道"我们走的是北欧极简风，要冷色调"。这就是人的判断价值。

### Step 2 — 字体选择

搜索 3 套候选字体配对：

```bash
python3 ./design/engine/scripts/search.py "<案例风格关键词>" --domain typography --max-results 3
```

展示时重点突出：

- Heading Font + Body Font
- **Mood/Style Keywords**（情感描述）
- **Best For**（适用场景）
- Google Fonts 链接（方便用户预览）

用 AskUserQuestion 让用户选择，格式同上。

**关键讲解**（选择后，2 行）：

> 字体搭配决定品牌"说话的语气"。Playfair Display 像优雅的杂志，Fira Code 像程序员的终端。你选的字体反映了你对品牌的理解。

### Step 3 — 风格微调

第 1 关生成的 STYLE 是 AI 推荐的第一名。现在让用户决定是否调整。

用 AskUserQuestion：

- 保留 AI 推荐的风格（当前是 XXX）
- 搜索替代风格，我想要更 [温暖/冷酷/活泼/...] 的感觉
- 保留基础风格，但想调整某个细节

如果用户选搜索替代：

```bash
python3 ./design/engine/scripts/search.py "<用户描述的感觉>" --domain style --max-results 3
```

展示结果让用户二选一。

### Step 4 — 组合成"精稿 v1"

把用户的选择汇总，与第 1 关的 v0 做简短对比（不超过 10 行）：

```
维度        v0（AI 全自动）          v1（人工选择）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
配色        <AI 推荐色值>            <用户选择色值>
字体        <AI 推荐字体>            <用户选择字体>
风格        <AI 推荐风格>            <用户选择/保留>
品牌感      通用的                   贴合品牌的
```

将用户选择记录到 `./design/output/learn-progress.md` 中，追加：

```markdown
## 用户设计选择（第3关）

- 配色：<方案编号和色值>
- 字体：<字体配对名称>
- 风格：<风格名称>
```

### Step 5 — 通关总结

**核心教学点**：同样的工具，人参与选择后，结果从"通用"变成"品牌专属"。

## 验证条件

- 用户完成了配色选择（AskUserQuestion 已回答）
- 用户完成了字体选择（AskUserQuestion 已回答）
