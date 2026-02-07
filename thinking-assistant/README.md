# 思维助手插件 (thinking-assistant)

提供协作思维和思维助手两个独立技能的 Claude Code 插件。

## 概述

本插件包含两个独立但互补的技能：

1. **协作思维 (collaborative-thinking)** - 基于多角色模拟的协作思维工具
2. **思维助手 (thinking-assistant)** - 基于 AI 主动提问的思维工具

---

## 技能一：协作思维 (collaborative-thinking)

### 设计理念

**核心理念**：他们怎么说（基于 Karpathy "LLMs as Simulators" 范式）

基于 Andrej Karpathy 的著名观点：

> **LLMs as Simulators**
>
> LLM 不是有自己观点的实体，而是能够模拟各种角色和视角的模拟器。
>
> "What would be a good group of people to explore xyz? What would they say?"

### 功能特性

#### 圆桌会议

通过让 LLM 模拟多个角色的观点，从不同角度深入分析议题，并达成共识或明确分歧。

**核心哲学：**
1. **平等参与** - 所有参与者地位均等，每个观点都重要
2. **开放对话** - 鼓励观点的自由和充分交换
3. **共识导向** - 寻求各方的共同点和一致意见

**两种参与者模式：**
1. **动态模式**（推荐）- LLM 根据议题自动决定适合的参与者
2. **自定义模式** - 手动指定参与者角色

#### 头脑风暴

通过让 LLM 模拟多个角色从不同角度产生创意，促进多元思维碰撞。

**四大原则：**
1. **延迟评判** - 不批评任何想法，鼓励自由表达
2. **自由奔放** - 鼓励大胆和疯狂的想法
3. **数量优先** - 先追求数量，再进行质量筛选
4. **综合改进** - 在他人想法的基础上进行延伸和组合

**两种参与者模式：**
1. **动态模式**（推荐）- LLM 根据主题自动决定适合的创意生成角色
2. **自定义模式** - 手动指定参与者角色

### 使用方式

#### 通过命令
```
/roundtable 如何提高团队协作效率？
/brainstorm 如何改进登录体验？
```

#### 自然对话触发
```
让我们圆桌讨论一下这个产品战略
帮我头脑风暴一下如何改进登录体验
从多个角度分析这个问题
模拟多个角色分析这个决策
```

### 触发条件

- 用户提到"圆桌会议"、"roundtable"、"讨论"、"分析议题"
- 用户提到"头脑风暴"、"brainstorm"、"产生创意"、"想法"
- 用户提到"多方观点"、"多个角度"、"模拟角色"
- 用户提到"协作思维"、"多视角分析"、"角色模拟"

---

## 技能二：思维助手 (thinking-assistant)

### 设计理念

**核心理念**：挖掘自己，自己想要什么（AI 主动提问）

通过自动选择合适的思维模型，引导用户进行深度思考和问题解决。

### 功能特性

支持四种核心思维模型：

1. **费曼学习法**
   - 深入理解复杂概念
   - 发现知识盲区
   - 核心理念："如果你不能简单解释它，你就没有真正理解它"

2. **苏格拉底诘问法**
   - 通过连续追问引导深度思考
   - 探索价值观和信念
   - 发现思维误区

3. **第一性原理**
   - 从最基本原理出发解构复杂系统
   - 创新解决方案
   - 突破传统思维限制

4. **水平思考法**
   - 跳出常规思维路径
   - 寻找新视角和创意
   - 跨界连接不同概念

### 使用方式

#### 通过命令
```
/ask 帮我深入理解量子力学
/ask 如何制定我的职业规划？
```

#### 自然对话触发
```
帮我深入理解区块链
我需要深度思考这个问题
探索我的职业价值观
```

### 触发条件

- 用户提到"深入理解"、"帮我理解"、"学习"、"深度思考"
- 用户提到"为什么"、"价值观"、"信念"、"观点"
- 用户需要深度思考或引导式学习
- 用户提出需要探索的问题

