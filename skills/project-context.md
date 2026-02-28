# AI 技能工坊 — 项目上下文

产研团队的 AI 协作工具集，覆盖产品、设计、写作，内含闯关教学。

## 按角色推荐

| 你的角色  | 推荐技能                           | 一句话说明                                     |
| --------- | ---------------------------------- | ---------------------------------------------- |
| 产品经理  | `/pm`                              | 写 PRD、用研分析、做竞品分析、排路线图、写汇报 |
| 设计师    | `/ui-ux-design` + `/design-review` | 生成设计系统 + 评审交付                        |
| 运营/市场 | `/interview-write`                 | 深度访谈挖故事 → 写文章                        |
| 想学 AI   | `/learn`                           | 5 关闯关，从零学会创建 Skill                   |
| 想学设计  | `/learn-design`                    | 5 关设计闯关，无需编程基础                     |

## 路径约定

所有路径使用相对路径（相对于项目根目录）：

- 写作相关：`./writing/`（examples/ 风格参考、drafts/ 中间产物、output/ 最终产出）
- 设计相关：`./design/`（engine/ 搜索引擎、output/ 设计输出）
- 学习相关：`./learning/`（进度、作品、教程资料）

## 项目结构

```
skill-hub/
├── .claude-plugin/              # Cowork 插件清单
├── .claude/skills/              # Claude Code 入口层
├── commands/                    # 命令实现（实际内容）
│   ├── pm/                      # 产品经理工具箱
│   ├── ui-ux-design/            # 设计系统生成
│   ├── design-review/           # 设计评审
│   ├── interview-write/         # 访谈写作
│   ├── interview-write-team/    # 团队对抗写作
│   ├── learn/                   # 闯关教学
│   ├── learn-design/            # 设计闯关教学
│   └── build-course/            # 课程生成器
├── agents/                      # Sub-agent 定义
├── skills/                      # 自动加载知识
├── design/engine/               # BM25 搜索引擎 + CSV 数据库
├── writing/                     # 写作工作空间
├── learning/                    # 学习工作空间
├── templates/                   # Skill 模板
└── tools/                       # 工具仓库链接
```
