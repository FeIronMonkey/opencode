# 6 Components

> **Purpose:** Navigation index for Part III component leaves (one package or T0 cluster per file). Not a behavioral contract.
> **Index:** [README.md](README.md)

Parent for [6.1](chapters/06.1-agent-cli.md)–[6.27](chapters/06.27-web.md). Cross-cutting layering lives in [3 Architecture](chapters/03-architecture.md) and [8 Domain model](chapters/08-domain-model.md).

| Chapter | Purpose |
|---------|---------|
| [6.1 Agent CLI](chapters/06.1-agent-cli.md) | Primary user CLI `opencode` and workspace `@opencode-ai/script` (one T0 cluster). |
| [6.2 Core](chapters/06.2-core.md) | Shipped `@opencode-ai/core` domain: Session V2, Location-scoped runner, process-global storage. |
| [6.3 SQLite adapters](chapters/06.3-sqlite-adapters.md) | Effect SQLite client and Drizzle Effect SQLite adapter packages. |
| [6.4 Protocol](chapters/06.4-protocol.md) | Effect `HttpApi` contract for instance routes (`@opencode-ai/protocol`). |
| [6.5 Server](chapters/06.5-server.md) | HTTP host for the Protocol `HttpApi` (`@opencode-ai/server`). |
| [6.6 HttpApi codegen](chapters/06.6-httpapi-codegen.md) | Build-time generator from an Effect `HttpApi` contract into HTTP client source. |
| [6.7 Client](chapters/06.7-client.md) | Generated Promise and Effect HTTP clients plus hand-authored generate inputs. |
| [6.8 Legacy JS SDK](chapters/06.8-sdk.md) | HTTP client facades, optional local server/TUI launchers, OpenAPI codegen for v2. |
| [6.9 SDK Next](chapters/06.9-sdk-next.md) | In-process host composing Client, Core, and Server without a network listener. |
| [6.10 LLM](chapters/06.10-llm.md) | Schema-first LLM core: request/event/tool language, provider routes, one-turn stream. |
| [6.11 HTTP recorder](chapters/06.11-http-recorder.md) | Record and replay Effect HTTP and WebSocket traffic from JSON cassettes. |
| [6.12 Plugin](chapters/06.12-plugin.md) | Plugin, tool, and TUI plugin type/helper exports (`@opencode-ai/plugin`). |
| [6.13 CodeMode](chapters/06.13-codemode.md) | Confined JavaScript execution over explicit, schema-described tools. |
| [6.14 TUI](chapters/06.14-tui.md) | Terminal UI: OpenTUI loop, keybinds, SDK-backed session UI, TUI plugin runtime. |
| [6.15 CLI (`lildax`)](chapters/06.15-cli.md) | Alternate CLI `@opencode-ai/cli`: `lildax` wrapper, daemon, TUI/API/serve handlers. |
| [6.16 Shared UI kit](chapters/06.16-ui.md) | SolidJS component library, themes, i18n, and shared UI contexts. |
| [6.17 Session UI](chapters/06.17-session-ui.md) | SolidJS library for transcript, diffs, markdown, review, and prompt input. |
| [6.18 App](chapters/06.18-app.md) | SolidJS web app UI: Vite shell, multi-server HTTP clients, session workspace. |
| [6.19 Desktop](chapters/06.19-desktop.md) | Electron shell hosting the web app UI and a local OpenCode backend. |
| [6.20 Enterprise](chapters/06.20-enterprise.md) | SolidStart enterprise app: session share APIs, object storage, public share viewer. |
| [6.21 Console app](chapters/06.21-console-app.md) | Cloud console SolidStart UI: marketing, billing, Zen/Go inference HTTP, webhooks. |
| [6.22 Console platform](chapters/06.22-console-platform.md) | Console core/function/mail/resource/support (one T0 cluster). |
| [6.23 Stats app](chapters/06.23-stats-app.md) | SolidStart public stats site at `/data/`. |
| [6.24 Stats backend](chapters/06.24-stats-backend.md) | `stats-core` + `stats-server`: lake ingest, stores, aggregation, read models. |
| [6.25 Function](chapters/06.25-function.md) | Cloudflare Worker for session sharing, support webhooks, and GitHub App tokens. |
| [6.26 Slack](chapters/06.26-slack.md) | Slack Socket Mode bot mapping channel threads to OpenCode sessions. |
| [6.27 Web](chapters/06.27-web.md) | Astro/Starlight docs/marketing site, share viewer, and plain-text doc export. |
