---
name: thinking-assistant
description: This skill should be used when user asks to "command:/ask", "/ask", "ask", "question", "active questioning", "deep understanding", "learn", "think", "deep thinking", "understand", "study", "explore values", "decision making", "问题分析", "意图识别", "思维模型选择", "提问会话", "深度追问", "总结反馈", or mentions "提问", "理解", "学习", "思考", "深入理解", "深度思考", "职业规划", "决策", "选择", "价值观".
---

# 思维助手 Skill (thinking-assistant)

提供 agent 主动提问功能，通过自动选择合适的思维模型，引导用户进行深度思考和问题解决。

---

## 执行要求

**必须按照** `active-questioning-workflow.md` 中的五阶段工作流程执行。

**关键约束**：必须在调用 AskUserQuestion 工具前，先输出"问题分析"和"思维模型选择"的文本内容。

---

## 参考资源

| 文件 | 说明 |
|------|------|
| `references/thinking-models.md` | 四种思维模型的详细说明和选择指南 |
| `references/active-questioning-workflow.md` | 五阶段完整工作流程详解 |
| `references/active-questioning-output.md` | 输出格式模板和示例 |
