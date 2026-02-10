---
name: multi-view
description: This skill should be used when user asks to "command:/brainstorm", "command:/roundtable", "/brainstorm", "/roundtable", "brainstorm", "roundtable", "collaborative thinking", "multi-perspective analysis", "participant simulation", "simulate multiple people", "roundtable meeting", "generate ideas", "creative thinking", "分析议题", "达成共识", "明确分歧", "多方观点", "多个角度", "模拟参会人", "协作思维", "多视角分析", "参会人模拟", "产生创意", "想法", "创意生成", "创新思考", "多角度思考", or mentions "头脑风暴", "圆桌会议", "多方讨论", "参会人模拟", "多角度分析", "协作思维", "产生创意", "分析议题", "达成共识", "明确分歧", "多方观点".
---

# 多视角 Skill (multi-view)

通过模拟多名参会者，提供圆桌会议和头脑风暴等协作思维工具。

---

## 执行要求

⚠️ **执行前必须阅读以下相关文档**：

[common.md](references/common.md)

### 圆桌会议流程

1. [roundtable.md](references/roundtable.md) - 圆桌会议工作流程
2. [participant-def.md](references/participant-def.md) - 参会者定义机制
3. [participants.md](references/participants.md) - 参会者选择流程
4. [research.md](references/research.md) - 调研官机制
5. [roundtable-output.md](references/roundtable-output.md) - 圆桌会议输出格式

### 头脑风暴流程

1. [brainstorm.md](references/brainstorm.md) - 头脑风暴工作流程
2. [participant-def.md](references/participant-def.md) - 参会者定义机制
3. [participants.md](references/participants.md) - 参会者选择流程
4. [research.md](references/research.md) - 调研官机制
5. [brainstorm-output.md](references/brainstorm-output.md) - 头脑风暴输出格式

### 公共文档

[common.md](references/common.md) - 公共流程

---

根据用户输入识别模式：
- **圆桌会议**：按照 [roundtable.md](references/roundtable.md) 执行
- **头脑风暴**：按照 [brainstorm.md](references/brainstorm.md) 执行

**关键要点**：
- 参会者以子代理角色扮演的形式工作，主代理只负责协调不进行角色扮演
- 参会者只能进行分析和输出文本，禁止任何文件修改或创建
- 严格按照对应的输出模板格式生成结果

---

## 技能目录架构

```
multi-view/
├── SKILL.md                          # 核心协调器（当前文件）
└── references/                       # 技能参考文档
    ├── common.md                      # 公共工作流程步骤
    ├── participant-def.md             # 参会者定义机制
    ├── participants.md                # 参会者选择流程
    ├── research.md                    # 调研官机制
    ├── roundtable.md                  # 圆桌会议工作流程
    ├── brainstorm.md                  # 头脑风暴工作流程
    ├── roundtable-output.md           # 圆桌会议输出格式
    └── brainstorm-output.md          # 头脑风暴输出格式
```
