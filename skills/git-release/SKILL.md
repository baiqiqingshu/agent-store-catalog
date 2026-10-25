---
name: git-release
description: Guide a small service repo through a tagged release with changelog and rollback notes.
---

# Git 发布助手

当用户要求为一个服务仓库做版本发布时：

1. 确认当前分支与待发布 commit，检查工作区是否干净。
2. 依据最近提交归纳变更，写入 CHANGELOG 条目。
3. 建议语义化版本号并创建带注释的 tag。
4. 输出回滚提示：记录上一个 tag 与镜像摘要。
5. 发布后对照 knowledge/release-checklist.md 的检查单逐项确认。

此示例不执行命令、不读取凭据。
