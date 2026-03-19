# Commands

这里收集 Claude Code 斜杠命令的详解。

## 什么是 Command？

Command 是用户输入 `/xxx` 触发的预设 prompt，类似快捷方式。

## 已收集的命令详解

| 命令 | 说明 |
|------|------|
| [核心命令详解](./core-commands.md) | /init, @, /model, /compact, /resume 等高频命令 |
| [上下文引用与 IDE 集成](./context-reference-ide.md) | @ 文件选择机制与 VS Code/IDEA 联动 |

## 命令速查表

| 命令 | 功能 |
|------|------|
| `/init` | 初始化项目，生成 CLAUDE.md |
| `@文件名` | 引用文件/文件夹到上下文 |
| `/model` | 切换模型 |
| `/status` | 查看状态（Token、上下文等） |
| `/compact` | 压缩上下文 |
| `/resume` | 恢复中断的会话 |
| `/mcp` | 管理 MCP 服务器 |
| `/skills` | 加载技能包 |
| `/memory` | 管理长期记忆 |
| `Shift+Tab` | 切换 编码/规划 模式 |

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
