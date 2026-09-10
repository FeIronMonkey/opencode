# 8 Domain model

> **Spec chapter:** Shipped `@opencode-ai/schema` wire and storage contracts (retrospective).
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**File:** `packages/schema/` (`packages/schema/src/index.ts`, `packages/schema/package.json`)

This chapter is a **retrospective** description of shipped Schema behavior (C8). Canonical home for the `@opencode-ai/schema` package, including `EventManifest` inventories and event types. Runtime services and UI live in other chapters; HTTP SSE payload unions for `/api/event` and `/api/session/:sessionID/event` are [7.1 HTTP API](07.1-http-api.md). This leaf owns serializable contracts only.

T1 assigns `@opencode-ai/schema` to this leaf only (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §2). The name `schema` also appears on T1’s **multi-leaf packages** consistency token because other leaves consume it (`T1-chapter-map.md` §7).

## Construction / configuration

| Parameter | Default / shipped value | Notes |
|-----------|-------------------------|-------|
| npm name | `@opencode-ai/schema` | `packages/schema/package.json` `name` |
| private | `true` | `packages/schema/package.json` `private` |
| module type | `"module"` | `packages/schema/package.json` `type` |
| license | `MIT` | `packages/schema/package.json` `license` |
| export `.` | `./src/index.ts` | `packages/schema/package.json` `exports["."]` |
| export `./*` | `./src/*.ts` | `packages/schema/package.json` `exports["./*"]` — specialized modules (manifests, V1 wrappers, event modules) are imported by subpath, not as first-class root barrel members (`packages/schema/AGENTS.md` Package Boundary; `packages/schema/src/index.ts`) |
| runtime dependencies | `effect` only (`catalog:`) | `packages/schema/package.json` `dependencies` — Schema does not declare Core, Protocol, or Server |
| scripts | `typecheck`: `tsgo --noEmit` | `packages/schema/package.json` `scripts` |
| generated-in-slice | no | task spec; T1 §2 `generated?` = no for this package |

**Dependency direction (C6).** Runtime dependencies are directed from Schema to Core and Protocol, then from Core and Protocol to Server. Client runtime code may depend on Schema and Protocol but never Core or Server; sdk-next composes Client, Core, and Server (`AGENTS.md`). Schema’s own package guide states `@opencode-ai/schema <- @opencode-ai/protocol <- @opencode-ai/server` (`packages/schema/AGENTS.md` Package Boundary). T1 **dep direction** token matches those phrases (`T1-chapter-map.md` §7). T1 consume edges for this leaf: 8 is consumed by 3, 6.2, 6.4, 6.7, 6.10, 6.18; 6.1 depends on 8 (`T1-chapter-map.md` §6).

**Role.** `@opencode-ai/schema` owns browser-safe wire and storage contracts shared by protocol, server, core, and generated SDKs. Schema values are serializable contract definitions, not service implementations or runtime registries (`packages/schema/AGENTS.md` Package Boundary).

## Behavior

### Package boundary and barrel

The root barrel exports canonical current domain namespaces plus prompt helpers and schema combinators (`packages/schema/src/index.ts`): `Agent`, `Command`, `Connection`, `Credential`, `Event`, `FileSystem`, `Integration`, `LLM`, `Location`, `Model`, `Permission`, `PermissionSaved`, `Project`, `ProjectCopy`, `Provider`, `Reference`, `Revert`, `Session`, `SessionInput`, `SessionMessage`, `Skill`, `Pty`, `PtyTicket`, `Question`, `Workspace`, `Prompt` / `Source` / `FileAttachment` / `AgentAttachment`, `PromptInput`, and `export *` from `packages/schema/src/schema.ts`.

Specialized event modules, manifests, infrastructure modules, and V1 contracts use direct entrypoints instead of becoming first-class root exports (`packages/schema/AGENTS.md` Package Boundary). Examples in tree: `EventManifest` (`packages/schema/src/event-manifest.ts`), `DurableEventManifest` (`packages/schema/src/durable-event-manifest.ts`), `Plugin` (`packages/schema/src/plugin.ts`), `SessionTodo` (`packages/schema/src/session-todo.ts`), `SessionEvent` (`packages/schema/src/session-event.ts`), `IdeEvent` (`packages/schema/src/ide-event.ts`).

