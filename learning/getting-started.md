# Skill-Hub 入门手册

> 只需 4 步人工操作，剩下的全部交给 AI。

---

## 你需要准备

- 一台电脑（macOS 或 Windows）
- 稳定的网络连接
- 预留约 1.5 小时（安装 30 分钟 + 闯关学习 60 分钟）

---

## 你只需要做 4 件事

以下是**必须你亲手完成**的步骤。为什么 AI 不能帮你做？因为这些都是"下载软件并安装到电脑上"的操作，AI 目前无法操作你的浏览器和系统安装器。

---

### 第 1 步：安装 CodeBuddy

CodeBuddy 是你的 AI 编程助手，后续所有操作都在里面完成。

1. 打开 https://www.codebuddy.cn/
2. 下载对应系统版本
3. 双击安装，一路确认即可

> 装好 CodeBuddy，你就有了一个 AI 搭档。

---

### 第 2 步：安装 Node.js

Node.js 是 Claude Code 运行所需的基础环境。

1. 打开 https://nodejs.org
2. 点击下载 **LTS 版本**（页面上最醒目的绿色按钮）
3. 双击安装：
   - **macOS**：双击 `.pkg` 文件，一路点「继续」
   - **Windows**：双击 `.msi` 文件，注意**勾选 "Add to PATH"**，一路点「Next」

> 安装完可能需要重启 CodeBuddy 终端才能生效，后面 AI 会帮你验证。

---

### 第 3 步：安装 cc-switch

cc-switch 是模型切换工具，让你可以使用国产大模型驱动 Claude Code。

安装包已经预置在项目中（后面 AI 帮你克隆代码后就能看到），位于 `tools/` 目录：

**macOS：**
1. 找到 `tools/macos/CC-Switch-v3.10.3-macOS.zip`
2. 双击解压，将 CC-Switch 拖入「应用程序」文件夹
3. 首次打开会提示"无法验证开发者"→ 打开「系统设置 → 隐私与安全」→ 点「仍要打开」

**Windows：**
1. 找到 `tools/windows/CC-Switch-v3.10.3-Windows.msi`
2. 双击运行，按提示完成安装

---

### 第 4 步：配置模型

启动 cc-switch 应用，配置你的模型提供商。

<!--
TODO: 用户补充以下内容：
1. cc-switch 操作截图（Add Provider → 选择提供商 → Enable）
2. API Key 获取步骤和截图
-->

1. 打开 cc-switch 应用
2. 点击 **"Add Provider"**
3. 选择模型提供商
4. 填入 API Key
5. 点击 **"Enable"**

> 配置完成后，记得**关闭并重新打开 CodeBuddy 的终端**，让配置生效。

---

## 剩下的，交给 AI！

完成上面 4 步后，打开 CodeBuddy，在 AI 对话框中发送：

```
请帮我完成 Skill-Hub 的环境配置：
1. 克隆代码仓库 https://github.com/cccccccAi/skill-hub.git
2. 安装 Claude Code
3. 验证所有工具是否安装成功
4. 告诉我怎么启动学习
```

AI 会自动帮你完成：

- ✅ 克隆项目代码到本地
- ✅ 在终端安装 Claude Code（只需你按一下回车）
- ✅ 逐项验证 Node.js、Claude Code 等是否安装成功
- ✅ 告诉你接下来该做什么

全部就绪后，在终端输入：

```bash
cd skill-hub
claude
```

进入 Claude Code 后，输入：

```
/learn
```

开始 5 关闯关学习！从此刻起，AI 就是你的教练。

---

## 常见问题

| 问题 | 解决方法 |
|------|---------|
| Node.js 安装后终端识别不了 | 关闭终端，重新打开一个新的 |
| cc-switch 打不开（macOS） | 系统设置 → 隐私与安全 → 往下找到 CC-Switch → 点「仍要打开」 |
| `claude` 启动后无法对话 | 确认 cc-switch 中已 Enable 模型，并重新打开了终端 |
| Windows 终端显示乱码 | 安装 Windows Terminal（在项目 `tools/windows/` 中有安装包），或从 Microsoft Store 搜索安装 |
| 不确定哪一步出了问题 | 把错误信息发给 CodeBuddy AI，让它帮你诊断 |

---

## 完整技术文档

如果你是技术用户，或想查看每一步的详细操作说明，请参考 [完整安装指南](setup-guide.md)。
