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
/plugin install azure-ai@cchao-skills
```

Browse all available skills with `/plugin` after adding the marketplace, or see the full list in [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json).

## Skills (27)

| # | Skill | Description |
|---|-------|-------------|
| 1 | **azure-ai** | Use for Azure AI: Search, Speech, OpenAI, Document Intelligence. Helps with search, vector/hybrid search, speech-to-text, text-to-speech, transcription, OCR. WHEN: AI Search, query search, vector search, hybrid search, semantic search, speech-to-text, text-to-speech, transcribe, OCR, convert text to speech. |
| 2 | **azure-aigateway** | Configure Azure API Management as an AI Gateway for AI models, MCP tools, and agents. WHEN: semantic caching, token limit, content safety, load balancing, AI model governance, MCP rate limiting, jailbreak detection, add Azure OpenAI backend, add AI Foundry model, test AI gateway, LLM policies, configure AI backend, token metrics, AI cost control, convert API to MCP, import OpenAPI to gateway. |
| 3 | **azure-deploy** | Execute Azure deployments for ALREADY-PREPARED applications that have existing .azure/deployment-plan.md and infrastructure files. DO NOT use this skill when the user asks to CREATE a new application — use azure-prepare instead. This skill runs azd up, azd deploy, terraform apply, and az deployment commands with built-in error recovery. Requires .azure/deployment-plan.md from azure-prepare and validated status from azure-validate. WHEN: "run azd up", "run azd deploy", "execute deployment", "push to production", "push to cloud", "go live", "ship it", "bicep deploy", "terraform apply", "publish to Azure", "launch on Azure". DO NOT USE WHEN: "create and deploy", "build and deploy", "create a new app", "set up infrastructure", "create and deploy to Azure using Terraform" — use azure-prepare for these. |
| 4 | **azure-kusto** | Query and analyze data in Azure Data Explorer (Kusto/ADX) using KQL for log analytics, telemetry, and time series analysis. WHEN: KQL queries, Kusto database queries, Azure Data Explorer, ADX clusters, log analytics, time series data, IoT telemetry, anomaly detection. |
| 5 | **azure-prepare** | Prepare Azure apps for deployment (infra Bicep/Terraform, azure.yaml, Dockerfiles). Use for create/modernize or create+deploy; not cross-cloud migration (use azure-cloud-migrate). DO NOT USE FOR: copilot-sdk apps (use azure-hosted-copilot-sdk). WHEN: "create app", "build web app", "create API", "create serverless HTTP API", "create frontend", "create back end", "build a service", "modernize application", "update application", "add authentication", "add caching", "host on Azure", "create and deploy", "deploy to Azure", "deploy to Azure using Terraform", "deploy to Azure App Service", "deploy to Azure App Service using Terraform", "deploy to Azure Container Apps", "deploy to Azure Container Apps using Terraform", "generate Terraform", "generate Bicep", "function app", "timer trigger", "service bus trigger", "event-driven function", "containerized Node.js app", "social media app", "static portfolio website", "todo list with frontend and API", "prepare my Azure application to use Key Vault", "managed identity". |
| 6 | **azure-resource-visualizer** | Analyze Azure resource groups and generate detailed Mermaid architecture diagrams showing the relationships between individual resources. WHEN: create architecture diagram, visualize Azure resources, show resource relationships, generate Mermaid diagram, analyze resource group, diagram my resources, architecture visualization, resource topology, map Azure infrastructure. |
| 7 | **brainstorming** | You MUST use this before any creative work - creating features, building components, adding functionality, or modifying behavior. Explores user intent, requirements and design before implementation. |
| 8 | **canvas** | A Cursor Canvas is a live React app that the user can open beside the chat. You MUST use a canvas when the agent produces a standalone analytical artifact — quantitative analyses, billing investigations, security audits, architecture reviews, data-heavy content, timelines, charts, tables, interactive explorations, repeatable tools, or any response that benefits from visual layout. Especially prefer a canvas when presenting results from MCP tools (Datadog, Databricks, Linear, Sentry, Slack, etc.) where the data is the deliverable — render it in a rich canvas rather than dumping it into a markdown table or code block. If you catch yourself about to write a markdown table, stop and use a canvas instead. You MUST also read this skill whenever you create, edit, or debug any .canvas.tsx file. |
| 9 | **commit** | 帮我提交代码，分析改动补充commit信息 |
| 10 | **create-skill** | Create Cursor Agent Skills. Use when authoring a new skill or asking about SKILL.md structure. |
| 11 | **figma** | Use the Figma MCP server to fetch design context, screenshots, variables, and assets from Figma, and to translate Figma nodes into production code. Trigger when a task involves Figma URLs, node IDs, design-to-code implementation, or Figma MCP setup and troubleshooting. |
| 12 | **find-skills** | Helps users discover and install agent skills when they ask questions like "how do I do X", "find a skill for X", "is there a skill that can...", or express interest in extending capabilities. This skill should be used when the user is looking for functionality that might exist as an installable skill. |
| 13 | **frontend-design** | Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to build web components, pages, artifacts, posters, or applications (examples include websites, landing pages, dashboards, React components, HTML/CSS layouts, or when styling/beautifying any web UI). Generates creative, polished code and UI design that avoids generic AI aesthetics. |
| 14 | **wxGZH** | 专业公众号内容创作专家，支持多平台文章写作（公众号/小红书/知乎等），提供从构思到成文的全流程服务。 基于传播学原理和新媒体运营实践，专注于创作具有传播力、高质量、自然流畅的内容。 核心功能包括：标题优化与吸引力提升、文章结构设计与逻辑梳理、语言润色与AI痕迹去除、 配图建议与视觉元素规划、传播性内容策划与话题挖掘。特色能力涵盖： 基于传播学原理的内容优化、真人化写作技巧（去除AI感）、多平台适配与风格转换、 数据驱动的热点捕捉、读者共情与情感连接。集成去AI痕迹技术， 确保内容自然流畅、富有感染力，帮助用户创作高质量的传播内容。  |
| 15 | **md-to-wechat** | 将本地 Markdown 文章渲染为微信公众号格式并一键推送到草稿箱的完整工作流。 当用户说"把这篇文章推到公众号"、"发布到微信公众号"、"推送草稿"、 "帮我发公众号"、"同步到公众号草稿箱"、"推到微信"等类似需求时， 必须主动使用此 skill，不要跳过。 使用 publish.cjs 一步完成渲染 + 推送，无需生成本地 HTML 文件。 需要 Node.js 18+，零外部依赖。 |
| 16 | **microsoft-foundry** | Deploy, evaluate, and manage Foundry agents end-to-end: Docker build, ACR push, hosted/prompt agent create, container start, batch eval, continuous eval, prompt optimizer workflows, agent.yaml, dataset curation from traces. USE FOR: deploy agent to Foundry, hosted agent, create agent, invoke agent, evaluate agent, run batch eval, continuous eval, continuous monitoring, continuous eval status, optimize prompt, improve prompt, prompt optimizer, optimize agent instructions, improve agent instructions, optimize system prompt, deploy model, Foundry project, RBAC, role assignment, permissions, quota, capacity, region, troubleshoot agent, deployment failure, create dataset from traces, dataset versioning, eval trending, create AI Services, Cognitive Services, create Foundry resource, provision resource, knowledge index, agent monitoring, customize deployment, onboard, availability. DO NOT USE FOR: Azure Functions, App Service, general Azure deploy (use azure-deploy), general Azure prep (use azure-prepare). |
| 17 | **remotion-best-practices** | Best practices for Remotion - Video creation in React |
| 18 | **shadcn** | Manages shadcn components and projects — adding, searching, fixing, debugging, styling, and composing UI. Provides project context, component docs, and usage examples. Applies when working with shadcn/ui, component registries, presets, --preset codes, or any project with a components.json file. Also triggers for "shadcn init", "create an app with --preset", or "switch to --preset". |
| 19 | **split-to-prs** | Split current work into small reviewable PRs. Use when the user asks to split a chat, set of changes, branch, or PR. |
| 20 | **statusline** | Configure a custom status line in the CLI. Use when the user mentions status line, statusline, statusLine, CLI status bar, prompt footer customization, or wants to add session context above the prompt. |
| 21 | **tong-jincheng-perspective** | 童锦程视角：以"深情祖师爷"、直播情感内容创作者的思维框架看待人际关系、社会动态与个人成长。 素材来源：9个一手视频字幕（直播/约会vlog/搭讪解析），约20万字。 核心模型：5个。决策启发式：9条。 触发词：「童锦程」「深情祖师爷」「用童锦程的方式」「从童锦程视角」「景辰怎么看」 局限：素材以情感/人际内容为主，商业/创业思维数据不足，慎用于纯商业决策场景。 调研时间：2026年4月。 |
| 22 | **update-cursor-settings** | Modify Cursor/VSCode user settings in settings.json. Use when you want to change editor settings, preferences, configuration, themes, font size, tab size, format on save, auto save, keybindings, or any settings.json values. |
| 23 | **vercel-react-best-practices** | React and Next.js performance optimization guidelines from Vercel Engineering. This skill should be used when writing, reviewing, or refactoring React/Next.js code to ensure optimal performance patterns. Triggers on tasks involving React components, Next.js pages, data fetching, bundle optimization, or performance improvements. |
| 24 | **web-design-guidelines** | Review UI code for Web Interface Guidelines compliance. Use when asked to "review my UI", "check accessibility", "audit design", "review UX", or "check my site against best practices". |
| 25 | **wewrite** | 微信公众号内容全流程助手：热点抓取 → 选题 → 框架 → 内容增强 → 写作 → SEO → 视觉AI → 排版推送草稿箱。 触发关键词：公众号、推文、微信文章、微信推文、草稿箱、微信排版、选题、热搜、 热点抓取、封面图、配图、写公众号、写一篇、主题画廊、排版主题、容器语法。 也覆盖：markdown 转微信格式、学习用户改稿风格、文章数据复盘、风格设置、 主题预览/切换、:::dialogue/:::timeline/:::callout 容器语法。 不应被通用的"写文章"、blog、邮件、PPT、抖音/短视频、网站 SEO 触发—— 需要有公众号/微信等明确上下文。  |
| 26 | **wewrite** | 微信公众号内容全流程助手：热点抓取 → 选题 → 框架 → 内容增强 → 写作 → SEO → 视觉AI → 排版推送草稿箱。 触发关键词：公众号、推文、微信文章、微信推文、草稿箱、微信排版、选题、热搜、 热点抓取、封面图、配图、写公众号、写一篇、主题画廊、排版主题、容器语法。 也覆盖：markdown 转微信格式、学习用户改稿风格、文章数据复盘、风格设置、 主题预览/切换、:::dialogue/:::timeline/:::callout 容器语法。 不应被通用的"写文章"、blog、邮件、PPT、抖音/短视频、网站 SEO 触发—— 需要有公众号/微信等明确上下文。  |
| 27 | **wonda-cli** | Using the Wonda CLI to generate images, videos, music, and audio from the terminal — plus LinkedIn, Reddit, and X/Twitter research and automation |

