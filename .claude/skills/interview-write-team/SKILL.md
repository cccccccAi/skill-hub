---
name: interview-write-team
description: >-
  多 Agent 协作写作团队。深度访谈 → 双写手对抗写作（悬念派 vs 洞察派）→
  6维度评审 → Team Lead 综合终稿。支持素材文件跳过访谈直接写作。
argument-hint: "[主题或文件路径]"
disable-model-invocation: true
allowed-tools: Read Write Edit Bash(ls) Bash(mkdir)
---

读取 commands/interview-write-team/interview-write-team.md 获取完整执行流程。
Agent prompt 文件在 agents/ 目录下（interviewer.md、writer-suspense.md、writer-insight.md、critic.md）。
写作规范见 commands/interview-write/style-guide.md。
