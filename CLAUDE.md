# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## 项目概述

Claude Code 插件集合仓库，包含 `mind-helper` 插件，提供多视角协作思维和 AI 主动提问功能。

---

## 本地开发/测试

```bash
# 使用插件目录方式启动 Claude Code
cd /home/linden/area/code/mine/plugins/mind-helper
claude --plugin-dir .
```

---

## 插件架构

### mind-helper 插件

包含两个独立技能：`multi-view`（多视角协作思维）和 `active-ask`（AI 主动提问）。

**目录结构**：
```
mind-helper/
├── .claude-plugin/plugin.json          # 插件清单
├── skills/
│   ├── multi-view/                    # 多视角技能（圆桌会议、头脑风暴）
│   │   ├── SKILL.md                 # 核心协调器
│   │   └── references/              # 工作流程、角色提示词、输出格式
│   └── active-ask/                  # 主动提问技能
│       ├── SKILL.md                 # 核心协调器
│       └── references/              # 思维模型、工作流程
├── commands/                         # 斜杠命令入口
│   ├── roundtable.md
│   ├── brainstorm.md
│   └── ask.md
├── agents/
│   └── readonly-participant.md         # 只读参与者代理（通过提示词实现只读约束）
```

---

## 文档编写规范

### 重要原则

1. **跨平台兼容性**：在文档或代码中描述操作约束时，使用抽象化语言而非具体工具名称：
   - ❌ 避免：提及特定系统的工具（如 `Write`、`Edit`）或命令（如 `mv`、`cp`）
   - ✅ 推荐：描述行为（如"禁止创建新文件"、"禁止修改文件内容"）

2. **保持 SKILL.md 简洁**：SKILL.md 作为核心协调器，应只包含：
   - 技能识别和触发条件（YAML frontmatter）
   - 简要的技能描述
   - 执行要求和关键要点
   - 技能目录架构（直观展示文件结构）

   详细内容（如代理配置、提示词模板、工作流程细节）应放在对应的 references 文件中。

3. **明确文档读取指引**：
   - 在 SKILL.md 的"执行要求"部分开头添加醒目的文档读取指引
   - 使用加粗或特殊格式提高视觉注意力
   - 简洁列出所有需要阅读的 references 文档及其用途
   - 特别标注包含关键约束的文档

   **示例**：
   ```markdown
   **执行前必须阅读**：
   1. `references/thinking-models.md` - 思维模型
   2. `references/active-questioning-workflow.md` - 执行流程（含关键约束）
   3. `references/active-questioning-output.md` - 输出格式
   ```

---

## 多视角技能 (multi-view) 核心概念

### 角色决定机制

动态角色决定：根据议题分析，选择 3-6 个角色。

**角色类型**：
- **具体人物角色**：如史蒂夫·乔布斯、埃隆·马斯克（有已知个性）
- **抽象职位角色**：如"具有乔布斯式完美主义的产品设计师"（必须包含详细人物画像）

**角色描述规范**：抽象角色必须包含性格特征、说话风格、价值观、决策偏好。

### 只读安全约束

所有角色代理通过提示词约束实现只读行为：

- **禁止**：创建/修改/删除文件、执行改变系统状态的操作、运行代码或脚本
- **允许**：读取文件、查找文件、搜索信息、查询系统状态（不改变状态）

### 工作流程

- **圆桌会议**：十一阶段流程（材料收集→角色决定→议题澄清→角色发言→调研验证→观点交换→共识提炼→会议总结）
- **头脑风暴**：十阶段流程（问题分析→材料收集→角色决定→协调创意生成→想法延伸组合→整理分类→调研验证→生成报告）

---

## 主动提问技能 (active-ask) 核心概念

### 四种思维模型

1. **费曼学习法**：深入理解复杂概念，发现知识盲区
2. **苏格拉底诘问法**：通过连续追问引导深度思考
3. **第一性原理**：从最基本原理出发解构复杂系统
4. **水平思考法**：跳出常规思维路径，寻找新视角

### 工作流程

自动选择合适的思维模型 → 按照工作流程引导用户 → 输出结果

---

## 触发方式

**推荐**：直接使用 skill 名字触发
```
/multi-view 议题内容
/active-ask 问题内容
```

**命令方式**（可能有识别问题）：
```
/roundtable 议题内容
/brainstorm 问题内容
/ask 问题内容
```
