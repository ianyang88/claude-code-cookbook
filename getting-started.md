# 快速上手指南

> 5 分钟让你的 Claude Code 脱胎换骨

---

## 必做级（5 分钟）

### 1. 安装高级状态栏

效果：终端底部实时显示模型名、Token 用量、花费、Git 分支、上下文占用等。

```bash
npx -y ccstatusline@latest
```

启动后按 `a` 添加小部件，选择 "Install to Claude Code settings"，重启 Claude Code 即可。

### 2. 掌握黄金工作流

```
探索 → 规划 → 执行
```

- 不要上来就说"帮我写个登录功能"
- 先让 Claude 探索现有代码
- 再规划方案
- 最后执行

### 3. 记住这些命令

| 命令 | 何时用 |
|------|--------|
| `/compact` | 对话太长时压缩 |
| `Shift+Tab` | 切换编码/规划模式 |
| `@文件名` | 把文件加入上下文 |

---

## 推荐级（15 分钟）

### 4. 美化你的终端

```bash
npx tweakcc
```

可以换主题颜色、自定义思考动画、创建工具集减少 token 消耗。

### 5. 加载开发技能包

将以下 skill 复制到 `~/.claude/skills/`：

| Skill | 帮你做什么 |
|-------|-----------|
| test-driven-development | 先写测试再写代码 |
| systematic-debugging | 遇到 bug 时系统化排查 |
| writing-plans | 复杂任务前先写计划 |

---

## 按需级（特定场景）

### 我要远程用 Claude Code

```bash
npm install -g cc-connect
```

在飞书、钉钉、Telegram 等平台远程控制 Claude Code。详见 [cc-connect](./tools/cc-connect.md)

### 我要 Web 界面

```bash
npx @cloudcli-ai/cloudcli
```

浏览器打开 `http://localhost:3001`，支持桌面和移动端。详见 [CloudCLI](./tools/claudecodeui.md)

### 我要处理文档

| 类型 | Skill | 能做什么 |
|------|-------|---------|
| PDF | [pdf](./skills/pdf/) | 读取、合并、拆分、OCR |
| Word | [docx](./skills/docx/) | 创建、编辑 .docx |
| PPT | [pptx](./skills/pptx/) | 创建演示文稿 |
| Excel | [xlsx](./skills/xlsx/) | 电子表格处理 |

复制对应 skill 到 `~/.claude/skills/` 即可。

### 我要做 UI 设计

安装 [ui-ux-pro-max](./plugins/ui-ux-pro-max.md) 插件，获得配色、字体、布局辅助。

---

## 完整资源列表

详见 [CLAUDE.md](./CLAUDE.md)
