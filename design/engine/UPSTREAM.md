# 上游信息

- **仓库**: https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- **同步版本**: main@d820991781d4bdb8e2b2ee40f12442a5002c2b97
- **同步日期**: 2026-02-28
- **同步范围**: `src/ui-ux-pro-max/data/` + `src/ui-ux-pro-max/scripts/`
- **License**: MIT

## 更新方法

```bash
# 1. 克隆最新版本
git clone --depth 1 https://github.com/nextlevelbuilder/ui-ux-pro-max-skill.git /tmp/uipro-update

# 2. 覆盖数据和脚本
cp /tmp/uipro-update/src/ui-ux-pro-max/data/*.csv ./design/engine/data/
cp /tmp/uipro-update/src/ui-ux-pro-max/data/stacks/*.csv ./design/engine/data/stacks/
cp /tmp/uipro-update/src/ui-ux-pro-max/scripts/*.py ./design/engine/scripts/

# 3. 重新添加 sys.path 防御（search.py 头部）
# 4. 更新本文件的版本和日期
# 5. 清理
rm -rf /tmp/uipro-update
```