---

## 架构设计

### 整体架构

```
用户 → 命令或自然语言触发
         ↓
    插件识别触发条件
         ↓
    选择对应的技能：
    - collaborative-thinking（协作思维）
    - thinking-assistant（思维助手）
         ↓
    执行对应技能的核心逻辑
         ↓
    输出结果
```

### 目录结构

```
thinking-assistant/
├── .claude-plugin/
│   └── plugin.json              # 插件清单
├── skills/
│   ├── collaborative-thinking/  # 协作思维技能
│   │   ├── SKILL.md             # 协作思维核心协调器
│   │   └── references/          # 协作思维参考文档
│   │       ├── karpathy-principle.md
│   │       ├── role-determination.md
│   │       ├── participant-modes.md
│   │       ├── coordination-strategies.md
│   │       ├── roundtable-workflow.md
│   │       ├── brainstorm-workflow.md
│   │       ├── roundtable-output.md
│   │       └── brainstorm-output.md
│   └── thinking-assistant/      # 思维助手技能
│       ├── SKILL.md             # 思维助手核心协调器
│       └── references/          # 思维助手参考文档
│           ├── thinking-models.md
│           ├── active-questioning-workflow.md
│           └── active-questioning-output.md
├── commands/
│   ├── ask.md                   # AI 主动提问命令
│   ├── brainstorm.md            # 头脑风暴命令
│   └── roundtable.md            # 圆桌会议命令
├── agents/
│   └── （动态加载，无预设角色文件）
└── README.md                   # 本文档
```

### 架构优势

| 维度 | 优势 |
|------|------|
| 技能独立性 | 每个技能有独立的核心逻辑和触发条件 |
| 清晰定位 | 协作思维 vs 思维助手，功能明确分离 |
| 维护便利 | 技能独立维护，互不影响 |
| 扩展性强 | 易于添加新的思维模型或协作方式 |
| 符合 KISS 原则 | 简单直接的架构，无循环依赖 |

---

## 安装方法

### 方法 1：作为本地插件使用

```bash
cd /home/linden/area/code/mine/plugins/thinking-assistant
claude --plugin-dir .
```

### 方法 2：添加到 Claude Code 插件目录

将 `thinking-assistant` 目录复制到你的 Claude Code 插件目录中。

---

## 使用示例

### 协作思维示例

#### 圆桌会议
```
用户: /roundtable 如何提高团队协作效率？

效果: collaborative-thinking Skill 自动触发，
     进入动态模式，由 SKILL.md 协调多角色讨论
```

#### 头脑风暴
```
用户: 帮我头脑风暴一下如何改进登录体验

效果: collaborative-thinking Skill 自动触发，
     进入动态模式，由 SKILL.md 协调多角色产生创意
```

### 思维助手示例

#### 费曼学习法
```
用户: /ask 帮我深入理解量子力学

效果: thinking-assistant Skill 自动触发，
     自动选择费曼学习法思维模型，引导提问
```

#### 苏格拉底诘问法
```
用户: /ask 我应该如何选择职业方向？

效果: thinking-assistant Skill 自动触发，
     自动选择苏格拉底诘问法思维模型，引导思考
```

---

## 两个技能的区别

| 维度 | 协作思维 (collaborative-thinking) | 思维助手 (thinking-assistant) |
|------|--------------------------------|--------------------------------|
| 核心理念 | 他们怎么说 | 我想要什么 |
| 触发条件 | 多角色讨论、创意生成 | 深度思考、问题探索 |
| 主要功能 | 圆桌会议、头脑风暴 | AI 主动提问 |
| 模拟方式 | 模拟多个角色的观点 | 模拟特定思维模型 |
| 适用场景 | 多视角分析、创意产生 | 深度学习、决策思考 |
| 理论基础 | Karpathy "LLMs as Simulators" | 费曼学习法、苏格拉底诘问法等 |
