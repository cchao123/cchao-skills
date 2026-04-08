---
name: commit-no-claude
description: 帮我提交代码，不包含 Claude Code 相关信息
disable-model-invocation: true
---

帮我提交当前的更改。要求：
1. 查看当前 git status 和 git diff
2. 生成一个简洁的 commit message（中文）
3. **重要**：commit message 中不要包含任何 Claude Code、Claude、Co-Authored-By 等相关信息
4. 不要在 commit message 中提及是 AI 辅助编写的
5. 执行 git commit

如果有未暂存的文件，询问用户是否需要一起提交。
