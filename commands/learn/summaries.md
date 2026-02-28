# 每关通关总结

每关验证通过后，按照通关总结协议执行：通关提示 → 验证题 → 要点 → 过渡选择（含可选原理图）。

---

## 第1关：认识项目

### 验证题

「CLAUDE.md 的作用是什么？」

- 项目说明书，Claude Code 启动时自动读取 ← 正确
- 代码配置文件
- 用户手册
- 日志文件

答对反馈：「没错！CLAUDE.md 就是项目的说明书，Claude Code 每次启动都会读它。」
答错反馈：「CLAUDE.md 是项目的入口说明书，Claude Code 每次启动都会自动读取，告诉 AI 这个项目是什么、有哪些 Skill。」

### 学习要点

✅ skill-hub 目录结构：skills 定义、writing 工作空间、learning 学习空间
✅ CLAUDE.md 是项目的入口说明书，Claude Code 每次启动都会读取

### 原理图（用户选择查看时展示）

```
项目结构的设计逻辑：

  .claude/skills/   → 技能定义（Claude Code 会自动扫描这里）
  writing/           → 技能的工作空间（输入输出都在这里）
  learning/          → 你的学习空间
  templates/         → Skill 模板（创建新 Skill 的起点）
  CLAUDE.md          → 项目说明书（Claude Code 每次启动都读）
```

---

## 第2关：理解结构

### 验证题

无（第2关自带 3 道验证题，不再重复）

### 学习要点

✅ SKILL.md = frontmatter（元数据）+ 正文（执行流程）
✅ name 决定调用方式（/name），allowed-tools 控制权限边界
✅ 复杂内容可拆到独立文件（references/ 子目录或 commands/ 目录）

### 原理图（用户选择查看时展示）

```
当你输入 /interview-write 时，发生了什么：

  用户输入 /skill-name
        ↓
  Claude Code 扫描 .claude/skills/ 下所有子目录
        ↓
  找到 frontmatter 中 name 匹配的 SKILL.md
        ↓
  加载 SKILL.md 作为 Agent 的指令
        ↓
  按 allowed-tools 限制可用工具
        ↓
  执行正文中定义的流程
```

---

## 第3关：实战写作

### 验证题

「Skill 是怎么学习你的写作风格的？」

- 读取 writing/examples/ 中的参考文章 ← 正确
- 联网搜索你的历史文章
- 你手动设置风格参数
- 从 CLAUDE.md 中读取

答对反馈：「对！examples/ 里放你喜欢的文章，AI 就会学习那种风格来写作。」
答错反馈：「AI 通过读取 writing/examples/ 里的参考文章来学习写作风格——放进去你喜欢的文章，下次写作就会用那种风格。」

### 学习要点

✅ Skill 完整生命周期：调用 → 执行 → 产出文件
✅ 风格参考（examples/）让 AI 学习特定写作风格

### 原理图（用户选择查看时展示）

```
/interview-write 的执行流程：

  Phase 1: 开场
    解析你传入的主题
        ↓
  Phase 2: 深度访谈
    通过提问收集你的故事素材
    实时保存到 drafts/interview-transcript.md
        ↓
  Phase 3: 判断终止
    素材足够时提议结束访谈
        ↓
  Phase 4: 学习风格
    读取 examples/ 中的参考文章
        ↓
  Phase 5: 写作
    结合素材+风格，生成文章
        ↓
  Phase 6: 自动优化
    检查金句密度、开头张力、字数
        ↓
  保存到 writing/output/
```

---

## 第4关：团队模式

### 验证题

「团队模式和单人模式最大的区别是？」

- Agent 数量多
- 不同视角对抗后融合，质量更高 ← 正确
- 速度更快
- 不需要访谈

答对反馈：「没错！团队模式的核心价值是多视角碰撞，不是简单的人多力量大。」
答错反馈：「团队模式的价值在于不同视角的对抗和融合——两个写手用不同风格写，Critic 评审后综合优点，产出比单一视角更有深度。」

### 学习要点

✅ 单人 vs 团队：多视角对抗后融合，质量更高
✅ 4 Agent 分工：Interviewer / Writer A / Writer B / Critic

### 原理图（用户选择查看时展示）

```
单人模式                         团队模式
┌──────────────┐          ┌─────────────────────────────┐
│              │          │                             │
│  一个 Agent   │          │  Interviewer → 访谈素材      │
│  全流程完成   │    vs     │  Writer A (悬念派) ──┐       │
│              │          │  Writer B (洞察派) ──┤→ Critic│
│              │          │                    └→ 终稿  │
└──────────────┘          └─────────────────────────────┘

关键差异：
  单人 → 一个人的视角，风格统一
  团队 → 多视角碰撞，取各家之长，质量更高
```

---

## 第5关：创建 Skill

### 验证题

「创建 Skill 后，放在哪个目录才能被 /name 调用？」

- .claude/skills/name/ ← 正确
- learning/
- templates/
- writing/

答对反馈：「完全正确！.claude/skills/ 是 Claude Code 扫描技能的地方。」
答错反馈：「Skill 需要放在 .claude/skills/你的skill名/ 目录下，Claude Code 启动时会自动扫描这个目录。」

### 学习要点

✅ 创建 Skill 的完整流程：确定需求 → 写 SKILL.md → 放到 .claude/skills/
✅ frontmatter 三要素：name + description + allowed-tools

### 原理图（用户选择查看时展示）

```
创建一个 Skill 只需要 3 步：

  1. 确定需求
     你要解决什么问题？用在什么场景？
        ↓
  2. 写 SKILL.md
     frontmatter: name + description + allowed-tools
     正文: 执行流程（Step 1, 2, 3...）
        ↓
  3. 放到正确位置
     .claude/skills/你的skill名/SKILL.md
        ↓
  完成！输入 /你的skill名 即可使用
```
