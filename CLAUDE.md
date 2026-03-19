# Claude Code Cookbook

AI 可读取的资源库，帮助用户配置 Claude Code 环境。

## 使用方式

1. 根据用户需求，从下方表格找到合适的资源
2. 读取对应的详细文档（链接在表格中）
3. 按文档指引帮用户安装配置

---

## Skills（技能包）

可加载的技能配置，复制到 `~/.claude/skills/` 即可使用。

### 开发流程类

| Skill | 用途 | 适用场景 | 详情 |
|-------|------|---------|------|
| test-driven-development | TDD 工作流 | 写测试先行 | [skills/test-driven-development/](./skills/test-driven-development/) |
| systematic-debugging | 系统化调试 | Bug/测试失败时 | [skills/systematic-debugging/](./skills/systematic-debugging/) |
| verification-before-completion | 完成前验证 | 避免假成功 | [skills/verification-before-completion/](./skills/verification-before-completion/) |
| writing-plans | 写实现计划 | 复杂任务前 | [skills/writing-plans/](./skills/writing-plans/) |
| brainstorming | 创意发散 | 设计方案 | [skills/brainstorming/](./skills/brainstorming/) |

### 文档处理类

| Skill | 用途 | 适用场景 | 详情 |
|-------|------|---------|------|
| pdf | PDF 处理 | 读取/合并/拆分/OCR | [skills/pdf/](./skills/pdf/) |
| docx | Word 文档 | 创建/编辑 .docx | [skills/docx/](./skills/docx/) |
| pptx | PowerPoint | 演示文稿 | [skills/pptx/](./skills/pptx/) |
| xlsx | Excel 表格 | 电子表格处理 | [skills/xlsx/](./skills/xlsx/) |

---

## Commands（斜杠命令）

Claude Code 内置命令的使用说明。

| 命令 | 功能 | 使用场景 |
|------|------|---------|
| `/init` | 初始化项目，生成 CLAUDE.md | 在新目录下运行 |
| `@文件名` | 引用文件到上下文 | 输入 `@main.py` 或 `@src/` |
| `/model` | 切换模型 | Sonnet / Opus 切换 |
| `/status` | 查看状态 | Token 使用、模型、上下文 |
| `/compact` | 压缩上下文 | 自动摘要对话历史 |
| `Shift + Tab` | 切换模式 | 编码模式 ↔ 计划模式 |
| `/resume` | 恢复会话 | 网络波动后找回对话 |
| `/mcp` | 管理 MCP | 连接外部数据源 |
| `/skills` | 加载技能包 | 调用预设任务模板 |
| `/memory` | 管理长期记忆 | 查看/清除偏好 |

### 模型选择

| 模型 | 适用场景 |
|------|---------|
| Sonnet 4.5 | 日常开发，平衡速度与智能 |
| Opus 4.5 | 复杂任务，需要最强推理 |

---

## Tools（外部工具）

增强 Claude Code 体验的第三方工具。

| Tool | 一句话介绍 | 适用场景 | 详情 |
|------|-----------|---------|------|
| ccstatusline | 高级状态栏 | 显示 Token/花费/上下文 | [tools/ccstatusline.md](./tools/ccstatusline.md) |
| tweakcc | 美化定制 | 自定义主题/动画 | [tools/tweakcc.md](./tools/tweakcc.md) |
| cc-connect | 远程控制 | 手机远程操作 | [tools/cc-connect.md](./tools/cc-connect.md) |
| claudecodeui | Web 界面 | 桌面/移动端可视化 | [tools/claudecodeui.md](./tools/claudecodeui.md) |

---

## Agents（代理）

专用子代理配置（可选扩展）。

详见 [agents/README.md](./agents/README.md)

---

## 如何贡献

请阅读 [CONTRIBUTING.md](./CONTRIBUTING.md)
