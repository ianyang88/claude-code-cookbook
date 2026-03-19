# Planning with Files

> 像 Manus 一样工作 — Meta 以 20 亿美元收购的 AI 代理公司的工作方式

## 一句话介绍

文件式规划系统，通过 `.planning/` 目录管理任务进度，支持会话恢复

## 适用场景

- 复杂多步骤任务
- 需要跨会话保持进度
- 团队协作追踪任务状态

## 核心功能

### 📁 文件式规划

在项目根目录创建 `.planning/` 文件夹，通过文件管理任务：

```
.planning/
├── task_plan.md      # 任务计划
├── findings.md       # 发现和调研
├── progress.md       # 进度追踪
└── errors.md         # 错误日志
```

### 🔄 会话恢复

当上下文满了运行 `/clear` 后，自动恢复之前的会话状态。

### 🎯 斜杠命令

| 命令 | 功能 |
|------|------|
| `/plan` | 开始新规划 |
| `/plan:status` | 查看当前规划状态 |

### 🖥️ 多 IDE 支持

- Claude Code
- GitHub Copilot
- Cursor
- Gemini CLI
- Kiro
- OpenCode
- Windsurf

## 安装方式

### 方式一：Claude Marketplace

```
/plugins install planning-with-files
```

### 方式二：手动安装

```bash
git clone https://github.com/OthmanAdi/planning-with-files.git
cp -r planning-with-files/.claude/* ~/.claude/
```

## 使用示例

```
用户: 用 planning-with-files 方式帮我重构认证模块

AI: 我将使用 planning-with-files 技能来规划这个任务...

[创建 .planning/task_plan.md]
[创建 .planning/progress.md]
[逐步执行并更新进度]
```

## 相关链接

- [GitHub 仓库](https://github.com/OthmanAdi/planning-with-files)
- [基准测试](https://github.com/OthmanAdi/planning-with-files/blob/main/docs/evals.md) - 96.7% 通过率

---

*版本: 2.23.0 | 最后更新: 2026-03*
