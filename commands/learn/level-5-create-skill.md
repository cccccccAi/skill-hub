# 第5关：创建你的 Skill（毕业关）

## 目标

用户从零创建一个贴合自己工作场景的 Skill，关键环节亲手参与。

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
- 数据分析师
- HR / 人力资源
- 项目经理

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

**数据分析师：**

```
你日常最头疼的事情是？
```

- 写分析报告太耗时，每次都要从数据讲到结论
- SQL 写完还要手动整理成可读的表格和图表描述
- 业务方提的数据需求描述模糊，要反复沟通
- 定期报表格式重复，每周/月都是同样的模板

**HR / 人力资源：**

```
你日常最头疼的事情是？
```

- JD 写了又写，每个岗位都要重新措辞
- 面试评估报告格式不统一，写起来费时
- 员工沟通话术需要因人而异，难以批量准备
- 培训方案和课程大纲从零开始太慢

**项目经理：**

```
你日常最头疼的事情是？
```

- 项目周报/月报写起来重复且耗时
- 会议纪要整理费时，关键决策容易遗漏
- 风险评估和问题跟踪缺少结构化模板
- 跨部门沟通邮件要反复斟酌措辞

### Step 3: 给出定制 Skill 建议

根据角色+痛点组合，给出 3 个针对性 Skill 建议。使用 AskUserQuestion 让用户选择。

每个建议包含：

- **Skill 名称**（小写连字符格式）
- **一句话描述**：能干什么
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

**数据分析师 + 分析报告：**

- `analysis-report` — 基于数据摘要生成完整分析报告（背景→发现→建议）
- `data-story` — 把数据表格转化为业务叙述，让非技术人也能看懂
- `chart-narrator` — 为图表生成解读文字，指出趋势和异常点

**数据分析师 + SQL/数据整理：**

- `sql-doc` — 为 SQL 查询生成可读的说明文档和结果解读
- `data-dictionary` — 基于表结构描述生成数据字典文档
- `query-explain` — 用自然语言解释复杂 SQL 的逻辑和用途

**数据分析师 + 需求沟通：**

- `requirement-clarify` — 把模糊的业务需求转化为明确的数据需求文档
- `metric-define` — 基于业务目标定义关键指标和计算口径
- `question-reframe` — 把业务方的模糊问题拆解为可分析的具体问题

**数据分析师 + 定期报表：**

- `report-template` — 基于指标维度生成标准化报表模板
- `weekly-insight` — 从周数据变化中提炼关键洞察和行动建议
- `anomaly-brief` — 检测数据异常并生成异常说明简报

**HR + JD 撰写：**

- `jd-writer` — 基于岗位需求快速生成结构化 JD
- `jd-polish` — 优化现有 JD 的措辞，提升吸引力
- `role-compare` — 对比多个岗位的职责差异，避免 JD 同质化

**HR + 面试评估：**

- `interview-eval` — 基于面试记录生成结构化评估报告
- `question-bank` — 根据岗位能力模型生成面试问题清单
- `candidate-compare` — 多候选人能力矩阵对比，辅助决策

**HR + 员工沟通：**

- `hr-message` — 根据沟通场景生成得体的员工沟通话术
- `onboard-guide` — 基于岗位生成新员工入职指引文档
- `feedback-craft` — 为绩效反馈生成建设性沟通话术

**HR + 培训方案：**

- `training-plan` — 基于培训目标生成课程大纲和日程安排
- `course-outline` — 输入主题生成结构化课程框架
- `learning-path` — 为特定角色设计学习路径和资源推荐

**项目经理 + 周报/月报：**

- `project-report` — 基于项目进展要点生成周报/月报
- `status-update` — 把零散的进度信息整理为结构化状态更新
- `milestone-summary` — 里程碑完成后生成阶段总结报告

**项目经理 + 会议纪要：**

- `meeting-minutes` — 基于会议要点生成结构化会议纪要
- `action-tracker` — 从会议讨论中提取行动项和负责人
- `decision-log` — 记录关键决策的背景、方案对比和最终选择

**项目经理 + 风险评估：**

- `risk-register` — 基于项目描述识别潜在风险并生成风险登记表
- `issue-brief` — 为项目问题生成简报（影响范围→原因→建议方案）
- `contingency-plan` — 为已识别风险生成应急预案

