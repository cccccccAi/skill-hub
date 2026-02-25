# 新建技能仓库指南

## 步骤

### 1. 创建 GitHub 仓库

- 仓库名：`skill-{英文域名}`（如 `skill-mao-research`）
- 可见性：根据需要选择 Public 或 Private

### 2. 克隆并初始化结构

```bash
cd ~/AI
git clone git@github.com:cccccccAi/skill-{domain}.git
cd skill-{domain}

# 复制模板文件
mkdir -p .claude/skills/{skill-name} eg 输出
cp ~/AI/skill-hub/templates/settings.json .claude/
cp ~/AI/skill-hub/templates/gitignore.template .gitignore
```

### 3. 编写 CLAUDE.md

参考 `templates/CLAUDE.template.md`，填写领域特定内容：
- 团队名称和描述
- 技能列表和触发词
- 领域规范（方法论、输出格式等）
- 团队模式下的文件所有权分配

### 4. 编写 SKILL.md

在 `.claude/skills/{skill-name}/SKILL.md` 中定义技能：

```yaml
---
name: {skill-name}
description: "{技能描述}"
license: Proprietary
---
```

关键要素：
- 静默执行协议（避免不必要的确认提问）
- 清晰的执行流程（Phase 1 → Phase 2 → ...）
- 文件读写路径（使用相对路径）
- 边缘情况处理
- Anti-Pattern 列表

### 5. 添加参考素材

将领域参考材料放入 `eg/` 目录（.md 格式为佳）。

### 6. 提交并推送

```bash
git add -A
git commit -m "初始化 skill-{domain} 技能仓库"
git push -u origin main
```

### 7. 更新 skill-hub 索引

编辑 `skill-hub/README.md`，在技能索引表中添加新仓库。

## 检查清单

- [ ] GitHub 仓库已创建（`skill-{domain}`）
- [ ] `.claude/settings.json` 已配置
- [ ] `.gitignore` 已就位
- [ ] `CLAUDE.md` 已编写（含领域规范）
- [ ] `.claude/skills/{name}/SKILL.md` 至少一个技能
- [ ] `eg/` 目录有参考素材
- [ ] 技能触发测试通过
- [ ] `skill-hub/README.md` 索引已更新
