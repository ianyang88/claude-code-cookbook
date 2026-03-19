# Skills 技能包

可加载的 Claude Code 技能配置。复制到 `~/.claude/skills/` 目录即可使用。

## 开发流程类

| Skill | 用途 | 详情 |
|-------|------|------|
| test-driven-development | TDD 工作流，写测试先行 | [test-driven-development/](./test-driven-development/) |
| systematic-debugging | 系统化调试，找根因再修复 | [systematic-debugging/](./systematic-debugging/) |
| verification-before-completion | 完成前强制验证 | [verification-before-completion/](./verification-before-completion/) |
| writing-plans | 写详细实现计划 | [writing-plans/](./writing-plans/) |
| brainstorming | 创意发散，设计方案 | [brainstorming/](./brainstorming/) |

## 协作开发类

| Skill | 用途 | 详情 |
|-------|------|------|
| subagent-driven-development | 多子代理并行执行任务 | [subagent-driven-development/](./subagent-driven-development/) |

## 文档处理类

| Skill | 用途 | 详情 |
|-------|------|------|
| pdf | PDF 读取/合并/拆分/OCR | [pdf/](./pdf/) |
| docx | Word 文档创建/编辑 | [docx/](./docx/) |
| pptx | PowerPoint 演示文稿 | [pptx/](./pptx/) |
| xlsx | Excel 电子表格 | [xlsx/](./xlsx/) |

## 工具类

| Skill | 用途 | 详情 |
|-------|------|------|
| skill-creator | 创建新 skill 的指南 | [skill-creator/](./skill-creator/) |
| web-artifacts-builder | 构建 claude.ai HTML artifacts | [web-artifacts-builder/](./web-artifacts-builder/) |

## 安装方式

```bash
# 复制整个目录到全局 skills
cp -r skills/* ~/.claude/skills/
```

或告诉 AI："帮我安装这些 skills"

---

**来源**：这些 skills 来自 Claude Code 官方和社区。