**项目经理 + 跨部门沟通：**

- `stakeholder-email` — 根据沟通目的生成专业得体的邮件
- `escalation-doc` — 生成问题升级文档（现状→影响→需要的支持）
- `alignment-brief` — 为跨部门对齐会议生成背景简报

### Step 3.5: Skill 设计的关键数据

在用户选完 Skill 建议后、写 description 之前，分享几个关键数据帮助用户理解 Skill 设计的核心：

> 在开始写之前，分享几个写好 Skill 的关键数据：
>
> - **description 的黄金长度：1-2 句话（50-100字）**— 太短 AI 不知道干什么，太长 AI 抓不住重点
> - **执行步骤最佳数量：3-5 步** — 少于 3 步太简单（直接用 Claude 就行，不需要 Skill），多于 5 步容易跑偏
> - **SKILL.md 推荐行数：50-150 行** — 这个项目里 interview-write 是 131 行，learn 是 172 行
> - **一个好的 Skill 解决的是"重复性工作"** — 你每次都要做、每次流程差不多、但每次都要花时间的事

### Step 4: 亲手写 description

这是整个闯关中最重要的一步——你要亲手写一句话。

先展示范例：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📝 写 description 的技巧

看看第3关用过的 interview-write 的 description：

  "通过凯文·凯利式深度访谈挖掘用户故事，
   结合参考风格写出高质量公众号文章。"

它的特点：
  ✅ 一句话说清楚干什么
  ✅ 提到了关键方法（凯文·凯利式访谈）
  ✅ 明确了最终产出（公众号文章）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

然后使用 AskUserQuestion 提问：

```
现在轮到你了——用一句话描述你的 {skill-name} 能做什么：
```

- 我来写（选 Other 输入你的 description）
- 给我个参考，我再改（AI 先写一版初稿，你来修改）
- 帮我写（AI 根据前面的选择自动生成）

**处理逻辑：**

- **"我来写"**：用户会在 Other 中输入自己的 description，直接使用
- **"给我个参考，我再改"**：AI 根据角色+痛点+Skill 名称生成一版 description，展示给用户，再用 AskUserQuestion 问「直接用这个 / 我改一下（选 Other 输入修改版）」
- **"帮我写"**：AI 自动生成，告知用户"这是我帮你写的，你随时可以在 SKILL.md 里改"

记录最终确定的 description，后续生成 SKILL.md 时使用。

### Step 5: 设计决策 + 生成骨架

告诉用户：

> 接下来有两个设计决策，决定了你的 Skill 怎么运行。

**决策 1：** 使用 AskUserQuestion 提问：

```
你的 Skill 拿到用户输入后，第一步应该做什么？
```

- 先解析参数（判断用户给了文件还是文字，像 interview-write 一样）
- 直接开始执行（不需要额外参数，开箱即用）
- 先提问收集信息（像访谈一样，先问用户几个问题再开始）

**决策 2：** 使用 AskUserQuestion 提问：

```
最终输出用什么格式？
```

- Markdown 表格（结构化数据，适合对比分析类）
- 分段叙述（像写文章一样，适合报告和方案类）
- 清单 / Checklist（逐条列出，适合审查和待办类）
- 混合格式（表格+叙述组合）

根据以上所有选择（角色、痛点、Skill 名称、用户写的 description、两个设计决策），生成完整的 SKILL.md。

创建目录：

```bash
mkdir -p ./learning/my-first-skill
```

生成的 SKILL.md 应包含：

```yaml
---
name: { 用户选的名字 }
description: >-
  {用户亲手写的 description，如果用户选了"帮我写"则用 AI 生成的}
argument-hint: "{根据决策1推断的参数说明}"
allowed-tools: Read Write Edit Bash(ls)
---
```

正文根据两个设计决策编排：

1. 概述（角色定位，基于角色+痛点）
2. 执行流程（3-4 个步骤，第一步根据决策1选择，最后一步的输出格式根据决策2）
3. 解析 `$ARGUMENTS`（根据决策1）
4. 输出规范（根据决策2）

保存到 `./learning/my-first-skill/SKILL.md`。

### Step 6: 展示 + 你来改一处

在终端展示完整 SKILL.md：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📄 你的第一个 Skill
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

{展示 SKILL.md 全文}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

逐块讲解：

