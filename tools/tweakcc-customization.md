# tweakcc：Claude Code 终极美化工具

> 自定义 Claude Code 的主题、系统提示、思考动画，打造个性化开发体验

## 项目简介

[tweakcc](https://github.com/Piebald-AI/tweakcc) 是一个强大的 CLI 工具，通过修改 Claude Code 的 `cli.js` 文件来实现深度自定义。从视觉主题到系统提示，几乎可以定制一切。

## 核心功能

### 🎨 自定义主题
- 图形化 HSL/RGB 颜色选择器
- 创建多个主题并快速切换
- 自定义所有 UI 颜色

### ✏️ 系统提示定制
- 修改主系统提示
- 自定义 17 个内置工具描述
- 修改 Task/Plan/Explore 子代理提示
- 自动处理版本更新冲突

### 🧩 工具集管理
- 创建不同的工具集合
- 按 `/toolset` 快速切换
- 减少系统提示长度，节省 token

### 🌙 思考动画
- 自定义思考动词（"思考中..."、"分析中..."）
- 70+ 种 spinner 动画可选
- 调整动画速度和相位

### 📝 其他美化
- 自定义用户消息样式
- 移除输入框 ASCII 边框
- 默认展开思考块
- 修改启动 banner
- 手动命名会话（`/title` 或 `/rename`）

## 使用场景

| 场景 | 优势 |
|------|------|
| 🎯 视觉个性化 | 打造专属配色主题 |
| ⚡ 优化性能 | 通过工具集减少 token 消耗 |
| 🔧 定制行为 | 修改系统提示以适应特定工作流 |
| 👀 调试分析 | 展开思考块查看详细推理过程 |

## 快速上手

### 一键运行（无需安装）

```bash
npx tweakcc

# 或使用 pnpm
pnpm dlx tweakcc
```

### 工作流程

1. **运行 tweakcc** - 首次运行会创建配置目录
2. **选择功能** - 主题/系统提示/工具集等
3. **应用更改** - 选择 `Apply customizations`
4. **重启 Claude Code** - 享受新体验

### 配置目录

tweakcc 按优先级查找配置目录：

1. `TWEAKCC_CONFIG_DIR` 环境变量
2. `~/.tweakcc/`
3. `~/.claude/tweakcc/`
4. `$XDG_CONFIG_HOME/tweakcc`

**推荐**：如果你版本控制 `~/.claude`，可以把 tweakcc 配置也放进去：

```bash
mkdir -p ~/.claude/tweakcc
```

## 系统提示定制详解

### 提示文件结构

tweakcc 为每个提示部分维护独立的 markdown 文件：

```
~/.tweakcc/system-prompts/
├── main-system-prompt.md      # 主系统提示
├── tool-bash.md               # Bash 工具描述
├── tool-read.md               # Read 工具描述
├── agent-task.md              # Task 代理提示
└── ...                        # 其他部分
```

### 定制流程

1. 运行 `npx tweakcc` 初始化
2. 编辑 `~/.tweakcc/system-prompts/` 中的 markdown 文件
3. 运行 `npx tweakcc --apply` 应用更改

### 版本更新处理

当 Claude Code 更新时：
- 未修改的文件自动更新
- 已修改且与官方冲突的文件生成 HTML diff 对比
- 手动解决冲突后更新 `ccVersion` 字段

### 推荐做法

```bash
# 用 Git 管理你的提示定制
cd ~/.tweakcc
git init
git add .
git commit -m "Initial tweakcc config"
```

## 工具集使用

### 创建工具集

1. 运行 `npx tweakcc`
2. 进入 `Toolsets` 菜单
3. 按 `n` 创建新工具集
4. 选择要启用的工具
5. 设置为默认

### 典型工具集示例

| 工具集名称 | 包含工具 | 用途 |
|-----------|---------|------|
| **full** | 所有工具 | 完整开发模式 |
| **research** | WebFetch, WebSearch | 研究/查阅模式 |
| **read-only** | Read, Glob, Grep | 代码审查模式 |
| **minimal** | Read, Edit | 快速修改模式 |

## 常见问题

### 主题没生效？

在 Claude Code 中使用 `/theme` 切换到新主题。

### 颜色没变化？

部分文本使用终端默认前景色，无法自定义。

### 想禁用所有颜色？

```bash
export FORCE_COLOR=0
claude
```

### 恢复默认？

删除 tweakcc 备份文件后重装 Claude Code：

```bash
rm ~/.tweakcc/cli.backup.js  # npm 安装
# 或
rm ~/.tweakcc/native-binary.backup  # 原生安装
```

然后重装 Claude Code 并重新运行 tweakcc。

## 注意事项

- ⚠️ 通过修改 `cli.js` 实现功能，更新 Claude Code 后需重新应用
- ✅ 配置会被保留，运行 `npx tweakcc --apply` 即可恢复
- 🔒 已验证支持 Claude Code 2.0.69+

## 相关链接

- [GitHub 仓库](https://github.com/Piebald-AI/tweakcc)
- [Claude Code 系统提示解析](https://github.com/Piebald-AI/claude-code-system-prompts)
- [Piebald 官网](https://piebald.ai/)

---

*最后更新：2026-03-19*