`Session.Event` is the same value as `SessionEvent`; `Workspace.Event` is the same value as `WorkspaceEvent` (`packages/schema/src/session.ts`, `packages/schema/src/workspace.ts`; `packages/schema/test/event-manifest.test.ts` `uses canonical definitions for current public events`).

A domain may keep a minimal public wire contract in Schema when SDK generation needs it without moving the broader runtime model here. Shipped example: `plugin.added` payload is `{ id: Plugin.ID }` only (`packages/schema/src/plugin.ts` `Event.Added`; `packages/schema/AGENTS.md` Package Boundary).

### Combinators and scalar schemas

`packages/schema/src/schema.ts` ships:

| Export | Behavior |
|--------|----------|
| `PositiveInt` | `Schema.Int` greater than 0 |
| `NonNegativeInt` | `Schema.Int` greater than or equal to 0 |
| `RelativePath` / `AbsolutePath` | branded strings |
| `optional(schema)` | optional object key; encode **omits** keys whose value is `undefined` |
| `statics(methods)` | `Object.assign` of methods onto a schema value |
| `DateTimeUtcFromMillis` | finite number ↔ UTC DateTime via epoch millis |

`optional` preserves inner codec transformations: decode `{ value: "1" }` with `optional(Schema.FiniteFromString)` yields `{ value: 1 }`; encode `{ value: 1 }` yields `{ value: "1" }`; encode `{ value: undefined }` yields `{}` (`packages/schema/test/contract-hygiene.test.ts` `optional properties preserve transformations and omit undefined while encoding`; `packages/schema/src/schema.ts` `optional`).

Package guide: use package `optional(...)` so encoded objects omit `undefined` keys; use raw `Schema.optional(...)` only when preserving encoded `undefined` is intentional (`packages/schema/AGENTS.md` Optional Fields And Defaults). Public Schema contracts are readonly by default; current top-level `src/*.ts` sources (excluding `*-v1.ts`) do not contain `Schema.Any` or `Schema.mutable` (`packages/schema/AGENTS.md` Mutability / Unknown Values; `packages/schema/test/contract-hygiene.test.ts` `current source avoids Any and mutable contract wrappers`).

Public `Schema.Struct` records use same-name interfaces (`export interface Info extends Schema.Schema.Type<typeof Info> {}`) (`packages/schema/AGENTS.md` Public Types; e.g. `Session.Info` in `packages/schema/src/session.ts`).

`FileSystem.FindInput` remains a constructible Effect Schema class (`new FileSystem.FindInput({ query: "src" })`) (`packages/schema/src/filesystem.ts`; `packages/schema/test/compatibility.test.ts` `moved class schemas remain constructible`).

### Identifiers

`packages/schema/src/identifier.ts` `create(descending, timestamp = Date.now())` builds a 26-character id. It computes `const current = BigInt(timestamp) * 0x1000n + BigInt(counter)`, then `const value = descending ? ~current : current`, then 12 hex digits from `value` (`(value >> BigInt(40 - 8 * index)) & 0xffn` for `index` 0–5), then `length - 12` random chars from `chars`. `ascending()` is `create(false)`; `descending()` is `create(true)`. Same-millisecond calls increment `counter`. Session IDs call `descending()`, so their 12 hex digits encode `~current`, not `current` (`packages/schema/src/session-id.ts` `create`; `packages/schema/src/identifier.ts` `create`).

