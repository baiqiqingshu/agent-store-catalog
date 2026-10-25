# Agent Store 内容仓库

这是 [agent-store](https://github.com/baiqiqingshu/agent-store) 服务的 Git 内容仓库，承载商店发布的 skill、MCP 配置与知识文档。商店服务从发布分支克隆并校验 `store.json`，条目以 `仓库ID:条目ID` 对外提供。

## 目录结构

- `store.json`：发布清单，登记条目 ID、版本、路径与 published 状态。
- `skills/<名称>/SKILL.md`：技能目录。
- `knowledge/*.md`：知识文档（UTF-8 文本）。

清单条目：hello（已发布 skill）、draft（未发布 skill）、fetch（stdio MCP 配置）、guide（知识文档）。同一仓库内 ID 跨类型唯一。

## 发布流程

1. 修改 skill、MCP 声明或知识文件，并在 `store.json` 更新 `version`、`tags`、`published`。
2. 提交并推送到发布分支（默认 `main`）。
3. 商店按配置间隔自动检查，也可在后台手动同步。

`published=false` 的条目不会出现在公开目录和知识检索中。
