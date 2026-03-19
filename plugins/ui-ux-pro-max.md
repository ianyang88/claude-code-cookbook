# UI/UX Pro Max

> AI 驱动的设计智能工具包 — 50+ 风格、161 色板、字体配对、图表类型、UX 指南

## 一句话介绍

UI/UX 设计数据库 + 搜索引擎，提供产品风格、配色、字体、图表、UX 最佳实践

## 适用场景

- 设计新界面或落地页
- 选择配色方案和字体
- 确定图表类型
- 避免常见的 UX 反模式

## 核心功能

### 🎨 设计资源库

| 领域 | 内容 |
|------|------|
| **产品类型** | SaaS、电商、作品集等推荐 |
| **UI 风格** | Glassmorphism、Minimalism、Brutalism 等 50+ |
| **配色方案** | 161 种色板，按产品类型分类 |
| **字体配对** | Google Fonts 导入代码 |
| **图表类型** | 图表选型和库推荐 |
| **UX 指南** | 最佳实践和反模式 |

### 🔍 搜索命令

```bash
python3 scripts/search.py "<query>" --domain <domain>
```

**领域搜索**：
- `product` - 产品类型推荐
- `style` - UI 风格 + AI 提示词 + CSS 关键词
- `typography` - 字体配对
- `color` - 配色方案
- `landing` - 页面结构和 CTA 策略
- `chart` - 图表类型
- `ux` - 最佳实践

**技术栈搜索**：
```bash
python3 scripts/search.py "<query>" --stack <stack>
```

支持：`html-tailwind`、`react`、`nextjs`、`vue`、`svelte`、`swiftui`、`react-native`、`flutter`、`shadcn`、`jetpack-compose`

### 🖥️ 多平台支持

- Claude Code
- Cursor
- Windsurf
- Droid (Factory)
- Continue

## 安装方式

### 方式一：Claude Marketplace

```
/plugins install ui-ux-pro-max
```

### 方式二：CLI 安装

```bash
npx uipro-cli init
```

### 方式三：手动安装

```bash
git clone https://github.com/AmberDarkDark/ui-ux-pro-max-skill.git
cp -r ui-ux-pro-max-skill/.claude/* ~/.claude/
```

## 使用示例

```
用户: 帮我设计一个 SaaS 产品的落地页

AI: [搜索产品类型和风格]
    [推荐配色方案]
    [推荐字体配对]
    [提供页面结构建议]
```

```
用户: 用 glassmorphism 风格，React + Tailwind 栈

AI: [搜索 glassmorphism 风格]
    [生成 React + Tailwind 代码]
    [包含相关 CSS 效果]
```

## 相关链接

- [GitHub 仓库](https://github.com/AmberDarkDark/ui-ux-pro-max-skill)
- [npm 包](https://www.npmjs.com/package/uipro-cli)

---

*版本: 2.0.1 | 最后更新: 2026-03*
