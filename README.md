# Claude Code Plugins

Claude Code 插件集合。

---

## 插件

### mind-helper

提供多视角协作思维和 AI 主动提问两个独立技能。

**多视角 (multi-view)**
- 基于 Karpathy "LLMs as Simulators" 理念
- 圆桌会议：模拟多个角色从不同角度分析议题
- 头脑风暴：通过多角色模拟产生创意

**主动提问 (active-ask)**
- AI 主动提问功能
- 支持四种思维模型：费曼学习法、苏格拉底诘问法、第一性原理、水平思考法
- 引导用户深度思考和问题解决

详见 [mind-helper/](./mind-helper/)

---

## 安装

### 添加 Marketplace

```bash
/plugin marketplace add goodmangll/plugins
```

### 安装插件

```bash
/plugin install mind-helper@goodmangll/plugins
```

### 本地开发/测试

```bash
cd /home/linden/area/code/mine/plugins/mind-helper
claude --plugin-dir .
```

---

## 作者

Silas Guo

---

## 许可证

MIT
