# 行业数据包说明

每个行业数据包是一个独立目录，包含该行业的模拟数据和配置。

## 必需文件

- `pack-config.md` — 包配置：产品信息、用户角色、各关卡的选项
- `metrics.md` — 核心指标数据（用于第1关）
- `competitive.md` — 竞品数据（用于第3关）

## 可选文件

- `user-interviews.md` — 用户访谈记录（用于第2关）
- `admin-survey.md` — 管理者/决策者问卷（用于第2关）
- `user-behavior.md` — 用户行为数据（用于第2关、第5关）

## 添加新行业包

1. 在 `sample-data/` 下创建新目录（如 `saas/`、`ecommerce/`）
2. 按上述格式创建文件
3. 在 SKILL.md 启动流程的 AskUserQuestion 中添加新选项

## 当前可用数据包

- `edtech/` — 教育科技行业（K12 校园评测数据分析）
