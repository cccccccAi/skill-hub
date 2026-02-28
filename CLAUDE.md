# AI 技能工坊

产研团队的 AI 协作工具集，覆盖产品、设计、写作，内含闯关教学。

## 新用户引导

> **AI IDE（如 CodeBuddy）读取到此文件时：** 如果用户刚克隆了这个项目、还没有安装 Claude Code，请引导用户先按照 `learning/getting-started.md` 完成环境安装（只需 3 步）。安装完成后，指导用户在终端中输入 `claude` 启动 Claude Code。

> **Claude Code 启动后读取到此文件时：** 先确认 `.claude/skills/` 目录下的技能文件完整（应包含 pm、ui-ux-design、design-review、interview-write、interview-write-team、learn、learn-design、build-course 八个目录）。然后提示用户：「欢迎来到 AI 技能工坊！输入技能命令开始使用，或输入 `/learn` 开始闯关学习。」

## 按角色推荐

| 你的角色 | 推荐技能 | 一句话说明 |
|---------|---------|----------|
| 产品经理 | `/pm` | 写 PRD、用研分析、做竞品分析、排路线图、写汇报 |
| 设计师 | `/ui-ux-design` + `/design-review` | 生成设计系统 + 评审交付 |
| 运营/市场 | `/interview-write` | 深度访谈挖故事 → 写文章 |
| 想学 AI | `/learn` | 5 关闯关，从零学会创建 Skill |
| 想学设计 | `/learn-design` | 5 关设计闯关，无需编程基础 |

## 技能说明

| 技能 | 说明 |
|------|------|
| `/pm [需求描述]` | 产品工具箱：写 PRD、用研分析、写汇报、排路线图、竞品分析、数据复盘 |
| `/ui-ux-design [设计需求]` | 设计生成：需求分析 → BM25 搜索 → 设计系统（配色/字体/风格） |
| `/design-review [设计稿描述]` | 设计评审：评审反馈、开发交付文档、WCAG 无障碍审查、UX 文案 |
| `/interview-write [主题]` | 访谈写作：深度访谈 → 风格学习 → 写作 → 自动优化 |
| `/interview-write-team [主题]` | 团队写作：访谈 → 双写手对抗 → 评审 → 综合终稿 |
| `/learn [关卡编号]` | 闯关教学：5关从入门到创建自己的 Skill |
| `/learn-design [关卡编号]` | 设计教学：5关从认识工具到完成设计项目 |
| `/build-course [学习主题]` | 课程生成器：输入主题 → 设计5关课程 → 生成 Skill 文件 → 模拟审计 |

## 项目结构

```
skill-hub/
├── .claude/skills/              # 所有技能定义
│   ├── pm/                      # 产品工具箱（/pm）
│   ├── ui-ux-design/            # 设计系统生成（/ui-ux-design）
│   ├── design-review/           # 设计评审（/design-review）
│   ├── interview-write/         # 访谈写作（/interview-write）
│   ├── interview-write-team/    # 团队对抗写作（/interview-write-team）
│   ├── learn/                   # 闯关教学（/learn）
│   ├── learn-design/            # 设计闯关教学（/learn-design）
│   └── build-course/            # 课程生成器（/build-course）
├── design/                      # 设计工作空间
│   ├── engine/                  # BM25 搜索引擎 + CSV 数据库
│   │   ├── scripts/             # Python 搜索脚本
│   │   └── data/                # 68 风格 + 96 配色 + 57 字体 + 13 技术栈
│   └── output/                  # 设计系统输出（不入 git）
├── writing/                     # 写作工作空间
│   ├── examples/                # 风格参考文章（可替换为你自己的）
│   ├── drafts/                  # 中间产物（不入 git）
│   └── output/                  # 最终产出（不入 git）
├── templates/                   # Skill 模板骨架
│   ├── basic/                   # 最简模板（~15行）
│   └── standard/                # 标准模板（~35行，含进阶结构）
├── learning/                    # 学习工作空间
│   ├── getting-started.md       # 入门手册（新手看这个）
│   ├── setup-guide.md           # 完整安装指南（技术参考）
│   ├── progress.md              # 闯关进度（不入 git）
│   └── my-first-skill/          # 学员作品（不入 git）
├── tools/                       # 工具包（已迁移到独立仓库）
└── CLAUDE.md
```

## 路径约定

所有路径使用相对路径（相对于项目根目录）。写作相关路径以 `./writing/` 为前缀，设计相关路径以 `./design/` 为前缀。

## 写作风格规范

- **字数**：1000 字符以内（默认，可在 `.claude/skills/interview-write/references/style-guide.md` 中调整）
- **标题**：3 个备选，极其吸睛
- **前三行**：3 秒内抓住读者
- **金句**：加粗（`**`），每 50-80 字一个
- **风格参考**：写作前必须读取 `./writing/examples/` 中所有 `.md` 文件

## 自定义风格案例

`writing/examples/` 目录存放写作风格参考文章。写作 Skill 会从中学习写作风格（节奏、金句密度、开场方式等）。

**你应该替换为自己喜欢的文章：**
- 支持 `.md` 格式
- 建议放 3-5 篇能代表你想要风格的文章
- AI 学习的是风格和节奏，不是字数——参考文章可以比输出上限长
- 修改后立即生效，无需重启

## Skill 模板

想自己创建新 Skill？从模板开始：
- `templates/basic/SKILL.md` — 最简骨架，快速上手
- `templates/standard/SKILL.md` — 完整模板，含 references/、Anti-Pattern 等进阶结构
