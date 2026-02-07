---
name: collaborative-thinking
description: This skill should be used when user asks to "command:/brainstorm", "command:/roundtable", "/brainstorm", "/roundtable", "brainstorm", "roundtable", "collaborative thinking", "multi-perspective analysis", "role simulation", "simulate multiple people", "roundtable meeting", "generate ideas", "creative thinking", "分析议题", "达成共识", "明确分歧", "多方观点", "多个角度", "模拟角色", "协作思维", "多视角分析", "角色模拟", "产生创意", "想法", "创意生成", "创新思考", "多角度思考", or mentions "头脑风暴", "圆桌会议", "多方讨论", "角色模拟", "多角度分析", "协作思维", "产生创意", "分析议题", "达成共识", "明确分歧", "多方观点".
---

# 协作思维 Skill (collaborative-thinking)

基于多角色模拟，提供圆桌会议和头脑风暴等协作思维工具。

---

## 执行要求

根据用户输入识别模式：
- **圆桌会议**：按照 `roundtable-workflow.md` 十一阶段工作流程执行
- **头脑风暴**：按照 `brainstorm-workflow.md` 十阶段工作流程执行

**关键要点**：
- 使用 Task 工具的 general-purpose 子代理进行角色扮演
- 并行启动多个 Task 实现同时讨论，提升效率
- 严格按照对应的输出模板格式生成结果

---

## 参考资源

| 文件 | 说明 |
|------|------|
| `references/role-determination.md` | 角色决定机制 |
| `references/research-officer.md` | 调研官机制 |
| `references/roundtable-workflow.md` | 圆桌会议工作流程 |
| `references/brainstorm-workflow.md` | 头脑风暴工作流程 |
| `references/roundtable-output.md` | 圆桌会议输出格式模板 |
| `references/brainstorm-output.md` | 头脑风暴输出格式模板 |
