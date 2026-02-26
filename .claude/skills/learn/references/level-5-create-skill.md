# 第5关：创建你的 Skill（毕业关）

## 目标

用户从零创建一个自己的 Skill，包含有效的 SKILL.md 和基本功能。

## 教学流程

### 1. 选择 Skill 主题

> 毕业关！你要创建自己的第一个 Skill。
>
> 不用太复杂，一个简单的 Skill 就行。比如：
> - **daily-summary** — 帮你总结今天做了什么
> - **code-review** — 检查代码并给出建议
> - **translate** — 翻译文本到指定语言
> - **brainstorm** — 围绕一个主题头脑风暴
>
> 你想做什么 Skill？（也可以自己想一个）

等用户回答。

### 2. 创建目录

引导用户操作（教练辅助，但让用户理解每一步）：

```bash
mkdir -p ./learning/my-first-skill
```

### 3. 一起写 SKILL.md

分步引导用户填写 SKILL.md：

#### 第一步：Frontmatter

> 还记得第2关学的吗？先写 frontmatter。

帮用户确定每个字段的值：

- **name** — 根据用户选的主题，用小写+连字符格式
- **description** — 用一两句话说明 Skill 做什么
- **argument-hint** — 用户可以传什么参数
- **allowed-tools** — 这个 Skill 需要什么工具权限

```yaml
---
name: 用户选的名字
description: >-
  用户描述的功能
argument-hint: "[参数说明]"
allowed-tools: Read Write Edit Bash(ls)
---
```

#### 第二步：正文

> 现在写正文。告诉 Claude 这个 Skill 要怎么执行。

引导用户写出：
1. 一个简单的概述
2. 执行流程（至少 2 个步骤）
3. 解析 `$ARGUMENTS` 获取用户输入

示例结构：

```markdown
# Skill 名称

## 概述
你是一个...

## 执行流程

### Step 1: 解析输入
解析 `$ARGUMENTS`，获取...

### Step 2: 执行任务
根据输入...

### Step 3: 输出结果
将结果保存到...
```

### 4. 保存文件

将用户编写的内容保存到 `./learning/my-first-skill/SKILL.md`。

### 5. 复盘

> 回顾一下你刚才做了什么：
> 1. 确定了 Skill 的名称和功能
> 2. 写了 frontmatter 定义元数据
> 3. 写了正文描述执行流程
>
> 这就是一个完整的 Skill！如果你把它放到 `.claude/skills/` 目录下，
> 就可以用 `/技能名` 来调用了。

## 验证

1. `./learning/my-first-skill/SKILL.md` 文件存在
2. 文件包含有效的 YAML frontmatter
3. frontmatter 中 `name` 字段存在且符合小写连字符格式
4. frontmatter 中 `description` 字段存在且非空
5. 文件总行数 > 10 行

全部通过 → 显示通关结语（由 SKILL.md 主编排处理）。
