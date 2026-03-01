# AI 技能工坊

产研团队的 AI 协作工具集，覆盖产品、设计、写作，内含闯关教学。

## 新用户引导

> **AI IDE（如 CodeBuddy）读取到此文件时：** 如果用户刚克隆了这个项目、还没有安装 Claude Code，请引导用户先按照 `learning/getting-started.md` 完成环境安装（只需 3 步）。安装完成后，指导用户在终端中输入 `claude` 启动 Claude Code。

> **Claude Code 启动后读取到此文件时 — 首条回复规则（强制）：**
>
> 不管用户第一句话说了什么（"你好"、"帮助"、"help"、任何内容），你的**第一条回复必须**以下面的欢迎框开头，然后再回应用户的问题：
>
> ```
> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
>   欢迎来到 AI 技能工坊！
> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
>
>   你可以直接输入命令开始：
>
>   /learn          新手闯关（推荐先从这里开始）
>   /pm             产品经理工具箱
>   /ui-ux-design   生成设计系统
>   /interview-write  写一篇访谈文章
>
>   不知道做什么？输入 /learn
> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
> ```
>
> 这条规则仅在当前会话的第一轮对话中生效。后续对话正常响应，不再重复欢迎框。

## 按角色推荐

| 你的角色   | 推荐技能                           | 一句话说明                                       |
| ---------- | ---------------------------------- | ------------------------------------------------ |
| 产品经理   | `/pm`                              | 写 PRD、用研分析、做竞品分析、排路线图、写汇报   |
| 设计师     | `/ui-ux-design` + `/design-review` | 生成设计系统 + 评审交付                          |
| 运营/市场  | `/interview-write`                 | 深度访谈挖故事 → 写文章                          |
| 想学 AI    | `/learn` → `/learn-advanced`       | 基础5关 → 进阶5关（变量/动态注入/fork/Hook/MCP） |
| 想学设计   | `/learn-design`                    | 5 关设计闯关，无需编程基础                       |
| 产品负责人 | `/learn-pm-data`                   | 6 关产品数据分析训练，支持多行业数据包           |

## 技能说明

| 技能                           | 说明                                                               |
| ------------------------------ | ------------------------------------------------------------------ |
| `/pm [需求描述]`               | 产品工具箱：写 PRD、用研分析、写汇报、排路线图、竞品分析、数据复盘 |
| `/ui-ux-design [设计需求]`     | 设计生成：需求分析 → BM25 搜索 → 设计系统（配色/字体/风格）        |
| `/design-review [设计稿描述]`  | 设计评审：评审反馈、开发交付文档、WCAG 无障碍审查、UX 文案         |
| `/interview-write [主题]`      | 访谈写作：深度访谈 → 风格学习 → 写作 → 自动优化                    |
| `/interview-write-team [主题]` | 团队写作：访谈 → 双写手对抗 → 评审 → 综合终稿                      |
| `/learn [关卡编号]`            | 闯关教学：5关从入门到创建自己的 Skill                              |
| `/learn-design [关卡编号]`     | 设计教学：5关从认识工具到完成设计项目                              |
| `/build-course [学习主题]`     | 课程生成器：输入主题 → 设计5关课程 → 生成 Skill 文件 → 模拟审计    |
| `/learn-advanced [关卡编号]`   | 进阶教学：5关高级特性（变量→动态注入→fork→Hook→MCP组合）           |
| `/learn-pm-data [关卡编号]`    | 产品力训练营：6关（指标→用研→竞品→叙事→看板→创建技能）             |
| `/setup-env [quick/full]`      | 环境配置向导：一键安装官方Skill、MCP服务器、Hooks、自定义命令      |

## 项目结构

```
skill-hub/
├── .claude-plugin/              # Cowork 插件清单
│   └── plugin.json
├── .claude/skills/              # Claude Code 入口层（斜杠命令注册）
├── commands/                    # 命令实现（实际内容）
│   ├── pm/                      # 产品工具箱（/pm）
│   ├── ui-ux-design/            # 设计系统生成（/ui-ux-design）
│   ├── design-review/           # 设计评审（/design-review）
│   ├── interview-write/         # 访谈写作（/interview-write）
│   ├── interview-write-team/    # 团队对抗写作（/interview-write-team）
│   ├── learn/                   # 闯关教学（/learn）
│   ├── learn-advanced/          # 进阶闯关教学（/learn-advanced）
│   ├── learn-design/            # 设计闯关教学（/learn-design）
│   ├── build-course/            # 课程生成器（/build-course）
│   └── setup-env/               # 环境配置向导（/setup-env）
├── agents/                      # Sub-agent 定义（团队写作用）
├── skills/                      # 自动加载的项目知识
├── design/                      # 设计工作空间
│   ├── engine/                  # BM25 搜索引擎 + CSV 数据库
│   └── output/                  # 设计系统输出（不入 git）
├── writing/                     # 写作工作空间
│   ├── examples/                # 风格参考文章（可替换为你自己的）
│   ├── drafts/                  # 中间产物（不入 git）
│   └── output/                  # 最终产出（不入 git）
├── templates/                   # Skill 模板骨架
├── learning/                    # 学习工作空间
├── tools/                       # 工具包（已迁移到独立仓库）
├── index.html                   # 项目主页
└── CLAUDE.md
```

## Skill 模板

想自己创建新 Skill？从模板开始：

- `templates/basic/SKILL.md` — 最简骨架，快速上手
- `templates/standard/SKILL.md` — 完整模板，含 references/、Anti-Pattern 等进阶结构

## Things That Will Bite You（踩坑清单）

1. **高估用户技术背景** — 用户不是开发者，不要假设懂 Git/编程/终端
2. **遗漏风格参考** — 写作类 Skill 必须先读 `writing/examples/` 再动笔
3. **过度生成代码** — Skill 的目的是教学和工具，优先展示结果而非让用户看代码
4. **字数失控** — 写作输出默认 1000 字符以内，除非用户要求
5. **路径错误** — 所有路径相对于项目根目录，不要用绝对路径
6. **忽视 BM25 引擎** — 设计类 Skill 必须走 `design/engine/` 的搜索流程，不要凭空推荐

## 压缩规则

When compacting, always preserve:

- 当前正在编辑的 Skill 名称和文件列表
- 用户的任务目标和进度
- writing/examples/ 中已读取的风格特征