Current ID constructors expose `create()` (`packages/schema/AGENTS.md` IDs And Identifiers). Shipped examples: `Question.ID.create()` starts with `que_`; `Pty.ID.create()` starts with `pty_` (`packages/schema/test/contract-hygiene.test.ts` `current ID constructors expose create`). Decode prefix checks: `Question.ID` `Schema.isStartsWith("que")`, `Pty.ID` `"pty"`, `SessionID` `"ses"`, `Permission.ID` `"per"` (underscore **not** required); `Event.ID` `Schema.isStartsWith("evt_")` (underscore **required**) (`packages/schema/src/question.ts`, `pty.ts`, `session-id.ts`, `permission.ts`, `event.ts` `ID`). Constructors emit `que_`, `pty_`, `ses_`, `per_`, `evt_`. `SessionID.create` uses `descending()`; `Question.ID` / `Pty.ID` / `Event.ID` use `ascending()`.

`SessionID.descending(id?)` and `Question.ID.ascending(id?)` / `Pty.ID.ascending(id?)` reuse `create()` when `id` is omitted, otherwise `schema.make(id)` (`packages/schema/src/session-id.ts`, `question.ts`, `pty.ts`). `Permission.ID.create(id?)` uses `id ?? "per_" + ascending()` (`packages/schema/src/permission.ts`).

Reusable exported public schemas carry stable unique `identifier` annotations. The hygiene test requires these identifiers to be strings and unique: `Agent.Color`, `FileSystem.Submatch`, `Model.Ref`, `Model.Capabilities`, `Model.Cost`, `Model.Api`, `Project.Icon`, `Project.Commands`, `Project.Time`, `Project.Info`, `Pty.Info`, `Session.ListAnchor` (`packages/schema/test/contract-hygiene.test.ts` `reusable public identifiers are stable and unique`).

Some current brands still use `V2` in identifiers (shipped, not a refactor requirement): `Session.Info` annotates `"SessionV2.Info"` (`packages/schema/src/session.ts`); `Question.ID` brand `"QuestionV2.ID"`; `Agent.ID` `"AgentV2.ID"`; `Model.ID` `"ModelV2.ID"`; `Permission.ID` `"PermissionV2.ID"`.

### Current versus V1

Current contracts are unversioned names (`Session`, `Permission`, `Question`). Legacy contracts retained for compatibility use explicit `V1` names (`SessionV1`, `PermissionV1`, `QuestionV1`) (`packages/schema/AGENTS.md` Current Versus V1).

Retained V1 implementations live under `packages/schema/src/v1/`. Compatibility entrypoints re-export the isolated modules and **are the same identity**:

| Compatibility module | Isolated module |
|----------------------|-----------------|
| `packages/schema/src/legacy-event.ts` | `packages/schema/src/v1/legacy-event.ts` |
| `packages/schema/src/permission-v1.ts` | `packages/schema/src/v1/permission.ts` |
| `packages/schema/src/question-v1.ts` | `packages/schema/src/v1/question.ts` |
| `packages/schema/src/session-v1.ts` | `packages/schema/src/v1/session.ts` |

(`packages/schema/test/v1-isolation.test.ts` `compatibility entrypoints preserve isolated V1 schema identity`)

Current top-level `src/*.ts` files other than those four wrappers MUST NOT contain `from "./v1/"` (`packages/schema/test/v1-isolation.test.ts` `current source does not import the V1 subtree directly`). `Schema.Any` appears in `packages/schema/src/v1/session.ts` (legacy JSON/metadata fields); the current-source hygiene scan does not include `src/v1/` or `*-v1.ts`.

### Event algebra

`Event.define` builds a struct with `id` (`Event.ID`, brand `Event.ID`, `create` → `"evt_" + ascending()`), optional `metadata` (`Record<string, unknown>` via package `optional`), literal `type`, optional `durable` `{ aggregateID, seq, version }`, optional `location` (`Location.Ref`), and `data` from the input field codecs. The returned schema is annotated with `identifier: input.type` and statics `type`, optional definition-level `durable: { version, aggregate }`, and `data` (`packages/schema/src/event.ts` `define`).

`Event.inventory(...definitions)` returns `Object.freeze(definitions)` (`packages/schema/src/event.ts` `inventory`). Calling `define` after `inventory()` does not mutate the frozen list (`packages/schema/test/event.test.ts` `definition is pure`).

