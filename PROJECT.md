# 项目维护说明

这个项目的目标是把持续学习沉淀为可公开分享的材料：

- `lessons/` 保存每次完整教学内容。
- `templates/` 保存可复用的课程、事件、公司基金和商品分析模板。
- `references/` 保存来源核验规范和长期参考来源。
- `skills/` 保存可复用的 Codex skills，让后续教学、核验和归档更稳定。
- `LEARNING_STATE.md` 保存当前学习进度、交接信息和下节课安排，便于跨电脑继续学习。

GitHub 仓库地址：https://github.com/XXFH1277/LecturesonEconomics

项目状态：持续更新中。后续每次正式教学都应尽量保存为课程笔记，并在需要时更新模板、来源规范和 skills。

## 每次更新流程

1. 开课前联网核验最新事实。
2. 使用合适模板完成教学。
3. 把课程保存到 `lessons/YYYY-MM-DD-topic-slug.md`。
4. 更新 `lessons/INDEX.md`。
5. 更新 `LEARNING_STATE.md`，记录本课交接和下节课安排。
6. 如果出现新的稳定工作流，更新 `skills/`。
7. 提交到 git，之后推送到 GitHub。

## GitHub 发布状态

目标远程仓库：

```text
https://github.com/XXFH1277/LecturesonEconomics.git
```

如果推送失败，优先检查 GitHub CLI 或 Git 凭据是否有效。
