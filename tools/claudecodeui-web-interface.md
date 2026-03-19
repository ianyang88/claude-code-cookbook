# claudecodeui：Claude Code 的 Web/移动端界面

> 在浏览器或手机上使用 Claude Code，告别纯终端体验

## 项目简介

[claudecodeui](https://github.com/siteboon/claudecodeui)（又名 Cloud CLI）是一个为 Claude Code、Cursor CLI、Codex 和 Gemini CLI 打造的 Web 界面。支持桌面和移动端，让你随时随地管理项目和会话。

## 核心功能

### 🖥️ 响应式界面
- 桌面端完整体验
- 移动端适配设计
- 触控友好操作

### 💬 聊天界面
- 实时 WebSocket 通信
- 会话管理与恢复
- 消息历史记录
- 代码块高亮显示

### 📁 文件浏览器
- 交互式文件树
- 在线编辑文件
- 语法高亮
- 创建/重命名/删除文件

### 🌳 Git 资源管理
- 查看改动
- 暂存和提交
- 切换分支

### 🔧 集成终端
- 直接访问 CLI
- 完整的命令行体验

### 🤖 TaskMaster AI 集成（可选）
- AI 驱动的任务规划
- PRD 解析为结构化任务
- Kanban 风格任务看板

## 使用场景

| 场景 | 优势 |
|------|------|
| 📱 移动办公 | 在平板/手机上查看项目进度、审批操作 |
| 🖥️ 大屏幕体验 | 比终端更直观的多窗口工作流 |
| 👥 团队共享 | 本地部署后团队成员可访问 |
| 📊 任务管理 | 结合 TaskMaster AI 做项目规划 |

## 快速上手

### 一键启动（推荐）

无需安装，直接运行：

```bash
npx @siteboon/claude-code-ui
```

访问 `http://localhost:3001`

### 全局安装

```bash
npm install -g @siteboon/claude-code-ui
claude-code-ui
```

### 后台运行（生产环境推荐）

```bash
# 安装 PM2
npm install -g pm2

# 启动服务
pm2 start claude-code-ui --name "claude-code-ui"

# 开机自启
pm2 startup
pm2 save
```

### CLI 命令

| 命令 | 说明 |
|------|------|
| `cloudcli` 或 `claude-code-ui` | 启动服务器 |
| `cloudcli start` | 显式启动 |
| `cloudcli status` | 查看配置和数据位置 |
| `cloudcli update` | 更新到最新版本 |
| `cloudcli -p 8080` | 指定端口启动 |

## 安全说明

⚠️ **重要**：所有 Claude Code 工具默认禁用，需要在设置中手动开启。建议按需启用，避免意外操作。

## 技术架构

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend       │    │  Agent          │
│   (React/Vite)  │◄──►│ (Express/WS)    │◄──►│  Integration    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 支持的 CLI

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- [Cursor CLI](https://docs.cursor.com/en/cli/overview)
- [Codex](https://developers.openai.com/codex)
- [Gemini-CLI](https://geminicli.com/)

## 相关链接

- [GitHub 仓库](https://github.com/siteboon/claudecodeui)
- [在线演示](https://claudecodeui.siteboon.ai/)
- [云版本](https://cloudcli.ai)

---

*最后更新：2026-03-18*
