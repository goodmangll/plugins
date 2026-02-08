---
name: active-ask
description: This skill should be used when user asks to "command:/ask", "/ask", "ask", "question", "active questioning", "deep understanding", "learn", "think", "deep thinking", "understand", "study", "explore values", "decision making", "问题分析", "意图识别", "思维模型选择", "提问会话", "深度追问", "总结反馈", or mentions "提问", "理解", "学习", "思考", "深入理解", "深度思考", "职业规划", "决策", "选择", "价值观".
---

# 主动提问 Skill (active-ask)

提供 agent 主动提问功能，通过自动选择合适的思维模型，引导用户进行深度思考和问题解决。

---

## 执行要求

⚠️ **执行前必须阅读**：
1. `references/thinking-models-definition.md` - 思维模型定义
2. `references/thinking-models-selection.md` - 思维模型选择指南
3. `references/active-questioning-workflow.md` - 执行流程（含关键约束）
4. `references/active-questioning-output.md` - 输出格式

**执行流程**：必须按照 `active-questioning-workflow.md` 中的五阶段工作流程执行。

**关键约束**：必须在调用 AskUserQuestion 工具前，先输出"问题分析"和"思维模型选择"的文本内容。

---

## 技能目录架构

```
active-ask/
├── SKILL.md                          # 核心协调器（当前文件）
└── references/                       # 技能参考文档
    ├── thinking-models-definition.md # 四种思维模型详细定义
    ├── thinking-models-selection.md  # 思维模型选择指南
    ├── active-questioning-workflow.md # 五阶段完整工作流程详解
    └── active-questioning-output.md  # 输出格式模板和示例
```
