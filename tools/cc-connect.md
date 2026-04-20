# cc-connect：手机远程控制 Claude Code

> 在飞书、钉钉、微信、Telegram 等聊天平台远程控制 Claude Code

**适用人群**：经常离开电脑、需要手机审批操作、团队协作的用户
**前置条件**：有飞书/钉钉/Telegram 等聊天平台账号，本机需保持运行
**不适合**：只在电脑前工作、不需要远程操作的用户
**5 分钟体验**：`npm install -g cc-connect` → 配置 Telegram → 发第一条消息

## 项目简介

[cc-connect](https://github.com/chenhg5/cc-connect) 是一个强大的桥接工具，把本地运行的 AI Coding Agents 连接到你常用的聊天平台。无论你在哪里，只要有手机就能控制 Claude Code 干活。

## 核心功能

### 🤖 支持多种 AI Agent
- Claude Code
- Codex (OpenAI)
- Cursor Agent
- Gemini CLI
- Qoder CLI
- OpenCode
- iFlow CLI

### 📱 支持多种聊天平台
- 飞书 / Lark
- 钉钉
- 微信企业版
- **微信个人版**（beta）
- Telegram
- Discord
- Slack
- LINE
- QQ / QQ Bot

**亮点**：大部分平台无需公网 IP！

### ✨ 特色功能

| 功能 | 说明 |
|------|------|
| 多 Agent 编排 | 群聊中绑定多个 bot，让它们互相协作 |
| 完整的聊天控制 | 通过斜杠命令切换模型、调整推理、管理权限模式 |
| 持久化记忆 | 通过 `/memory` 读写 agent 指令文件 |
| 智能调度 | 用自然语言设置定时任务，如"每天早上 6 点总结 GitHub trending" |
| 多模态支持 | 发送语音或截图，自动处理 STT/TTS |
| 多项目管理 | 一个进程管理多个项目 |
| 多语言界面 | 支持中文、英文、日文、西班牙文 |
| 工作目录切换 | `/dir` 在聊天中切换工作目录 |
| 附件回传 | Agent 生成的截图、PDF 等文件自动发回聊天 |
| 自动压缩 | 上下文过长时自动 trim，避免会话中断 |
| Provider 管理 | `/provider` 运行时切换 API 提供者 |

## 使用场景

- 🚇 **通勤路上**：手机发消息让 Claude Code 继续写代码
- ☕ **咖啡厅**：远程查看 Claude 的进度，审批工具调用
- 🏠 **外出时**：用 Telegram 接收任务完成通知
- 🤝 **团队协作**：飞书群里让多个 AI Agent 讨论问题

## 快速上手

### 安装

```bash
# 稳定版（推荐）
npm install -g cc-connect

# Beta 版（更多功能，可能不稳定）
npm install -g cc-connect@beta

# 或下载二进制
curl -L -o cc-connect https://github.com/chenhg5/cc-connect/releases/latest/download/cc-connect-linux-amd64
chmod +x cc-connect
```

> **微信个人版**：仅在 beta 版中可用，稳定版暂不包含此平台。

### 配置

```bash
mkdir -p ~/.cc-connect
cp config.example.toml ~/.cc-connect/config.toml
# 编辑配置文件，填入你的平台凭证
vim ~/.cc-connect/config.toml
```

### 运行

```bash
cc-connect
```

### 升级

```bash
# npm 升级
npm install -g cc-connect

# 二进制自更新
cc-connect update           # 稳定版
cc-connect update --pre     # Beta 版
```

## 常用命令

```
/new [name]       # 开始新会话
/list             # 列出所有会话
/switch <id>      # 切换会话
/dir [path]       # 查看/切换工作目录
/dir reset        # 重置到配置的默认目录
/mode yolo        # 自动批准所有工具（谨慎使用）
/model            # 切换模型
/provider list    # 列出 API 提供者
/provider switch  # 切换 API 提供者
/cron add 0 6 * * * 每天总结 GitHub trending  # 设置定时任务
```

## 附件回传

Agent 生成的截图、PDF、bundle 等文件可自动发回聊天平台。目前支持飞书和 Telegram。

首次使用需运行：
```
/bind setup
```

## 相关链接

- [GitHub 仓库](https://github.com/chenhg5/cc-connect)
- [使用文档](https://github.com/chenhg5/cc-connect/blob/main/docs/usage.md)
- [AI 友好安装指南](https://github.com/chenhg5/cc-connect/blob/main/INSTALL.md)
- [飞书配置指南](https://github.com/chenhg5/cc-connect/blob/main/docs/feishu.md)
- [Telegram 配置指南](https://github.com/chenhg5/cc-connect/blob/main/docs/telegram.md)
- [Discord 社区](https://discord.gg/kHpwgaM4kq)
- [Telegram 群组](https://t.me/+odGNDhCjbjdmMmZl)

---

*最后更新：2026-04-20*
