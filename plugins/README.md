# Plugins 插件

通过 Claude Marketplace 或手动安装的功能扩展包。

## 已收集的插件

| Plugin | 一句话介绍 | 适用场景 | 详情 |
|--------|-----------|---------|------|
| planning-with-files | 文件式规划系统 | 复杂任务、会话恢复 | [planning-with-files.md](./planning-with-files.md) |
| ui-ux-pro-max | UI/UX 设计工具包 | 界面设计、配色、字体 | [ui-ux-pro-max.md](./ui-ux-pro-max.md) |
| everything-claude-code | 50K+ Stars 综合优化包 | 进阶用户一步到位 | [everything-claude-code.md](./everything-claude-code.md) |

## 安装方式

### 方式一：Claude Marketplace

```
/plugins install <plugin-name>
```

### 方式二：手动安装

```bash
# 克隆插件仓库
git clone <plugin-repo>

# 复制到 Claude 配置目录
cp -r <plugin>/.claude/* ~/.claude/
```

### 方式三：告诉 AI 安装

```
帮我安装 planning-with-files 插件
```

## 插件 vs Skills

- **Skills**: 单个技能文件，放在 `~/.claude/skills/`
- **Plugins**: 功能包，可能包含 skills、commands、hooks 等多个组件

---

**欢迎推荐新插件！** 请阅读 [CONTRIBUTING.md](../CONTRIBUTING.md)。
