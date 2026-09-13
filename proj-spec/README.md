# OpenCode Specification — Chapter Index

Retrospective spec of **shipped** OpenCode behavior. Not a redesign. No `initial_spec.md`. Process notes: [slicing.md](slicing.md). Inbox: [open-questions.md](open-questions.md). Successor prompt: [HANDOFF.md](HANDOFF.md).

This README is navigation only. Product contracts live in `proj-spec/chapters/`. Parent indexes: [6 Components](06-components.md), [7 Interface](07-interface.md), [10 Operations](10-operations.md), [11 Examples](11-examples.md), [12 Testing](12-testing.md).

## How to use these chapters

- Read §1–§3 before writing product code.
- Implement along §6 in the dependency order recorded in Part II (§3 architecture, §9 design decisions), after REVIEW-SPEC and user spec-gate approval.
- Use §7–§8 for external API and schema contracts; §10 and §13 for install, generate, and performance.
- Validate with §11 examples, §12 test locations, and §14 for done-ness.

## Change history

| Topic | Spec | Plan | Log |
|-------|------|------|-----|
| *(none yet)* | | | |

## Status (2026-09-13)

Spec-only retrospective **closed**. REVIEW-SPEC r2 PASS (`reviews/opencode-spec-r2.md`, `c56aa9a3`, commit `41f8a7d85e`). User approved the spec gate 2026-09-13. **No implementation plan from this job** — do not start `@spec-driven-plan` or write `proj-spec/implementation-plan.md` from this README. Historical product code predates the spec (`#retrospective-migration`). Later behavior changes start `@spec-driven-change`. `HANDOFF.md` is a historical extra-review prompt, not current next steps.

## Part I — Product Definition

| Chapter | Title | Purpose |
|---------|-------|---------|
| [1](chapters/01-overview.md) | Overview | Product one-liner and shipped surfaces. |
| [2](chapters/02-goals.md) | Goals | Shipped product goals and explicit non-goals. |

## Part II — Design

| Chapter | Title | Purpose |
|---------|-------|---------|
| [3](chapters/03-architecture.md) | Architecture | Runtime layering Schema → Core/Protocol → Server, Client limits, sdk-next composition. |
| [4](chapters/04-stack.md) | Stack | Bun workspaces, Turbo pipeline, and workspace catalog pins. |
| [5](chapters/05-file-tree.md) | File tree | Workspace package paths (not a repository dump). |
| [9](chapters/09-design-decisions.md) | Design decisions | Recorded workspace layering and generate rules. |

## Part III — Components

Parent index: [6 Components](06-components.md).

| Chapter | Title | Purpose |
|---------|-------|---------|
| [6.1](chapters/06.1-agent-cli.md) | Agent CLI | Primary CLI `opencode` and `@opencode-ai/script`. |
| [6.2](chapters/06.2-core.md) | Core | `@opencode-ai/core` domain. |
| [6.3](chapters/06.3-sqlite-adapters.md) | SQLite adapters | Effect SQLite + Drizzle Effect SQLite adapters. |
| [6.4](chapters/06.4-protocol.md) | Protocol | `@opencode-ai/protocol` HttpApi contract. |
| [6.5](chapters/06.5-server.md) | Server | `@opencode-ai/server` HTTP host. |
| [6.6](chapters/06.6-httpapi-codegen.md) | HTTP API codegen | Build-time HttpApi client generator. |
| [6.7](chapters/06.7-client.md) | Client | Generated Effect/HTTP clients. |
| [6.8](chapters/06.8-sdk.md) | Legacy SDK | `@opencode-ai/sdk` HTTP facades and OpenAPI codegen. |
| [6.9](chapters/06.9-sdk-next.md) | SDK Next | In-process Client+Core+Server host. |
| [6.10](chapters/06.10-llm.md) | LLM | Schema-first LLM core. |
| [6.11](chapters/06.11-http-recorder.md) | HTTP recorder | HTTP record/replay. |
| [6.12](chapters/06.12-plugin.md) | Plugin | Plugin / tool / TUI plugin exports. |
| [6.13](chapters/06.13-codemode.md) | CodeMode | Confined code execution. |
| [6.14](chapters/06.14-tui.md) | TUI | Terminal UI. |
| [6.15](chapters/06.15-cli.md) | CLI | Alternate CLI `lildax`. |
| [6.16](chapters/06.16-ui.md) | UI kit | Shared UI kit (including generated assets). |
| [6.17](chapters/06.17-session-ui.md) | Session UI | Session transcript and prompt UI. |
| [6.18](chapters/06.18-app.md) | App | Web app UI. |
| [6.19](chapters/06.19-desktop.md) | Desktop | Electron desktop. |
| [6.20](chapters/06.20-enterprise.md) | Enterprise | Enterprise app. |
| [6.21](chapters/06.21-console-app.md) | Console app | Cloud console UI. |
| [6.22](chapters/06.22-console-platform.md) | Console platform | Console core/function/mail/resource/support. |
| [6.23](chapters/06.23-stats-app.md) | Stats app | Stats SolidStart site. |
| [6.24](chapters/06.24-stats-backend.md) | Stats backend | `stats-core` + `stats-server`. |
| [6.25](chapters/06.25-function.md) | Function | `@opencode-ai/function` worker. |
| [6.26](chapters/06.26-slack.md) | Slack | Slack bot. |
| [6.27](chapters/06.27-web.md) | Web | Astro/Starlight docs and marketing site. |

## Part IV — Interface

Parent index: [7 Interface](07-interface.md) (also lists §8).

| Chapter | Title | Purpose |
|---------|-------|---------|
| [7.1](chapters/07.1-http-api.md) | HTTP API | Public HTTP/`HttpApi` (generated trees are not source of truth). |
| [7.2](chapters/07.2-sdk-api.md) | SDK API | SDK export surface (legacy + next + client). |
| [7.3](chapters/07.3-cli.md) | CLI | CLI binaries and flags (`opencode`, `lildax`). |
| [7.4](chapters/07.4-plugin-api.md) | Plugin API | Plugin export surface. |
| [8](chapters/08-domain-model.md) | Domain model | `@opencode-ai/schema` domain/schema. |

## Part V — Operations

Parent index: [10 Operations](10-operations.md) (install and generate only). §13 is listed here, not as a child of §10.

| Chapter | Title | Purpose |
|---------|-------|---------|
| [10.1](chapters/10.1-install.md) | Install | Bins, desktop `main`, workspace install scripts. |
| [10.2](chapters/10.2-generate.md) | Generate | Regeneration commands (C5). |
| [13](chapters/13-performance.md) | Performance | Perf only where T0/T1 name it. |

## Part VI — Validation

Parent indexes: [11 Examples](11-examples.md), [12 Testing](12-testing.md).

| Chapter | Title | Purpose |
|---------|-------|---------|
| [11.1](chapters/11.1-surfaces.md) | Surface examples | Example entrypoints per T0 surface. |
| [12.1](chapters/12.1-workspace.md) | Workspace tests | Package test locations and `scripts.test` when known. |
| [14](chapters/14-acceptance.md) | Acceptance | Retrospective acceptance vs shipped surfaces. |
