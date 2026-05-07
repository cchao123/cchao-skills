# Skills Backup

> Synced by [Skills Manager](https://github.com/cchao123/skills-managers) — a desktop app for managing AI coding agent skills.

## Use as a Claude Code marketplace

This repository is auto-generated as a [Claude Code plugin marketplace](https://docs.claude.com/en/docs/claude-code/plugin-marketplaces). Each skill below is exposed as an individually installable plugin.

In Claude Code, add this marketplace:

```bash
/plugin marketplace add cchao123/cchao-skills
```

Then install any skill you want:

```bash
/plugin install brainstorming@cchao-skills
```

Browse all available skills with `/plugin` after adding the marketplace, or see the full list in [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json).

## Skills (16)

| # | Skill | Description |
|---|-------|-------------|
| 1 | **brainstorming** | You MUST use this before any creative work - creating features, building components, adding functionality, or modifying behavior. Explores user intent, requirements and design before implementation. |
| 2 | **canvas** | A Cursor Canvas is a live React app that the user can open beside the chat. You MUST use a canvas when the agent produces a standalone analytical artifact — quantitative analyses, billing investigations, security audits, architecture reviews, data-heavy content, timelines, charts, tables, interactive explorations, repeatable tools, or any response that benefits from visual layout. Especially prefer a canvas when presenting results from MCP tools (Datadog, Databricks, Linear, Sentry, Slack, etc.) where the data is the deliverable — render it in a rich canvas rather than dumping it into a markdown table or code block. If you catch yourself about to write a markdown table, stop and use a canvas instead. You MUST also read this skill whenever you create, edit, or debug any .canvas.tsx file. |
| 3 | **commit** | 帮我提交代码，分析改动补充commit信息 |
| 4 | **create-skill** | Create Cursor Agent Skills. Use when authoring a new skill or asking about SKILL.md structure. |
| 5 | **figma** | Use the Figma MCP server to fetch design context, screenshots, variables, and assets from Figma, and to translate Figma nodes into production code. Trigger when a task involves Figma URLs, node IDs, design-to-code implementation, or Figma MCP setup and troubleshooting. |
| 6 | **find-skills** | Helps users discover and install agent skills when they ask questions like "how do I do X", "find a skill for X", "is there a skill that can...", or express interest in extending capabilities. This skill should be used when the user is looking for functionality that might exist as an installable skill. |
| 7 | **frontend-design** | Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to build web components, pages, artifacts, posters, or applications (examples include websites, landing pages, dashboards, React components, HTML/CSS layouts, or when styling/beautifying any web UI). Generates creative, polished code and UI design that avoids generic AI aesthetics. |
| 8 | **wxGZH** | 专业公众号内容创作专家，支持多平台文章写作（公众号/小红书/知乎等），提供从构思到成文的全流程服务。 基于传播学原理和新媒体运营实践，专注于创作具有传播力、高质量、自然流畅的内容。 核心功能包括：标题优化与吸引力提升、文章结构设计与逻辑梳理、语言润色与AI痕迹去除、 配图建议与视觉元素规划、传播性内容策划与话题挖掘。特色能力涵盖： 基于传播学原理的内容优化、真人化写作技巧（去除AI感）、多平台适配与风格转换、 数据驱动的热点捕捉、读者共情与情感连接。集成去AI痕迹技术， 确保内容自然流畅、富有感染力，帮助用户创作高质量的传播内容。  |
| 9 | **md-to-wechat** | 将本地 Markdown 文章渲染为微信公众号格式并一键推送到草稿箱的完整工作流。 当用户说"把这篇文章推到公众号"、"发布到微信公众号"、"推送草稿"、 "帮我发公众号"、"同步到公众号草稿箱"、"推到微信"等类似需求时， 必须主动使用此 skill，不要跳过。 使用 publish.cjs 一步完成渲染 + 推送，无需生成本地 HTML 文件。 需要 Node.js 18+，零外部依赖。 |
| 10 | **shadcn** | Manages shadcn components and projects — adding, searching, fixing, debugging, styling, and composing UI. Provides project context, component docs, and usage examples. Applies when working with shadcn/ui, component registries, presets, --preset codes, or any project with a components.json file. Also triggers for "shadcn init", "create an app with --preset", or "switch to --preset". |
| 11 | **split-to-prs** | Split current work into small reviewable PRs. Use when the user asks to split a chat, set of changes, branch, or PR. |
| 12 | **statusline** | Configure a custom status line in the CLI. Use when the user mentions status line, statusline, statusLine, CLI status bar, prompt footer customization, or wants to add session context above the prompt. |
| 13 | **update-cursor-settings** | Modify Cursor/VSCode user settings in settings.json. Use when you want to change editor settings, preferences, configuration, themes, font size, tab size, format on save, auto save, keybindings, or any settings.json values. |
| 14 | **vercel-react-best-practices** | React and Next.js performance optimization guidelines from Vercel Engineering. This skill should be used when writing, reviewing, or refactoring React/Next.js code to ensure optimal performance patterns. Triggers on tasks involving React components, Next.js pages, data fetching, bundle optimization, or performance improvements. |
| 15 | **wewrite** | 微信公众号内容全流程助手：热点抓取 → 选题 → 框架 → 内容增强 → 写作 → SEO → 视觉AI → 排版推送草稿箱。 触发关键词：公众号、推文、微信文章、微信推文、草稿箱、微信排版、选题、热搜、 热点抓取、封面图、配图、写公众号、写一篇、主题画廊、排版主题、容器语法。 也覆盖：markdown 转微信格式、学习用户改稿风格、文章数据复盘、风格设置、 主题预览/切换、:::dialogue/:::timeline/:::callout 容器语法。 不应被通用的"写文章"、blog、邮件、PPT、抖音/短视频、网站 SEO 触发—— 需要有公众号/微信等明确上下文。  |
| 16 | **wewrite** | 微信公众号内容全流程助手：热点抓取 → 选题 → 框架 → 内容增强 → 写作 → SEO → 视觉AI → 排版推送草稿箱。 触发关键词：公众号、推文、微信文章、微信推文、草稿箱、微信排版、选题、热搜、 热点抓取、封面图、配图、写公众号、写一篇、主题画廊、排版主题、容器语法。 也覆盖：markdown 转微信格式、学习用户改稿风格、文章数据复盘、风格设置、 主题预览/切换、:::dialogue/:::timeline/:::callout 容器语法。 不应被通用的"写文章"、blog、邮件、PPT、抖音/短视频、网站 SEO 触发—— 需要有公众号/微信等明确上下文。  |

