# Claude Code 极简速查

> 面向非开发人员的最精简操作指南

## 启动和恢复

```bash
claude                    # 启动
claude "你的问题"          # 带问题启动
claude -p "你的问题"       # 问完即走，不进入对话
claude -c                 # 恢复上次对话（终端关了用这个）
claude -r                 # 选择历史对话恢复
```

## 对话中常用命令

```bash
/help                     # 查帮助
/clear                    # 清空重来
/compact                  # 聊太久AI忘事了，压缩一下
/copy                     # 复制AI最后一条回复
/rename 周报              # 给对话取名，方便下次找
/exit                     # 退出
```

## 快捷键

```bash
Ctrl+C                    # 打断AI回答
Ctrl+D                    # 退出
Shift+Tab                 # 切换权限模式（普通/自动同意/只读）
Esc 按两下                 # 撤回上一步
@文件名                    # 引用文件给AI看
!git status               # 直接跑终端命令（前面加感叹号）
```

## 权限模式

```bash
claude --permission-mode plan          # 只读模式（只分析不动代码）
claude --permission-mode acceptEdits   # 自动同意模式（省得反复确认）
```

## 退出 Vim（万一进去了）

```
Esc → 输入 :q! → 回车
```

## 日志/文件丢给AI分析

```bash
cat error.log | claude -p "帮我分析报错原因"
```

---

> 记住三条就够：`claude` 启动，`claude -c` 恢复，进了 Vim 按 `Esc` 打 `:q!` 回车