`Event.latest(definitions)` keeps one definition per `type`: if both have `durable` and versions differ, the **higher** `durable.version` wins regardless of array order (`packages/schema/test/event.test.ts` `latest selection is independent of declaration order`; `packages/schema/src/event.ts` `latest`).

`Event.versionedType(type, version)` is `` `${type}.${version}` ``. `Event.durable(definitions)` indexes definitions that have `durable` by that key (`packages/schema/test/event.test.ts` `durable definitions are indexed by type and version`).

### Event manifests

`EventManifest.ServerDefinitions` length is **55**. `EventManifest.Definitions` length is **85**. `EventManifest.Latest.size` is **85**. `EventManifest.Durable.size` is **32** (`packages/schema/test/event-manifest.test.ts` `owns the complete public event surface`; `packages/schema/src/event-manifest.ts`).

`ServerDefinitions` is `foundationDefinitions` + `featureDefinitions` + `SessionTodo.Event.Definitions` (no V1 live session events, installation, LSP, PermissionV1, TUI, MCP, LegacyEvent, Project.Event, session status, QuestionV1, compaction, VCS, workspace, worktree, or ServerEvent extras that appear only on the full list, including Schema `ServerEvent.Connected` / `server.connected`) (`packages/schema/src/event-manifest.ts`). The HTTP synthetic `server.connected` variant on `/api/event` is [7.1 HTTP API](07.1-http-api.md), not a second inventory here.

`Definitions` concatenates foundation, SessionV1 **live** (non-durable) definitions, installation, feature, todos, LSP, PermissionV1, TUI, MCP, LegacyEvent, Project, session status, QuestionV1, compaction, VCS, workspace, worktree, ServerEvent (`packages/schema/src/event-manifest.ts` `Definitions`).

`EventManifest.Latest` is `Event.latest(Definitions)`. `EventManifest.Durable` is `DurableEventManifest.Durable`: durable SessionV1 event definitions plus `SessionEvent.DurableDefinitions` (`packages/schema/src/event-manifest.ts`; `packages/schema/src/durable-event-manifest.ts`).

Canonical lookups (`packages/schema/test/event-manifest.test.ts` `uses canonical definitions for current public events`):

| Key / surface | Value |
|---------------|--------|
| `Latest.get("session.next.step.ended")` | `SessionEvent.Step.Ended` |
| `Latest.get("todo.updated")` | `SessionTodo.Event.Updated` |
| `Latest.get("project.updated")` | `Project.Event.Updated` |
| `Project.Event.Definitions` | `[Project.Event.Updated]` |
| `FileSystem.Event.Definitions` | `[FileSystem.Event.Edited]` |
| `Integration.Event.Definitions` | `[Updated, ConnectionUpdated]` |
| `Permission.Event.Definitions` | `[Asked, Replied]` |
| `Reference.Event.Definitions` | `[Updated]` |
| `Latest.has("ide.installed")` | `false` |
| `IdeEvent.Definitions` | `[IdeEvent.Installed]` (not on the public Latest map) |
| `Definitions.slice(40, 43)` | `SessionV1.Event.PartDelta`, `Diff`, `Error` |
| `Durable.has("session.next.step.ended.1")` | `false` |
| `Durable.get("session.next.step.ended.2")` | `SessionEvent.Step.Ended` |

`SessionEvent.Step.Ended` / `Step.Failed` use durable `{ aggregate: "sessionID", version: 2 }` (`packages/schema/src/session-event.ts` `stepSettlementOptions`). Other durable session-next events in that file use version **1** (`options`). `DurableDefinitions` omits delta/live-only members (`Text.Delta`, `Reasoning.Delta`, `Tool.Input.Delta`, `Compaction.Delta`) that remain on `SessionEvent.Definitions` (`packages/schema/src/session-event.ts`).

