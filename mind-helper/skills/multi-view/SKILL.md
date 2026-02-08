---
name: multi-view
description: This skill should be used when user asks to "command:/brainstorm", "command:/roundtable", "/brainstorm", "/roundtable", "brainstorm", "roundtable", "collaborative thinking", "multi-perspective analysis", "role simulation", "simulate multiple people", "roundtable meeting", "generate ideas", "creative thinking", "分析议题", "达成共识", "明确分歧", "多方观点", "多个角度", "模拟角色", "协作思维", "多视角分析", "角色模拟", "产生创意", "想法", "创意生成", "创新思考", "多角度思考", or mentions "头脑风暴", "圆桌会议", "多方讨论", "角色模拟", "多角度分析", "协作思维", "产生创意", "分析议题", "达成共识", "明确分歧", "多方观点".
---

# 多视角 Skill (multi-view)

基于多角色模拟，提供圆桌会议和头脑风暴等协作思维工具。

---

## 执行要求

**执行前必须阅读**：

### 若为圆桌会议流程：
1. `references/roundtable-workflow.md` - 圆桌会议工作流程
2. `references/role-determination.md` - 角色决定机制
3. `references/role-determination-process.md` - 角色决定流程
4. `references/research-officer.md` - 调研官机制
5. `references/role-prompt-templates.md` - 通用提示词约束
6. `references/roundtable-role-prompt.md` - 圆桌会议角色提示词
7. `references/roundtable-output.md` - 圆桌会议输出格式

### 若为头脑风暴流程：
1. `references/brainstorm-workflow.md` - 头脑风暴工作流程
2. `references/role-determination.md` - 角色决定机制
3. `references/role-determination-process.md` - 角色决定流程
4. `references/research-officer.md` - 调研官机制
5. `references/role-prompt-templates.md` - 通用提示词约束
6. `references/brainstorm-role-prompt.md` - 头脑风暴角色提示词
7. `references/brainstorm-output.md` - 头脑风暴输出格式

---

根据用户输入识别模式：
- **圆桌会议**：按照 `roundtable-workflow.md` 十一阶段工作流程执行
- **头脑风暴**：按照 `brainstorm-workflow.md` 十阶段工作流程执行

**关键要点**：
- 角色只能进行分析和输出文本，禁止任何文件修改或创建
- 严格按照对应的输出模板格式生成结果

---

## 技能目录架构

```
multi-view/
├── SKILL.md                          # 核心协调器（当前文件）
└── references/                       # 技能参考文档
    ├── role-determination.md         # 角色决定机制
    ├── role-determination-process.md # 角色决定流程
    ├── role-prompt-templates.md      # 通用提示词约束说明
    ├── roundtable-role-prompt.md     # 圆桌会议角色提示词
    ├── brainstorm-role-prompt.md     # 头脑风暴角色提示词
    ├── research-officer.md           # 调研官机制
    ├── roundtable-workflow.md        # 圆桌会议工作流程
    ├── brainstorm-workflow.md        # 头脑风暴工作流程
    ├── roundtable-output.md          # 圆桌会议输出格式
    └── brainstorm-output.md          # 头脑风暴输出格式
```
