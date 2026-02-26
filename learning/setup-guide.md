# Claude Code 环境安装指南（完整版）

> **新手推荐先看 [入门手册](getting-started.md)**，只需 3 步即可上手。本文档是详细技术参考。
>
> 本指南兼容 macOS 和 Windows，无需 Anthropic 账号。

---

## Step 0: 准备终端环境

### macOS

1. 打开 CodeBuddy（https://www.codebuddy.cn/）
2. 按 `Ctrl + ~` 或点击菜单「终端 → 新建终端」打开内置终端

### Windows

1. **先安装 Windows Terminal**：打开 Microsoft Store，搜索 "Windows Terminal"，点击安装。如果无法访问 Microsoft Store，可使用项目中预置的安装包（见下方说明）
2. 打开 CodeBuddy（https://www.codebuddy.cn/）
3. 按 `Ctrl + ~` 打开终端，确认终端类型是 **PowerShell**（不是 CMD）

> **备选方案：** 如果 Microsoft Store 不可用，在 CodeBuddy 中打开项目后，找到 `tools/windows/WindowsTerminal-v1.23-x64.zip`（64位系统）或 `WindowsTerminal-v1.23-x86.zip`（32位系统），解压后直接运行 `WindowsTerminal.exe` 即可使用。

> Windows 用户注意：如果 CodeBuddy 终端默认不是 PowerShell，点击终端右上角的下拉箭头切换。

---

## Step 1: 安装 Node.js 18+

Node.js 是运行 Claude Code 所需的基础工具。

### macOS

前往 https://nodejs.org → 点击下载 LTS 版本（.pkg 文件）→ 双击安装 → 一路点「继续」直到完成。

### Windows

前往 https://nodejs.org → 点击下载 LTS 版本（.msi 文件）→ 双击安装 → 安装时**勾选 "Add to PATH"** → 一路点「Next」直到完成。

### 验证

安装完成后，在终端输入：

```bash
node -v
```

看到 `v18.x.x` 或更高版本号即成功。如果提示"命令未找到"，请**关闭并重新打开终端**再试。

---

## Step 2: 安装 Claude Code

### macOS

在终端运行：

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

### Windows（PowerShell）

在终端运行：

```powershell
irm https://claude.ai/install.ps1 | iex
```

### 验证

```bash
claude --version
```

看到版本号即成功。

**暂时不要运行 `claude`**，先完成下一步配置模型。

---

## Step 3: 安装 cc-switch 并配置模型

cc-switch 是一个模型切换工具，让你可以使用 Qwen 等国产大模型来驱动 Claude Code。

### 4a. 安装 cc-switch

安装包已预置在仓库的 `tools/` 目录中，可直接使用：

#### macOS

解压 `tools/macos/CC-Switch-v3.10.3-macOS.zip`（Finder 中双击即可解压），将 CC-Switch 拖入「应用程序」文件夹。

首次打开可能提示「无法验证开发者」：
- 关闭提示
- 打开「系统设置 → 隐私与安全」
- 往下滚动找到 CC-Switch 的提示，点击「仍要打开」

> 也可用 Homebrew 安装：`brew tap farion1231/ccswitch && brew install --cask cc-switch`

#### Windows

运行 `tools/windows/CC-Switch-v3.10.3-Windows.msi`，按提示完成安装。

### 4b. 配置模型

1. 启动 cc-switch 应用
2. 点击 **"Add Provider"**
3. 选择模型提供商
4. 点击 **"Enable"**
5. **关闭并重新打开 CodeBuddy 终端**

---

## Step 4: 验证环境

在终端依次运行以下命令：

```bash
node -v          # 应看到 v18+
claude --version # 应看到版本号
```

全部通过即可进入下一步。

---

## Step 5: 启动 Claude Code 并开始学习

### 6a. 打开终端并进入项目目录

在 CodeBuddy 终端中，确保当前在 skill-hub 项目目录下：

```bash
cd skill-hub    # 如果还没在项目目录中
```

### 6b. 启动 Claude Code

```bash
claude
```

首次启动可能需要几秒钟。看到 Claude Code 的交互界面说明启动成功。

### 6c. 开始闯关学习

Claude Code 启动后，它会自动读取项目信息。输入以下命令开始学习：

```
/learn
```

这将启动 5 关闯关教学，从零学会使用 Claude Code Skills。

---

## 环境验证清单

完成以上所有步骤后，确认以下项目全部通过：

- [ ] CodeBuddy 已安装，终端可用
- [ ] Node.js 18+（`node -v` 通过）
- [ ] Claude Code（`claude --version` 通过）
- [ ] cc-switch 已配置模型
- [ ] `claude` 可正常启动，`/learn` 可以运行

---

## 常见问题

| 问题 | 解决 |
|------|------|
| Windows 上 `irm` 命令报错 | 确认使用 **PowerShell** 而不是 CMD，建议先安装 Windows Terminal |
| macOS 上 `curl` 命令报错 | 重启终端，或在 CodeBuddy 中新建一个终端窗口 |
| `claude` 启动后无法对话 | 确认 cc-switch 中已经 Enable 了模型 |
| cc-switch 打不开（macOS） | 系统设置 → 隐私与安全 → 点「仍要打开」 |
| Windows 终端显示乱码 | 使用 Windows Terminal，不要用默认 CMD |