`SessionV1.Event.Definitions` types, in order: `session.created`, `session.updated`, `session.deleted`, `message.updated`, `message.removed`, `message.part.updated`, `message.part.removed`, `message.part.delta`, `session.diff`, `session.error`. Seven of those are durable with `aggregate === "sessionID"` and `version === 1` (`packages/schema/test/legacy-event.test.ts` `owns all SessionV1 definitions`; `packages/schema/test/event-manifest.test.ts`).

Legacy transient public types: `message.part.delta`, `session.diff`, `session.error`, `permission.asked`, `permission.replied`, `question.asked`, `question.replied`, `question.rejected`, `project.updated`, `command.executed` (`packages/schema/test/legacy-event.test.ts` `owns the legacy transient public definitions`).

Package guide: classify events as `current`, `shared transitional`, or `V1-only` before adding them to a public manifest; being emitted by V1 is not enough for Protocol/SDK Next; keep a single canonical definition (`packages/schema/AGENTS.md` Events). Protocol HTTP unions: `GET /api/event` (`event.subscribe`) over `EventManifest.ServerDefinitions` plus HTTP-synthetic `server.connected`, and `GET /api/session/:sessionID/event` (`session.events`) over `SessionEvent.Durable`, are [7.1 HTTP API](07.1-http-api.md). SDK Next publication beyond that HTTP catalog is OQ-8-1.

### Selected current domain contracts

Field-level truth is the cited module. This table is the slice-level map, not a second copy of every field.

| Namespace | Shipped contract (citations) |
|-----------|------------------------------|
| `Session.Info` | `id`, optional `parentID`, `projectID`, optional `agent` / `model`, `cost`, `tokens`, `time` `{ created, updated, optional archived }`, `title`, `location`, optional `subpath`, optional `revert` (`packages/schema/src/session.ts`) |
| `Session.ListAnchor` | `id`, `time` (finite), `direction` `"previous"` \| `"next"` |
| `Location.Ref` | `directory` (`AbsolutePath`), optional `workspaceID` (`packages/schema/src/location.ts`). Omitted `workspaceID` means implicit-local placement; explicit workspace identity remains reserved for future placement semantics (`AGENTS.md` V2 Session Core) |
| `Location.Info` | class with `directory`, optional `workspaceID`, `project: { id, directory }` |
| `Location.response(data)` | `{ location: Info, data }` |
| `SessionDelivery.Delivery` / `SessionInput.Delivery` | `"steer"` \| `"queue"` (`packages/schema/src/session-delivery.ts`) |
| `SessionInput.Admitted` | `admittedSeq`, `id` (message), `sessionID`, `prompt`, `delivery`, `timeCreated`, optional `promotedSeq` (`packages/schema/src/session-input.ts`) |
| `SessionTodo.Info` | `content`, `status`, `priority` as **arbitrary strings** (descriptions mention pending/high/etc.; decode accepts other strings) (`packages/schema/src/session-todo.ts`; `packages/schema/test/contract-hygiene.test.ts` `todo status and priority preserve arbitrary strings`) |
| `Model.Ref` | `id`, `providerID`, optional `variant` (`packages/schema/src/model.ts`) |
| `Agent.Info` | includes `mode` `"subagent"` \| `"primary"` \| `"all"`, `permissions: Permission.Ruleset` (`packages/schema/src/agent.ts`) |
| `LLM.ToolContent` | tagged union `text` \| `file` (`packages/schema/src/llm.ts`) |
| `Project.Vcs` | literal `"git"` (`packages/schema/src/project.ts`) |

## Error handling

| Situation | Behavior |
|-----------|----------|
| `Event.latest` sees two **different** definitions with the same `type` and cannot choose by durable version | throws `Error` with message `Duplicate latest event definition for ${definition.type}` (`packages/schema/src/event.ts` `latest`) |
| `Event.durable` sees two definitions with the same `versionedType` key | throws `Error` with message `Duplicate durable event definition for ${key}` (`packages/schema/src/event.ts` `durable`) |
| Invalid unknown input to Schema codecs | Effect Schema decode/encode failure (as exercised by `Schema.decodeUnknownSync` / `Schema.encodeSync` in `packages/schema/test/contract-hygiene.test.ts`) — Schema does not define a separate domain error union for these failures |

