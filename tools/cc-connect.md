# cc-connect：手机远程控制 Claude Code

> 在飞书、钉钉、微信、Telegram 等聊天平台远程控制 Claude Code

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

## 使用场景

- 🚇 **通勤路上**：手机发消息让 Claude Code 继续写代码
- ☕ **咖啡厅**：远程查看 Claude 的进度，审批工具调用
- 🏠 **外出时**：用 Telegram 接收任务完成通知
- 🤝 **团队协作**：飞书群里让多个 AI Agent 讨论问题

## 快速上手

### 安装

```bash
# 通过 npm 安装
npm install -g cc-connect

# 或下载二进制
curl -L -o cc-connect https://github.com/chenhg5/cc-connect/releases/latest/download/cc-connect-linux-amd64
chmod +x cc-connect
```

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

## 常用命令

```
/new [name]       # 开始新会话
/list             # 列出所有会话
/switch <id>      # 切换会话
/mode yolo        # 自动批准所有工具（谨慎使用）
/model            # 切换模型
/cron add 0 6 * * * 每天总结 GitHub trending  # 设置定时任务
```

## 相关链接

- [GitHub 仓库](https://github.com/chenhg5/cc-connect)
- [使用文档](https://github.com/chenhg5/cc-connect/blob/main/docs/usage.md)
- [飞书配置指南](https://github.com/chenhg5/cc-connect/blob/main/docs/feishu.md)
- [Telegram 配置指南](https://github.com/chenhg5/cc-connect/blob/main/docs/telegram.md)
- [Discord 社区](https://discord.gg/kHpwgaM4kq)
- [Telegram 群组](https://t.me/+odGNDhCjbjdmMmZl)

---

*最后更新：2026-03-18*
