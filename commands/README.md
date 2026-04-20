# Commands 斜杠命令

Claude Code 内置命令的使用说明。

## 什么是 Command？

Command 是用户输入 `/xxx` 触发的预设 prompt，类似快捷方式。

## 命令速查表

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

## 模型选择

| 模型 | 适用场景 |
|------|---------|
| Sonnet 4.6 | 日常开发，平衡速度与智能 |
| Opus 4.6 | 复杂任务，需要最强推理 |

## 如何贡献自定义命令

将 `.md` 文件放到项目的 `.claude/commands/` 目录：

```
.claude/
└── commands/
    ├── review.md
    ├── test.md
    └── commit.md
```

### 命令模板

```markdown
---
description: 命令简短描述
---

这里是命令触发后展开的完整 prompt。
```

---

**欢迎贡献！** 请阅读 [CONTRIBUTING.md](../CONTRIBUTING.md)。