- frontmatter 各字段的作用（回顾第2关知识）
- 正文是如何指导 AI 执行的
- 你的两个设计决策是怎么体现在流程中的
- allowed-tools 为什么选了这几个

然后使用 AskUserQuestion 问：

```
看看你的 Skill，有没有想调整的地方？
```

- 改一下 description（重新写那句话）
- 调整执行步骤的顺序
- 加一条 Anti-Pattern（告诉 AI "不要做什么"）
- 就这样，挺好的

如果用户选了调整项，执行对应修改后重新展示。

### Step 7: 部署说明 + 模拟试跑

告知部署步骤：

> 想实际使用的话，两步就行：
>
> **第一步：复制到 skills 目录**
>
> ```bash
> cp -r ./learning/my-first-skill .claude/skills/{skill-name}
> ```
>
> **第二步：重启 Claude Code**
> 新增的 Skill 需要重新启动 Claude Code（关闭当前窗口再打开，或新开一个窗口）才能被识别。
> 重启后输入 `/{skill-name}` 就能用了！
>
> **注意：** 修改已有 Skill 的内容不需要重启，只有新增 Skill 目录时才需要。

然后模拟一次调用效果：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🎬 模拟试跑：如果你输入 /{skill-name} ...

> 用户输入：/{skill-name} {示例参数}

Skill 会按照你设计的流程执行：
  Step 1: {根据决策1} ...
  Step 2: {核心处理} ...
  Step 3: {输出结果，格式为决策2选择的格式} ...

最终你会得到一份 {产出描述}。
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

> 另外，项目里有模板可以参考：
>
> - `templates/basic/SKILL.md` — 最简骨架，快速上手
> - `templates/standard/SKILL.md` — 完整模板，含进阶结构
>
> 以后想创建新 Skill，可以从这些模板开始。

### Step 8: 展示到你的作品墙

使用 AskUserQuestion 提问：

```
要不要把你的作品展示到 index.html 的「我的作品」Tab 上？
```

- 好！帮我生成（AI 自动读取、解析、生成可视化卡片）
- 先跳过（直接进入通关结语）

**如果用户选"好！帮我生成"：**

执行以下步骤（全自动，不需要用户操作）：

1. **读取** `./learning/my-first-skill/SKILL.md`
2. **解析内容**：
   - YAML frontmatter：提取 `name`、`description`、`allowed-tools` 列表
   - 正文：统计编号列表的**数量**作为执行步骤数、表格行的**数量**作为边缘情况数、Anti-Pattern 标题下列表项的**数量**作为防护规则数
3. **生成 HTML 卡片**，使用 index.html 中已有的 CSS 类，模板如下：

```html
<div class="achievement-card">
  <div class="achievement-card-header">
    <span class="achievement-badge">SKILL</span>
    <h3>{name}</h3>
  </div>
  <p class="desc">{description}</p>
  <div class="achievement-tools">
    <div class="achievement-tool-badges">
      <span class="achievement-tool-badge">{每个工具一个 badge}</span>
    </div>
  </div>
  <div class="stats">
    <div class="stat"><strong>{步骤数}</strong>执行步骤</div>
    <div class="stat"><strong>{边缘情况数}</strong>边缘处理</div>
    <div class="stat"><strong>{反模式数}</strong>防护规则</div>
  </div>
  <div class="congrats">你创建了自己的第一个 Skill</div>
</div>
```

> 注意：stats 中的数字只统计数量，不列出具体内容。如果某项数量为 0，对应的 stat 仍然显示（显示 0）。

4. **用 Edit 工具**找到 `index.html` 中 `<!-- SKILL-SHOWCASE-START -->` 和 `<!-- SKILL-SHOWCASE-END -->` 之间的内容，替换为生成的卡片 HTML（放在 `<div class="achievement-cards">` 容器内）
5. **告知用户**：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🏆 已完成！

你的 Skill 已经可视化展示在 index.html 中了。
用浏览器打开 index.html，点击最后一个 Tab「我的作品」查看。
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## 验证

1. `./learning/my-first-skill/SKILL.md` 文件存在
2. 文件包含有效的 YAML frontmatter
3. frontmatter 中 `name` 字段存在且符合小写连字符格式
4. frontmatter 中 `description` 字段存在且非空
5. 文件总行数 > 10 行

全部通过 → 显示通关结语（由 SKILL.md 主编排处理）。
