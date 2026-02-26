# AI 技能工作空间

基于 Agent Skills 开放标准的多技能系统，通过 Claude Code 驱动。

## 项目结构

```
skill-hub/
├── .claude/skills/              # 所有技能定义
│   ├── interview-write/         # 单人访谈写作（/interview-write）
│   ├── interview-write-team/    # 团队对抗写作（/interview-write-team）
│   └── learn/                   # 闯关式交互教学（/learn）
├── writing/                     # 写作工作空间
│   ├── examples/                # 风格参考文章（可自定义）
│   ├── drafts/                  # 中间产物（不入 git）
│   └── output/                  # 最终发布的文章
├── learning/                    # 学习工作空间
│   ├── setup-guide.md           # 环境安装指南
│   ├── progress.md              # 闯关进度（不入 git）
│   └── my-first-skill/          # 学员作品（不入 git）
└── CLAUDE.md
```

## 路径约定

所有路径使用相对路径（相对于项目根目录）。写作相关路径以 `./writing/` 为前缀。

## 技能说明

| 技能 | 说明 |
|------|------|
| `/interview-write [主题]` | 单人模式：访谈 → 写作 → 自动优化 |
| `/interview-write-team [主题]` | 团队模式：访谈 → 双写手对抗 → 评审 → 综合终稿 |
| `/learn [关卡编号]` | 闯关教学：5关从入门到创建自己的 Skill |

## 写作风格规范

- **字数**：1000 字符以内（硬性要求）
- **标题**：3 个备选，极其吸睛
- **前三行**：3 秒内抓住读者
- **金句**：加粗（`**`），每 50-80 字一个
- **风格参考**：写作前必须读取 `./writing/examples/` 中所有 `.md` 文件

## 自定义风格案例

`writing/examples/` 目录存放写作风格参考文章。写作 Skill 在生成文章前会读取这些案例来学习风格。

你可以替换或新增自己喜欢的文章作为参考：
- 支持 `.md` 格式
- 建议放 3-5 篇能代表你想要风格的文章
- 修改后立即生效，无需重启
