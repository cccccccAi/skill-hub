# Skill Hub — AI 技能工坊

产研团队的 AI 协作工具集，覆盖产品、设计、写作，内含闯关教学。

基于 [Agent Skills](https://agentskills.io) 开放标准，通过 Claude Code 驱动。

## 技能索引

| 技能 | 说明 | 适合角色 |
|------|------|---------|
| `/pm [需求]` | 产品经理工具箱：写 PRD、用研分析、汇报、路线图、竞品分析 | 产品经理 |
| `/ui-ux-design [需求]` | 设计系统生成：BM25 搜索 → 配色/字体/风格方案 | 设计师 |
| `/design-review [设计稿]` | 设计评审：评审反馈、开发交付、无障碍审查、UX 文案 | 设计师 |
| `/interview-write [主题]` | 访谈写作：深度访谈 → 风格学习 → 写作 → 自动优化 | 运营/市场 |
| `/interview-write-team [主题]` | 团队写作：访谈 → 双写手对抗 → 评审 → 综合终稿 | 运营/市场 |
| `/learn [关卡]` | 闯关教学：5 关从入门到创建自己的 Skill | 全员 |
| `/learn-design [关卡]` | 设计教学：5 关从认识工具到完成设计项目 | 设计师 |
| `/build-course [主题]` | 课程生成器：输入主题 → 自动生成闯关课程 | 培训负责人 |

## 快速开始

**第一步：** 用浏览器打开项目中的 [`index.html`](index.html)，了解项目全貌。

新手也可以看 [`learning/getting-started.md`](learning/getting-started.md)（入门手册），只需 3 步。

```bash
git clone https://github.com/cccccccAi/skill-hub.git
cd skill-hub
claude

# 产品经理
/pm 写一个会员系统的 PRD

# 设计师
/ui-ux-design SaaS 仪表盘 深色模式
/design-review 评审我们的登录页设计

# 运营
/interview-write 我最近的创业故事

# 学习
/learn
```

## 详细文档

项目配置、技能说明、模板使用等详见 [`CLAUDE.md`](CLAUDE.md)。
