# 项目维护说明

这个项目的目标是把持续学习沉淀为可公开分享的材料：

- `lessons/` 保存每次完整教学内容。
- `templates/` 保存可复用的课程、事件、公司基金和商品分析模板。
- `references/` 保存来源核验规范和长期参考来源。
- `skills/` 保存可复用的 Codex skills，让后续教学、核验和归档更稳定。

## 每次更新流程

1. 开课前联网核验最新事实。
2. 使用合适模板完成教学。
3. 把课程保存到 `lessons/YYYY-MM-DD-topic-slug.md`。
4. 更新 `lessons/INDEX.md`。
5. 如果出现新的稳定工作流，更新 `skills/`。
6. 提交到 git，之后推送到 GitHub。

## GitHub 发布状态

当前本地仓库还没有远程地址。发布到 GitHub 需要：

1. 重新登录 GitHub CLI，或提供一个已创建的 GitHub 仓库地址。
2. 添加 `origin` remote。
3. 推送 `main` 分支。

建议仓库名：`economic-classroom` 或 `realtime-econ-classroom`。
