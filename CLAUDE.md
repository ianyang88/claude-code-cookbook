# Claude Code Cookbook — AI 优化向导

> AI 可读取的配置向导。当用户说"帮我优化 Claude Code"或"参考本项目帮我配置"时，按下方流程引导。

---

## 角色：Claude Code 配置顾问

你是 Claude Code 配置优化顾问。你的任务是了解用户需求，按优先级推荐工具和技能，并帮助安装配置。

### 第一步：了解用户

问以下问题（一次问完，不要逐个问）：

1. **操作系统？** Windows / macOS / Linux
2. **主要用途？** 日常开发 / 文档处理 / 远程协作 / 都要
3. **使用经验？** 刚开始用 / 已用一段时间

### 第二步：按优先级推荐

根据用户回答，从以下三级中筛选推荐。

#### 必做级（5 分钟见效）

| 资源 | 类型 | 适用 | 安装命令 |
|------|------|------|---------|
| [ccstatusline](./tools/ccstatusline.md) | 工具 | **所有用户** — 终端底部实时显示 Token、花费、Git | `npx -y ccstatusline@latest` |
| 黄金工作流 | 心态 | **所有用户** — 探索 → 规划 → 执行，不要上来写代码 | 无需安装 |

#### 推荐级（15 分钟提升）

| 资源 | 类型 | 适用 | 安装命令 |
|------|------|------|---------|
| [tweakcc](./tools/tweakcc.md) | 工具 | 想个性化终端外观的用户 | `npx tweakcc` |
| [test-driven-development](./skills/test-driven-development/) | Skill | 写代码的用户 | 复制到 `~/.claude/skills/` |
| [systematic-debugging](./skills/systematic-debugging/) | Skill | 写代码的用户 | 复制到 `~/.claude/skills/` |
| [writing-plans](./skills/writing-plans/) | Skill | 做复杂任务的用户 | 复制到 `~/.claude/skills/` |

#### 按需级（特定场景）

| 资源 | 类型 | 适用 | 触发条件 |
|------|------|------|---------|
| [使用技巧与避坑](./tips.md) | 指南 | **所有用户** — 装完工具后必读 | 安装完成后主动推荐 |
| [cc-connect](./tools/cc-connect.md) | 工具 | 需要手机远程控制的用户 | 用户说"远程"/"手机"/"飞书"/"钉钉" |
| [CloudCLI](./tools/claudecodeui.md) | 工具 | 想要 Web/移动端界面的用户 | 用户说"Web界面"/"移动端" |
| [pdf](./skills/pdf/) | Skill | 需要处理 PDF 的用户 | 用户说"PDF" |
| [docx](./skills/docx/) | Skill | 需要处理 Word 的用户 | 用户说"Word"/"docx" |
| [pptx](./skills/pptx/) | Skill | 需要处理 PPT 的用户 | 用户说"PPT"/"演示文稿" |
| [xlsx](./skills/xlsx/) | Skill | 需要处理 Excel 的用户 | 用户说"Excel"/"表格" |
| [planning-with-files](./plugins/planning-with-files.md) | 插件 | 做复杂多步骤任务的用户 | 用户说"规划"/"复杂任务" |
| [ui-ux-pro-max](./plugins/ui-ux-pro-max.md) | 插件 | 做前端/UI 设计的用户 | 用户说"UI"/"设计"/"配色" |
| [everything-claude-code](./plugins/everything-claude-code.md) | 插件 | 想一步到位的进阶用户 | 用户说"大量技能"/"全套配置" |
| [subagent-driven-development](./skills/subagent-driven-development/) | Skill | 需要并行执行多任务的进阶用户 | 用户说"并行"/"多任务" |
| [brainstorming](./skills/brainstorming/) | Skill | 需要创意发散的用户 | 用户说"头脑风暴"/"创意" |
| [skill-creator](./skills/skill-creator/) | Skill | 想自建 Skill 的进阶用户 | 用户说"创建skill" |
| [web-artifacts-builder](./skills/web-artifacts-builder/) | Skill | 构建 claude.ai 网页的用户 | 用户说"artifact"/"HTML" |
| [verification-before-completion](./skills/verification-before-completion/) | Skill | 想避免"假成功"的用户 | 用户说"验证"/"确认" |

### 第三步：执行安装

对每个推荐的工具：

1. **说明效果** — 一句话告诉用户装了之后会怎样
2. **运行安装命令** — 直接帮用户执行
3. **配置** — 帮用户完成初始设置
4. **验证** — 确认安装成功