No package-level HTTP/CLI exit codes; this package is contract-only (`packages/schema/AGENTS.md` Package Boundary).

## Verification

Verification is the canonical index for decision ↔ coverage (workflow `#spec-anchor-format` Placement). One tag per line.

- tests: none found (package.json / exports / dependency direction)
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#construction--configuration
- tests: `packages/schema/test/event-manifest.test.ts` `uses canonical definitions for current public events`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#package-boundary-and-barrel
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-manifests
- tests: `packages/schema/test/contract-hygiene.test.ts` `optional properties preserve transformations and omit undefined while encoding`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#combinators-and-scalar-schemas
- tests: `packages/schema/test/contract-hygiene.test.ts` `current source avoids Any and mutable contract wrappers`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#combinators-and-scalar-schemas
- tests: `packages/schema/test/compatibility.test.ts` `moved class schemas remain constructible`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#combinators-and-scalar-schemas
- tests: `packages/schema/test/contract-hygiene.test.ts` `current ID constructors expose create`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#identifiers
- tests: `packages/schema/test/contract-hygiene.test.ts` `reusable public identifiers are stable and unique`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#identifiers
- tests: `packages/schema/test/v1-isolation.test.ts` `compatibility entrypoints preserve isolated V1 schema identity`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#current-versus-v1
- tests: `packages/schema/test/v1-isolation.test.ts` `current source does not import the V1 subtree directly`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#current-versus-v1
- tests: `packages/schema/test/event.test.ts` `definition is pure`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-algebra
- tests: `packages/schema/test/event.test.ts` `latest selection is independent of declaration order`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-algebra
- tests: `packages/schema/test/event.test.ts` `durable definitions are indexed by type and version`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-algebra
- tests: `packages/schema/test/event-manifest.test.ts` `owns the complete public event surface`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-manifests
- tests: `packages/schema/test/legacy-event.test.ts` `owns all SessionV1 definitions`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-manifests
- tests: `packages/schema/test/legacy-event.test.ts` `owns the legacy transient public definitions`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#event-manifests
- tests: `packages/schema/test/contract-hygiene.test.ts` `todo status and priority preserve arbitrary strings`
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#behavior
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#selected-current-domain-contracts
- tests: none found (`Event.latest` / `Event.durable` duplicate throws; OQ-8-2)
- Spec-Anchor: proj-spec/chapters/08-domain-model.md#error-handling

## Related chapters

- [README](../README.md)
- [3 Architecture](03-architecture.md)
- [6.1 Agent CLI](06.1-agent-cli.md)
- [6.2 Core](06.2-core.md)
- [6.4 Protocol](06.4-protocol.md)
- [7.1 HTTP API](07.1-http-api.md)
- [6.7 Client](06.7-client.md)
- [6.10 LLM](06.10-llm.md)
- [6.18 App](06.18-app.md)

## Open questions

### OQ-8-1 — SDK Next event publication

- **Unknown:** Which Schema event types SDK Next exposes beyond the Protocol HTTP unions in [7.1 HTTP API](07.1-http-api.md) (`EventManifest.ServerDefinitions` plus HTTP-synthetic `server.connected` on `/api/event`; `SessionEvent.Durable` on `/api/session/:sessionID/event`).
- **Why in-slice paths are insufficient:** SDK Next packages are outside this leaf’s allowed-paths (C10). Protocol `/api/event` and session event HTTP unions are specified in 7.1, not unknown.
- **Blocking:** none

### OQ-8-2 — Duplicate event definition throws

- **Unknown:** none for the throw messages themselves (cited in `packages/schema/src/event.ts`); coverage gap only.
- **Why:** no test in `packages/schema/test/` asserts `Duplicate latest event definition` or `Duplicate durable event definition`.
- **Blocking:** none
