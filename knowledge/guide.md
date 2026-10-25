# 团队上手指南

欢迎使用内网 Agent Store。这里的 skill、MCP 配置和知识文档全部由团队 Git 仓库管理。

## 发布流程

1. 在 skills/<名称>/SKILL.md 编写技能说明，或在 knowledge/ 编写 UTF-8 文档。
2. 在仓库根目录 store.json 登记条目，设置 version、tags 和 published。
3. 提交并推送到远程 Git；在后台点击仓库「同步」。
4. 使用 Python 客户端 list 确认目录，再 install 或 update。

published=false 的内容不会出现在公开目录和知识检索结果中。

## 部署与查询

Docker 部署服务时，应挂载持久化数据卷以及只读 SSH 目录。SSH known_hosts 中须预先信任公司的 Git 主机，凭据只留在服务器。

本机 agent 可安装 agent-store 使用 skill。需要认证时通过 AGENT_STORE_TOKEN 环境变量提供只读令牌，避免把管理令牌写入技能或 Git 仓库。

内置 MCP 的 search_knowledge 和 read_knowledge 工具可以查询这份指南；商店只读知识工具不在服务器运行远程仓库代码。
