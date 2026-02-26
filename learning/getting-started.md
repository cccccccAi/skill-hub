# Skill-Hub 入门手册

> 只需 3 步，剩下的交给 AI。

---

## 你需要准备

- 一台电脑（macOS 或 Windows）
- 稳定的网络连接
- 预留约 1.5 小时（安装 30 分钟 + 闯关学习 60 分钟）

---

## 第 1 步：安装 CodeBuddy，获取项目代码

CodeBuddy 是你的 AI 编程助手，后续所有操作都在它里面完成。

### 1.1 安装 CodeBuddy

1. 打开 https://www.codebuddy.cn/
2. 下载对应系统版本，双击安装

### 1.2 克隆项目代码

1. 打开 CodeBuddy
2. 点击「克隆 Git 仓库」（或菜单中的 Clone Repository）
3. 输入地址：`https://github.com/cccccccAi/skill-hub.git`
4. 选择一个文件夹保存，等待下载完成

### 1.3 让 AI 帮你安装依赖

项目打开后，在 CodeBuddy 的 AI 对话框中发送：

```
请阅读项目说明，帮我安装 Claude Code 及所有相关依赖。
```

AI 会自动帮你：
- ✅ 阅读项目文档，了解需要安装什么
- ✅ 引导你安装 Node.js（需要你去网站下载，AI 会给你链接和步骤）
- ✅ 在终端安装 Claude Code
- ✅ 引导你安装 cc-switch（从项目 `tools/` 目录中找到安装包）
- ✅ 验证所有工具是否安装成功

> 跟着 AI 的提示一步步操作即可，遇到问题直接问它。

---

## 第 2 步：配置模型

cc-switch 安装完成后，需要配置模型才能使用。

<!--
TODO: 用户补充以下内容：
1. cc-switch 操作截图（Add Provider → 选择提供商 → Enable）
2. API Key 配置信息
-->

1. 打开 cc-switch 应用
2. 按照下方提供的配置信息，复制粘贴 API 配置
3. 点击 **"Enable"**
4. **关闭并重新打开 CodeBuddy 的终端**，让配置生效

---

## 第 3 步：启动 Claude Code，开始学习

在 CodeBuddy 终端中输入：

```bash
cd skill-hub
claude
```

进入 Claude Code 后，它会自动读取项目信息。告诉它：

```
请熟悉一下这个项目，然后带我开始 /learn 技能的学习。
```

或者直接输入：

```
/learn
```

从此刻起，AI 就是你的教练，带你完成 5 关闯关学习！

---

## 常见问题

| 问题 | 解决方法 |
|------|---------|
| cc-switch 打不开（macOS） | 系统设置 → 隐私与安全 → 往下找到 CC-Switch → 点「仍要打开」 |
| `claude` 启动后无法对话 | 确认 cc-switch 中已 Enable 模型，并重新打开了终端 |
| Windows 终端显示乱码 | 安装 Windows Terminal（项目 `tools/windows/` 中有安装包） |
| 遇到任何报错 | 把错误信息发给 CodeBuddy AI 或 Claude Code，让它帮你诊断 |

---

## 完整技术文档

技术用户可参考 [完整安装指南](setup-guide.md) 查看每一步的详细操作说明。
