# Everything Claude Code：综合优化插件包

> 50K+ Stars 的 Claude Code 性能优化系统，Anthropic 黑客松获奖项目

## 项目简介

[everything-claude-code](https://github.com/affaan-m/everything-claude-code)（简称 ECC）是一个经过 10+ 个月实战打磨的综合配置包。不是简单的配置文件集合，而是一套完整的系统：技能、本能、记忆优化、持续学习、安全扫描。

**适用人群**：想一步到位获得大量高质量配置的进阶用户
**前置条件**：已熟悉 Claude Code 基本操作
**不适合**：刚开始用 Claude Code 的新手（先装 statusline 和基础 skill）

## 包含内容

| 类型 | 数量 | 亮点 |
|------|------|------|
| Skills | **81 个** | 覆盖 Python/Go/Java/Swift/Perl 等，含 TDD、安全扫描、持续学习等 |
| Commands | **43 个** | `/plan`、`/tdd`、`/code-review`、`/learn`、`/verify` 等 |
| Agents | **17 个** | 代码审查、安全检测、构建修复等专用代理 |
| Rules | 多套 | 编码规范、安全检查、测试要求 |
| Hooks | 多个 | 会话持久化、自动格式化、持续学习 |
| MCP Configs | 多个 | 外部服务集成配置 |

## 核心理念

- **Token 优化** — 模型选择、系统提示精简、后台进程
- **记忆持久化** — 通过 Hooks 自动保存/加载上下文
- **持续学习** — 从会话中自动提取模式，转化为可复用技能
- **验证循环** — 检查点 vs 持续评估、评分器类型
- **子代理编排** — 上下文问题、迭代检索模式

## 安装方式

### 方式一：Claude 插件市场（推荐）

```bash
claude plugin install everything-claude-code
```

### 方式二：手动安装

```bash
git clone https://github.com/affaan-m/everything-claude-code.git
# 按需复制 skills/commands/agents/rules 到 ~/.claude/ 对应目录
```

## 注意事项

- 包含大量内容，建议**按需选用**而非全部安装
- 先读 [Shorthand Guide](https://github.com/affaan-m/everything-claude-code/blob/main/the-shortform-guide.md) 了解核心理念
- 支持 Claude Code、Codex、Cowork 等多个 Agent 框架

## 相关链接

- [GitHub 仓库](https://github.com/affaan-m/everything-claude-code)
- [Shorthand Guide（短篇指南）](https://github.com/affaan-m/everything-claude-code/blob/main/the-shortform-guide.md)
- [Longform Guide（长篇指南）](https://github.com/affaan-m/everything-claude-code/blob/main/the-longform-guide.md)
