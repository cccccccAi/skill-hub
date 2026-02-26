# 第1关：项目结构导览

## 目标

让用户了解 skill-hub 的目录结构和各部分职责。

## 教学流程

### 1. 检查当前位置

先检查 `.claude/skills/` 目录是否存在且有内容（`ls .claude/skills/`）。

- **目录存在且有 ≥2 个子目录** → 已在 skill-hub，跳关
- **目录不存在** → 提示用户需要先打开 skill-hub 项目（参考 `learning/getting-started.md`）

### 2. 目录导览

带用户看目录结构：

```bash
ls -la
```

讲解每个关键目录：

- **`.claude/skills/`** — 所有技能定义的家。每个子目录就是一个 Skill。
- **`writing/`** — 写作工作空间
  - `examples/` — 风格参考文章，Skill 会读取这些学习写作风格
  - `drafts/` — 中间产物，写作过程中的草稿
  - `output/` — 最终文章，也就是成品
- **`learning/`** — 你的学习工作空间（就是现在用的）
- **`templates/`** — Skill 模板骨架，第5关创建 Skill 时会用到
- **`tools/`** — 预置的安装包（cc-switch、Windows Terminal）
- **`CLAUDE.md`** — 项目的"说明书"，Claude Code 每次启动都会读这个文件

### 3. CLAUDE.md 的作用

> CLAUDE.md 是整个项目的"入口说明书"。Claude Code 每次启动都会自动读取它。
> 它告诉 AI：这个项目是什么、有哪些 Skill 可以用、写作规范是什么。
>
> 后面创建自己的 Skill 时，你也会和这个文件打交道。

## 验证

运行以下检查：

1. `ls .claude/skills/ | wc -l` → 至少 2 个目录

通过 → 显示：

```
✅ 第1关通过！你已经了解了 skill-hub 的项目结构。
```
