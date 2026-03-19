# Claude Code Cookbook

AI 可读取的资源库，帮助用户配置 Claude Code 环境。

## 使用方式

1. 根据用户需求，从下方表格找到合适的资源
2. 读取对应的详细文档（链接在表格中）
3. 按文档指引帮用户安装配置

---

## Skills（技能包）

工作方法论、最佳实践、进阶技巧。

| Skill | 一句话介绍 | 适用场景 | 详情 |
|-------|-----------|---------|------|
| mindset-shift | 从写代码的工人变成管理者 | 想充分发挥 Claude Code 潜力 | [skills/mindset-shift.md](./skills/mindset-shift.md) |
| golden-workflow | 探索 → 规划 → 执行三步法 | 避免一上来就写代码 | [skills/golden-workflow.md](./skills/golden-workflow.md) |
| master-techniques | 强迫反思、并行处理、子代理 | 进阶用户，想要更高效 | [skills/master-techniques.md](./skills/master-techniques.md) |
| context-reference | @ 文件引用和 IDE 集成 | 想高效传递上下文 | [skills/context-reference.md](./skills/context-reference.md) |

---

## Commands（斜杠命令）

Claude Code 内置命令的使用说明。

| 命令 | 功能 | 使用场景 |
|------|------|---------|
| `/init` | 初始化项目，生成 CLAUDE.md | 在新目录下运行 |
| `@文件名` | 引用文件到上下文 | 输入 `@main.py` 或 `@src/` |
| `/model` | 切换模型 | Sonnet / Opus 切换 |
| `/status` | 查看状态 | Token 使用、模型、上下文 |
| `/compact` | 压缩上下文 | 自动摘要对话历史 |
| `Shift + Tab` | 切换模式 | 编码模式 ↔ 计划模式 |
| `/resume` | 恢复会话 | 网络波动后找回对话 |
| `/mcp` | 管理 MCP | 连接外部数据源 |
| `/skills` | 加载技能包 | 调用预设任务模板 |
| `/memory` | 管理长期记忆 | 查看/清除偏好 |

### 模型选择

| 模型 | 适用场景 |
|------|---------|
| Sonnet 4.5 | 日常开发，平衡速度与智能 |
| Opus 4.5 | 复杂任务，需要最强推理 |

---

## Tools（外部工具）

增强 Claude Code 体验的第三方工具。

| Tool | 一句话介绍 | 适用场景 | 详情 |
|------|-----------|---------|------|
| ccstatusline | 高级状态栏 | 显示 Token/花费/上下文 | [tools/ccstatusline.md](./tools/ccstatusline.md) |
| tweakcc | 美化定制 | 自定义主题/动画 | [tools/tweakcc.md](./tools/tweakcc.md) |
| cc-connect | 远程控制 | 手机远程操作 | [tools/cc-connect.md](./tools/cc-connect.md) |
| claudecodeui | Web 界面 | 桌面/移动端可视化 | [tools/claudecodeui.md](./tools/claudecodeui.md) |

---

## Agents（代理）

专用子代理配置（可选扩展）。

详见 [agents/README.md](./agents/README.md)

---

## 如何贡献

请阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)
