# 第5关：创建你的 Skill（毕业关）

## 目标

用户从零创建一个贴合自己工作场景的 Skill，所有引导通过选择题完成。

## 教学流程

### Step 1: 了解角色

使用 AskUserQuestion 提问：

```
你的日常工作角色是？
```

选项：
- 产品经理
- 设计师
- 运营
- 市场/品牌

记录用户选择的角色，后续步骤据此动态调整。

### Step 2: 了解痛点

根据用户角色，使用 AskUserQuestion 提问对应痛点：

**产品经理：**
```
你日常最头疼的事情是？
```
- 写 PRD 太耗时，每次都要从头梳理
- 竞品分析要翻大量资料，整理费时
- 需求评审总被挑战，缺少数据支撑
- 用户反馈太杂，难以归纳出优先级

**设计师：**
```
你日常最头疼的事情是？
```
- 设计方案要写长篇说明文档
- 设计评审被质疑缺少依据
- 多版本文案对比很繁琐
- 交互规范文档维护太累

**运营：**
```
你日常最头疼的事情是？
```
- 活动方案写作太耗时
- 数据报告整理重复劳动多
- 用户运营话术千篇一律
- 内容选题总没灵感

**市场/品牌：**
```
你日常最头疼的事情是？
```
- 品牌文案需要多版本适配不同渠道
- 竞品动态跟踪费时费力
- 营销报告格式重复
- 社交媒体内容创意匮乏

### Step 3: 给出定制 Skill 建议

根据角色+痛点组合，给出 3 个针对性 Skill 建议。使用 AskUserQuestion 让用户选择。

每个建议包含：
- **Skill 名称**（小写连字符格式）
- **一句话描述**：能干什么
- **使用场景**：什么时候用
- **调用示例**：`/skill-name 参数`

#### 建议参考（根据角色+痛点组合选取）

**产品经理 + PRD：**
- `prd-draft` — 基于需求描述快速生成 PRD 框架，含用户故事和验收标准
- `requirement-qa` — 模拟需求评审，提前发现逻辑漏洞和缺失场景
- `user-story-gen` — 从一句话需求展开为完整用户故事集

**产品经理 + 竞品分析：**
- `competitor-brief` — 输入竞品名称，整理核心功能对比和差异化要点
- `feature-compare` — 多产品功能矩阵对比，输出结构化表格
- `market-scan` — 从产品角度梳理行业趋势和机会点

**产品经理 + 需求评审：**
- `requirement-qa` — 模拟评审提问，提前准备回答
- `data-argument` — 为需求补充数据论据和用户痛点佐证
- `decision-doc` — 生成决策文档，记录方案对比和选择理由

**产品经理 + 用户反馈：**
- `feedback-digest` — 归纳用户反馈为分类摘要和优先级排序
- `insight-extract` — 从反馈原文中提取关键洞察和行动建议
- `voice-of-user` — 把碎片化反馈整理为用户声音报告

**设计师 + 设计说明：**
- `design-brief` — 基于设计稿描述生成设计说明文档
- `design-rationale` — 为设计决策补充理论依据和竞品参考
- `handoff-doc` — 生成开发交付文档，标注交互细节

**设计师 + 设计评审：**
- `design-critique` — 模拟评审视角，提前发现设计方案弱点
- `design-rationale` — 为设计选择补充可用性原则和数据支撑
- `ux-checklist` — 可用性检查清单，逐项验证设计方案

**设计师 + 文案对比：**
- `copy-polish` — 多版本文案对比优化，输出推荐版本和理由
- `copy-variants` — 基于一句核心文案生成多个风格变体
- `tone-check` — 检查文案是否符合品牌调性和目标受众

**设计师 + 规范文档：**
- `design-spec` — 基于组件描述生成交互规范文档
- `component-doc` — 为设计组件生成使用说明和示例
- `changelog-gen` — 根据设计修改记录生成变更日志

**运营 + 活动方案：**
- `event-plan` — 基于活动目标快速生成方案框架
- `event-copy` — 生成活动推广文案（多渠道适配）
- `event-review` — 活动方案自检，补充遗漏环节

**运营 + 数据报告：**
- `report-template` — 基于数据维度生成报告模板和分析框架
- `data-narrative` — 把数据表格转化为可读的分析叙述
- `weekly-digest` — 从数据要点生成周报摘要

**运营 + 话术：**
- `reply-craft` — 基于用户场景生成个性化回复话术
- `message-variants` — 一条核心信息生成多种语气版本
- `empathy-reply` — 生成带共情感的用户沟通话术

**运营 + 选题：**
- `topic-brainstorm` — 围绕领域关键词生成内容选题清单
- `hook-writer` — 为选题生成吸睛开头和标题
- `content-calendar` — 基于主题方向生成周/月内容排期

**市场/品牌 + 多版本文案：**
- `copy-adapt` — 一篇核心文案适配多个渠道格式
- `copy-variants` — 生成不同风格的文案变体
- `slogan-gen` — 基于品牌定位生成 slogan 候选

**市场/品牌 + 竞品跟踪：**
- `competitor-watch` — 整理竞品近期动态要点
- `market-brief` — 生成行业/竞品简报
- `diff-analysis` — 与竞品的差异化定位分析

**市场/品牌 + 营销报告：**
- `campaign-report` — 基于数据生成营销活动复盘报告
- `report-template` — 生成标准化报告框架
- `insight-summary` — 从营销数据提炼关键洞察

**市场/品牌 + 社交媒体：**
- `social-post` — 基于主题快速生成社交媒体帖子
- `content-idea` — 围绕品牌调性生成内容创意
- `trending-hook` — 结合热点生成品牌借势内容

### Step 4: 方案确认

展示用户选中 Skill 的详细方案：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 你的 Skill 方案

名称：/skill-name
功能：一句话描述
使用场景：什么时候用
调用方式：/skill-name 参数说明

它能帮你解决：{对应痛点}
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

使用 AskUserQuestion 确认：
- "就用这个方案，开始创建"
- "换一个 Skill 建议"（回到 Step 3）

### Step 5: 生成 SKILL.md

创建目录：
```bash
mkdir -p ./learning/my-first-skill
```

根据前面选择的内容，自动生成 SKILL.md。关键字段已根据选择预填好，正文流程根据 Skill 类型自动编排。

生成的 SKILL.md 应包含：

```yaml
---
name: {用户选的名字}
description: >-
  {基于建议的描述}
argument-hint: "{参数说明}"
allowed-tools: Read Write Edit Bash(ls)
---
```

正文至少包含：
1. 概述（角色定位）
2. 执行流程（3-4 个步骤）
3. 解析 `$ARGUMENTS`
4. 输出规范

保存到 `./learning/my-first-skill/SKILL.md`。

### Step 6: 展示成品 + 讲解

在终端展示完整 SKILL.md，并逐块讲解：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📄 你的第一个 Skill
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

{展示 SKILL.md 全文}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

讲解要点：
- frontmatter 各字段的作用（回顾第2关知识）
- 正文是如何指导 AI 执行的
- allowed-tools 为什么选了这几个

最后告知：
> 如果想实际使用，只需要把这个文件复制到 `.claude/skills/{skill-name}/SKILL.md`，
> 然后就可以用 `/{skill-name}` 来调用了！

## 验证

1. `./learning/my-first-skill/SKILL.md` 文件存在
2. 文件包含有效的 YAML frontmatter
3. frontmatter 中 `name` 字段存在且符合小写连字符格式
4. frontmatter 中 `description` 字段存在且非空
5. 文件总行数 > 10 行

全部通过 → 显示通关结语（由 SKILL.md 主编排处理）。
