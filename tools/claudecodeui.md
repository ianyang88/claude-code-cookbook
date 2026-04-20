# CloudCLI (原 claudecodeui)：Claude Code 的 Web/移动端界面

> 在浏览器或手机上使用 Claude Code，告别纯终端体验

**适用人群**：想要图形界面、在手机/平板上查看项目、团队共享的用户
**前置条件**：Node.js v22+（自托管）或浏览器（Cloud 方案）
**不适合**：纯终端用户、不想在本机跑服务的用户
**5 分钟体验**：`npx @cloudcli-ai/cloudcli` → 浏览器打开 `http://localhost:3001`

## 项目简介

[CloudCLI](https://github.com/siteboon/claudecodeui)（原名 claudecodeui）是一个为 Claude Code、Cursor CLI、Codex 和 Gemini CLI 打造的 Web 界面。支持桌面和移动端，让你随时随地管理项目和会话。

> ⚠️ **包名已变更**：从 `@siteboon/claude-code-ui` 更名为 `@cloudcli-ai/cloudcli`。

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

### 🧩 插件系统
- 安装社区插件或自建插件
- 添加自定义 Tab 和后端服务
- [插件开发模板](https://github.com/cloudcli-ai/cloudcli-plugin-starter)

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

### 方式一：CloudCLI Cloud（推荐）

无需本地部署，完全托管的容器化开发环境，支持 Web、移动端、API 和 IDE 访问。

详见 [cloudcli.ai](https://cloudcli.ai)

### 方式二：自托管（npm）

```bash
# 一键启动（推荐，需要 Node.js v22+）
npx @cloudcli-ai/cloudcli

# 全局安装
npm install -g @cloudcli-ai/cloudcli
cloudcli
```

访问 `http://localhost:3001` — 自动发现所有已有会话。

### 方式三：Docker Sandbox（实验性）

在隔离沙盒中运行 Agent，提供 hypervisor 级别的隔离：

```bash
npx @cloudcli-ai/cloudcli@latest sandbox ~/my-project
```

### 后台运行（生产环境推荐）

```bash
# 安装 PM2
npm install -g pm2

# 启动服务
pm2 start cloudcli --name "cloudcli"

# 开机自启
pm2 startup
pm2 save
```

### CLI 命令

| 命令 | 说明 |
|------|------|
| `cloudcli` | 启动服务器 |
| `cloudcli -p 8080` | 指定端口启动 |

## 安全说明

⚠️ **重要**：所有 Claude Code 工具默认禁用，需要在设置中手动开启。建议按需启用，避免意外操作。

## 方案对比

| | 自托管 (npm) | Docker Sandbox (实验性) | CloudCLI Cloud |
|---|---|---|---|
| **适用** | 本地 Agent 会话 | 隔离 Agent 环境 | 团队云端使用 |
| **访问** | `[yourip]:port` | `localhost:port` | 任何设备 |
| **隔离** | 运行在宿主机 | hypervisor 级别 | 完全云端隔离 |
| **需要开机** | 是 | 是 | 否 |
| **费用** | 免费开源 | 免费开源 | $7/月起 |

> 所有方案均使用你自己的 AI 订阅（Claude、Cursor 等），CloudCLI 只提供环境。

## 支持的 CLI

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- [Cursor CLI](https://docs.cursor.com/en/cli/overview)
- [Codex](https://developers.openai.com/codex)
- [Gemini-CLI](https://geminicli.com/)

## 相关链接

- [GitHub 仓库](https://github.com/siteboon/claudecodeui)
- [在线文档](https://cloudcli.ai/docs)
- [CloudCLI Cloud](https://cloudcli.ai)

---

*最后更新：2026-04-20*
