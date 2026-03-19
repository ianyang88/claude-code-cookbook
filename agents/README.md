# Agents 代理

专用子代理配置（可选扩展）。

## 什么是 Agent？

Agent 是具有特定专业能力的子代理，可以并行执行任务，提供多视角分析。

## 内置代理类型

Claude Code 内置了多种代理类型：

| Agent | 用途 |
|-------|------|
| general-purpose | 通用代理，处理复杂任务 |
| Explore | 快速探索代码库 |
| Plan | 设计实现计划 |
| code-reviewer | 代码质量审查 |
| security-reviewer | 安全漏洞检测 |
| tdd-guide | 测试驱动开发指导 |

## 使用场景

```
请启动两个子代理：
1. 一个负责安全审查
2. 一个负责编写测试

同时进行，最后合并结果
```

## 自定义代理

可以在 `.claude/agents/` 目录下创建自定义代理配置。

### 代理模板

```markdown
---
name: agent-name
description: 代理简短描述
tools: Read, Write, Edit, Bash
model: sonnet
---

# Agent 指令

详细描述代理应该如何执行任务...
```

---

**欢迎贡献！** 请阅读 [CONTRIBUTING.md](../CONTRIBUTING.md)。