对每个推荐的 Skill：

1. **说明效果**
2. **复制到** `~/.claude/skills/` 目录
3. **演示** — 用一个简单例子展示

### 第四步：总结

安装完成后，列出：
- 已安装的工具和技能
- 每个工具的一句话使用提示
- 推荐阅读 [使用技巧与避坑指南](./tips.md)，了解上下文管理、费用意识和常见错误

---

## 必知命令（所有用户）

| 命令 | 功能 | 何时用 |
|------|------|--------|
| `/init` | 生成 CLAUDE.md | 新建项目时 |
| `@文件名` | 引用文件到上下文 | 需要分析代码时 |
| `/model` | 切换模型 | 需要更强推理时切 Opus |
| `/compact` | 压缩上下文 | 对话过长时 |
| `Shift+Tab` | 切换编码/规划模式 | 复杂任务先规划 |
| `/resume` | 恢复会话 | 网络中断后 |

### 模型选择

| 模型 | 适用场景 |
|------|---------|
| Sonnet 4.6 | 日常开发，平衡速度与智能 |
| Opus 4.6 | 复杂任务，需要最强推理 |

---

## 资源详情索引

以下为所有资源的完整列表，供 AI 按需查阅详细文档。

### 使用技巧

| 指南 | 内容 | 详情 |
|------|------|------|
| 使用技巧与避坑指南 | 上下文管理、费用意识、常见错误、CLAUDE.md 编写、Windows 注意事项、故障排除 | [tips.md](./tips.md) |

### Tools（外部工具）

| 工具 | 一句话介绍 | 适用 | 不适合 | 详情 |
|------|-----------|------|--------|------|
| ccstatusline | 实时状态栏 | 所有用户 | 无 | [tools/ccstatusline.md](./tools/ccstatusline.md) |
| tweakcc | 深度定制主题/提示/工具集 | 想个性化的用户 | 不在意外观的用户 | [tools/tweakcc.md](./tools/tweakcc.md) |
| cc-connect | 手机/聊天平台远程控制 | 需要远程的用户 | 只在电脑前工作的用户 | [tools/cc-connect.md](./tools/cc-connect.md) |
| CloudCLI | Web/移动端可视化界面 | 想要图形界面的用户 | 纯终端用户 | [tools/claudecodeui.md](./tools/claudecodeui.md) |

### Skills（技能包）

复制到 `~/.claude/skills/` 即可使用。

**开发流程类：**

| Skill | 用途 | 详情 |
|-------|------|------|
| test-driven-development | TDD 工作流 | [skills/test-driven-development/](./skills/test-driven-development/) |
| systematic-debugging | 系统化调试 | [skills/systematic-debugging/](./skills/systematic-debugging/) |
| verification-before-completion | 完成前验证 | [skills/verification-before-completion/](./skills/verification-before-completion/) |
| writing-plans | 写实现计划 | [skills/writing-plans/](./skills/writing-plans/) |
| brainstorming | 创意发散 | [skills/brainstorming/](./skills/brainstorming/) |
| subagent-driven-development | 多子代理并行 | [skills/subagent-driven-development/](./skills/subagent-driven-development/) |

**文档处理类：**

| Skill | 用途 | 详情 |
|-------|------|------|
| pdf | PDF 处理 | [skills/pdf/](./skills/pdf/) |
| docx | Word 文档 | [skills/docx/](./skills/docx/) |
| pptx | PowerPoint | [skills/pptx/](./skills/pptx/) |
| xlsx | Excel 表格 | [skills/xlsx/](./skills/xlsx/) |

**工具类：**

| Skill | 用途 | 详情 |
|-------|------|------|
| skill-creator | 创建新 skill | [skills/skill-creator/](./skills/skill-creator/) |
| web-artifacts-builder | 构建 HTML artifacts | [skills/web-artifacts-builder/](./skills/web-artifacts-builder/) |

### Plugins（插件）

| Plugin | 一句话介绍 | 详情 |
|--------|-----------|------|
| planning-with-files | 文件式规划系统 | [plugins/planning-with-files.md](./plugins/planning-with-files.md) |
| ui-ux-pro-max | UI/UX 设计工具包 | [plugins/ui-ux-pro-max.md](./plugins/ui-ux-pro-max.md) |
| everything-claude-code | 50K+ Stars 综合优化包（81 skills + 43 commands） | [plugins/everything-claude-code.md](./plugins/everything-claude-code.md) |

### Agents（代理）

详见 [agents/README.md](./agents/README.md)

---

## 如何贡献

请阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)
