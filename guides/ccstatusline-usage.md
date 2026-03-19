# ccstatusline：Claude Code 高级状态栏

> 在终端底部显示模型信息、Git 状态、Token 用量等实时指标

## 项目简介

[ccstatusline](https://github.com/sirmalloc/ccstatusline) 是一个高度可定制的 Claude Code 状态栏工具。通过 TUI 界面配置，支持 Powerline 样式、多种小部件、实时指标追踪。

![Demo](https://raw.githubusercontent.com/sirmalloc/ccstatusline/main/screenshots/demo.gif)

## 核心功能

### 📊 实时指标

- **模型信息** - 当前使用的 Claude 模型
- **Token 追踪** - 输入/输出/缓存/总计 token 数
- **Token 速度** - 每秒处理 token 数（支持滚动窗口）
- **上下文使用** - 上下文窗口占用百分比
- **会话时长** - 当前会话持续时间
- **会话花费** - 实时 USD 花费追踪
- **Block 计时器** - 5 小时用量块进度

### 🌳 Git 集成

- **Git Branch** - 当前分支名
- **Git Changes** - `+insertions -deletions`
- **Git Worktree** - 当前 worktree 名称
- **Git Root Dir** - 仓库根目录名

### ⚡ Powerline 支持

- 美观的箭头分隔符样式
- 自定义 Powerline 字体
- 多行状态栏支持
- 自动对齐

### 🖥️ 交互式 TUI

- 可视化配置界面
- 实时预览
- 小部件分类选择器
- 颜色自定义

## 可用小部件一览

| 类别 | 小部件 |
|------|--------|
| **模型** | Model, Output Style, Version |
| **Token** | Input, Output, Cached, Total, Input Speed, Output Speed, Total Speed |
| **上下文** | Context Length, Context %, Context % (usable), Context Bar |
| **会话** | Session Clock, Session Cost, Session Name, Session ID |
| **用量** | Session Usage, Weekly Usage, Block Timer, Block Reset Timer, Weekly Reset Timer |
| **Git** | Branch, Changes, Insertions, Deletions, Root Dir, Worktree |
| **其他** | Current Working Dir, Terminal Width, Memory Usage |
| **自定义** | Custom Text, Custom Command, Link, Separator, Flex Separator |

## 快速上手

### 一键运行（无需安装）

```bash
# 使用 npm
npx -y ccstatusline@latest

# 使用 Bun（更快）
bunx -y ccstatusline@latest
```

### 配置流程

1. **启动配置界面**
   ```bash
   npx -y ccstatusline@latest
   ```

2. **添加小部件** - 按 `a` 选择要显示的小部件

3. **自定义样式** - 设置颜色、间距、分隔符

4. **安装到 Claude Code** - 选择 "Install to Claude Code settings"

5. **重启 Claude Code** - 状态栏自动显示

### Claude Code 配置格式

安装后会在 `~/.claude/settings.json` 中添加：

```json
{
  "statusLine": {
    "type": "command",
    "command": "npx -y ccstatusline@latest",
    "padding": 0
  }
}
```

## Powerline 配置

### 启用 Powerline

1. 在配置界面进入 "Powerline Setup"
2. 启用 Powerline 模式
3. 选择分隔符样式
4. 安装 Powerline 字体（可选自动安装）

### Windows 字体安装

```powershell
# 通过 winget 安装 Nerd Font
winget install JetBrainsMono.NerdFont
```

### 终端配置

**Windows Terminal** (推荐):
```json
{
  "profiles": {
    "defaults": {
      "font": {
        "face": "JetBrainsMono Nerd Font",
        "size": 12
      }
    }
  }
}
```

## 自定义命令小部件

执行 shell 命令并显示输出：

```bash
# 显示当前时间
date +%H:%M

# 显示 Node.js 版本
node -v

# 显示 Git commit hash
git rev-parse --short HEAD

# 集成 ccusage 用量追踪
npx -y ccusage@latest statusline
```

**注意**：命令超时默认 1000ms，可在编辑时按 `t` 调整。

## 高级配置

### 自定义配置路径

```bash
# Linux/macOS
export CLAUDE_CONFIG_DIR=/custom/path/to/.claude

# Windows PowerShell
$env:CLAUDE_CONFIG_DIR="C:\custom\path\.claude"
```

### 使用代理

用量小部件支持 HTTPS 代理：

```bash
export HTTPS_PROXY=http://proxy.example.com:8080
```

### Block Timer 缓存

自动缓存 block 指标以减少 JSONL 解析：
- 缓存位置：`~/.cache/ccstatusline/`
- 自动 5 小时失效

## 常见问题

### Powerline 符号显示为方框？

安装 Nerd Font 并在终端中配置。

### Git 信息不显示？

确保在 Git 仓库中运行，且 Git 已安装。

### Windows 上颜色不正确？

VSCode 终端可能强制对比度，调整设置：
```json
"terminal.integrated.minimumContrastRatio": 1
```

### 命令输出不显示？

尝试增加超时时间（按 `t` 键）。

## 相关链接

- [GitHub 仓库](https://github.com/sirmalloc/ccstatusline)
- [npm 包](https://www.npmjs.com/package/ccstatusline)
- [相关项目：ccusage](https://github.com/ryoppippi/ccusage)

---

*最后更新：2026-03-19*
