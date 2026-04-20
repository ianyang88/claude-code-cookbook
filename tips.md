# 使用技巧与避坑指南

> 安装完工具之后，这些经验让你用得更好

---

## 上下文管理

上下文窗口是 Claude Code 的"工作记忆"。用满了就会自动压缩，压缩后之前讨论的细节会丢失。

### 什么时候该 `/compact`

- 对话超过 **20 轮** 时主动压缩
- 切换到**不相关的新任务**时先压缩
- Claude 开始**重复自己**或**遗忘之前说过的话**时

### 什么时候该开新会话

- 任务**完全不同**（比如从写代码切到写文档）
- 已经 `/compact` 过但效果不好
- Claude 的输出质量明显下降

### 保持上下文健康的习惯

- 一次只做一件事，不要在同一个会话里来回切换任务
- 大文件用 `@文件名` 引入，不要让 Claude 自己去找
- 用 `/status` 查看 Token 使用情况，超过 **75%** 就该压缩了

---

## 费用意识

### 模型成本差异

| 模型 | 相对成本 | 适用场景 |
|------|---------|---------|
| Sonnet | 1x | 日常开发 |
| Opus | ~3x | 复杂架构决策、难搞的 bug |

### 省钱习惯

- 日常开发用 Sonnet，只有真正需要深度推理时才切 Opus
- 用 `/model` 切换，不要全程用 Opus
- 探索和简单改动用 Sonnet，复杂规划和审查用 Opus
- 安装 ccstatusline 后可以实时看到花费

---

## 常见错误

### 1. 上来就写代码

```
❌ "帮我写个登录功能"
✅ "先帮我看看现有的认证系统是怎么实现的"
```

先探索，再规划，最后执行。用 `Shift+Tab` 切到规划模式先出方案。

### 2. 一次塞太多任务

```
❌ "帮我重构整个项目，加上测试，再写个 README"
✅ "帮我重构 auth 模块" → 完成后 → "帮我给 auth 模块写测试"
```

拆成小任务，一个会话一个重点。

### 3. 不验证就信任

```
❌ Claude 说"已经修好了" → 直接提交
✅ Claude 说"已经修好了" → 跑一下测试确认
```

### 4. 忽略 CLAUDE.md

每个项目都应该有 CLAUDE.md。没有的话用 `/init` 生成一个。这是 Claude 理解你项目的关键。

### 5. 把它当搜索引擎

```
❌ "Python 怎么读文件"
✅ "在这个项目里，用现有的工具函数帮我加一个读取 config.yml 的功能"
```

给它上下文，而不是问通用问题。

---

## 写好你的 CLAUDE.md

CLAUDE.md 是 Claude 理解你项目的"说明书"。写得好，Claude 的输出质量会明显提升。

### 必须包含的内容

```markdown
# 项目名

## 项目概述
一到两句话说清楚这个项目是做什么的。

## 技术栈
用了什么框架、语言、数据库。

## 运行命令
- 启动：`npm run dev`
- 测试：`npm test`
- 构建：`npm run build`

## 项目结构
src/
├── components/   # UI 组件
├── services/     # 业务逻辑
└── utils/        # 工具函数

## 开发规范
- 命名：camelCase
- 组件：函数式组件
- 状态：用 Zustand，不用 Redux
```

### 常见错误

- **太长** — 超过 100 行 Claude 会忽略后半部分
- **太抽象** — "遵循最佳实践" 没用，要说具体用什么
- **没有运行命令** — Claude 不知道怎么跑你的项目
- **忘了更新** — 技术栈变了但 CLAUDE.md 没改

### 小技巧

- 用 `/init` 自动生成初始版本，再手动调整
- 把团队的代码规范写进去（命名、文件组织、错误处理）
- 标注已知的坑（"这个 API 有个 bug，不要用 X 方法"）

---

## GitHub 下载加速

国内直连 GitHub 下载文件经常超时。使用镜像加速：

```bash
# 首选：ghfast.top（~300KB/s）
curl -L -o 文件名.zip "https://ghfast.top/https://github.com/用户/仓库/releases/download/版本/文件名"

# 备选：gh-proxy.com（小文件可用）
curl -L -o 文件名.zip "https://gh-proxy.com/https://github.com/用户/仓库/releases/download/版本/文件名"

# 镜像也不行时：用 aria2c 多线程下载
aria2c -x 16 "https://ghfast.top/https://github.com/用户/仓库/releases/download/版本/文件名"
```

可用镜像（2026-04 测试）：`ghfast.top`（~300KB/s）、`gh-proxy.com`（小文件可用）

镜像可能随时间失效，搜索"GitHub 加速镜像"获取最新可用地址。

---

## Windows 用户注意事项

- 路径用**正斜杠** `/` 而不是 `\`，在 Claude Code 里两种都行但 `/` 更稳妥
- 路径有空格时用**引号**包裹
- 如果遇到权限问题，检查是否需要管理员权限
- **Windows Terminal** 是最佳选择，比 CMD 和 PowerShell 体验更好
- 安装 Nerd Font（如 `winget install DEVCOM.JetBrainsMonoNerdFont`）可以让状态栏和主题显示更多符号

---

## 故障排除

| 问题 | 解决方案 |
|------|---------|
| Claude 输出变差、遗忘上下文 | `/compact` 或开新会话 |
| 网络中断后对话丢失 | `/resume` 恢复 |
| 工具安装失败 | 检查 Node.js 版本（`node -v`），需要 18+ |
| 状态栏不显示 | 检查 `~/.claude/settings.json` 中是否有 `statusLine` 配置 |
| 主题/美化不生效 | 重启 Claude Code，或用 `npx tweakcc --apply` 重新应用 |
| `/compact` 后 Claude 忘了之前的约定 | 重要约定写在 CLAUDE.md 里，不会被压缩掉 |
