# 3 Architecture

> **Spec chapter:** Runtime package layering Schema → Core and Protocol → Server, Client runtime limits, and sdk-next composition.
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**Files:** `packages/schema/package.json` (`@opencode-ai/schema`), `packages/core/package.json` (`@opencode-ai/core`), `packages/protocol/package.json` (`@opencode-ai/protocol`), `packages/server/package.json` (`@opencode-ai/server`), `packages/client/package.json` (`@opencode-ai/client`), `packages/sdk-next/package.json` (`@opencode-ai/sdk-next`); workspace membership `package.json` `workspaces.packages`; layering rule `AGENTS.md`.

This chapter is the runtime **layering** contract for the packages named in the consistency token **multi-leaf packages** that this slice covers: `schema`, `core`, `protocol`, `server`, `client`, `sdk-next`. Package internals, HTTP `HttpApi`, and domain types live in the related §6 / §8 chapters. This pass is retrospective of shipped manifests and `AGENTS.md`. Tokens `plugin`, `ui`, and `sdk` remain named in that multi-leaf list; this chapter does not specify their behavior.

## Construction / configuration

These packages are first-party workspace members via root `package.json` `workspaces.packages` entry `packages/*`.

| Parameter | Value | Source |
|-----------|-------|--------|
| Schema `name` | `@opencode-ai/schema` | `packages/schema/package.json` |
| Schema `private` / `type` | `true` / `module` | `packages/schema/package.json` |
| Core `name` | `@opencode-ai/core` | `packages/core/package.json` |
| Core `private` / `type` | `true` / `module` | `packages/core/package.json` |
| Protocol `name` | `@opencode-ai/protocol` | `packages/protocol/package.json` |
| Protocol `private` / `type` | `true` / `module` | `packages/protocol/package.json` |
| Server `name` | `@opencode-ai/server` | `packages/server/package.json` |
| Server `private` / `type` | `true` / `module` | `packages/server/package.json` |
| Client `name` | `@opencode-ai/client` | `packages/client/package.json` |
| Client `private` / `type` | `true` / `module` | `packages/client/package.json` |
| sdk-next `name` | `@opencode-ai/sdk-next` | `packages/sdk-next/package.json` |
| sdk-next `private` / `type` | `true` / `module` | `packages/sdk-next/package.json` |

Package-local exports (entrypoints only; not domain contracts):

| Package | `exports` | Source |
|---------|-----------|--------|
| `@opencode-ai/schema` | `"."` → `./src/index.ts`; `"./*"` → `./src/*.ts` | `packages/schema/package.json` |
| `@opencode-ai/protocol` | `"./*"` → `./src/*.ts` | `packages/protocol/package.json` |
| `@opencode-ai/core` | `"./effect/layer-node"`, `"./effect/app-node"`, `"./session/runner"`, `"./system-context"`, `"./*"` | `packages/core/package.json` |
| `@opencode-ai/server` | `"./*"` → `./src/*.ts` | `packages/server/package.json` |
| `@opencode-ai/client` | `"."` → `./src/index.ts`; `"./effect"` → `./src/effect.ts` | `packages/client/package.json` |
| `@opencode-ai/sdk-next` | `"."` → `./src/index.ts` | `packages/sdk-next/package.json` |

## Behavior

### Runtime dependency direction

Runtime dependencies MUST stay directed from Schema to Core and Protocol, then from Core and Protocol to Server (`AGENTS.md`).

Declared first-party `dependencies` (workspace) that implement that direction:

| Package | First-party `dependencies` | Source |
|---------|----------------------------|--------|
| `@opencode-ai/schema` | none | `packages/schema/package.json` `dependencies` (`effect` only) |
| `@opencode-ai/protocol` | `@opencode-ai/schema` | `packages/protocol/package.json` |
| `@opencode-ai/core` | `@opencode-ai/schema` (also `@opencode-ai/llm`, `@opencode-ai/plugin`, `@opencode-ai/effect-drizzle-sqlite`, `@opencode-ai/effect-sqlite-node`) | `packages/core/package.json` |
| `@opencode-ai/server` | `@opencode-ai/core`, `@opencode-ai/protocol` | `packages/server/package.json` |

`@opencode-ai/core` `dependencies` MUST NOT list `@opencode-ai/protocol`, `@opencode-ai/server`, `@opencode-ai/client`, or `@opencode-ai/sdk-next` (absent from `packages/core/package.json` `dependencies`). `@opencode-ai/protocol` `dependencies` MUST NOT list `@opencode-ai/core`, `@opencode-ai/server`, `@opencode-ai/client`, or `@opencode-ai/sdk-next` (absent from `packages/protocol/package.json` `dependencies`). `@opencode-ai/schema` MUST NOT list those packages in `dependencies` (absent from `packages/schema/package.json` `dependencies`).

### Client runtime versus devDependencies

Client runtime code may depend on Schema and Protocol but never Core or Server (`AGENTS.md`).

| Field | Packages | Source |
|-------|----------|--------|
| `@opencode-ai/client` `dependencies` | `@opencode-ai/schema`, `@opencode-ai/protocol` | `packages/client/package.json` |
| `@opencode-ai/client` `dependencies` MUST NOT include | `@opencode-ai/core`, `@opencode-ai/server` | absent from `packages/client/package.json` `dependencies` |
| `@opencode-ai/client` `devDependencies` | includes `@opencode-ai/core`, `@opencode-ai/server` (and `@opencode-ai/httpapi-codegen`) | `packages/client/package.json` |

`peerDependencies` may include `effect` `4.0.0-beta.83` with `peerDependenciesMeta.effect.optional` `true` (`packages/client/package.json`). That peer is not a Core or Server runtime dependency.

### sdk-next composition

`sdk-next` composes Client, Core, and Server (`AGENTS.md`).

| Field | Value | Source |
|-------|-------|--------|
| `@opencode-ai/sdk-next` `dependencies` | `@opencode-ai/client`, `@opencode-ai/core`, `@opencode-ai/server`, `effect` | `packages/sdk-next/package.json` |

`@opencode-ai/sdk-next` `dependencies` do not list `@opencode-ai/schema` or `@opencode-ai/protocol` (`packages/sdk-next/package.json`). Schema/Protocol reach sdk-next through Client (and Schema through Core) per those packages’ own `dependencies`.

## Error handling

`AGENTS.md` and the listed `package.json` files do not define an error string, HTTP status, or process exit code for a runtime-layering violation. Root `package.json` `scripts.test` is `echo 'do not run tests from root' && exit 1`; that exit is the workspace test-from-root guard, not a Schema/Core/Protocol/Server import check.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement and `#spec-coverage-audit`). One tag per line.

Allowed source paths for this slice do not include test files.

- Spec-Anchor: proj-spec/chapters/03-architecture.md#construction--configuration — tests: none found
- Spec-Anchor: proj-spec/chapters/03-architecture.md#behavior — tests: none found
- Spec-Anchor: proj-spec/chapters/03-architecture.md#runtime-dependency-direction — tests: none found
- Spec-Anchor: proj-spec/chapters/03-architecture.md#client-runtime-versus-devdependencies — tests: none found
- Spec-Anchor: proj-spec/chapters/03-architecture.md#sdk-next-composition — tests: none found
- Spec-Anchor: proj-spec/chapters/03-architecture.md#error-handling — tests: none found

### OQ-003-001: Layering tests not in slice sources

- **Tags:** `proj-spec/chapters/03-architecture.md#verification`, `proj-spec/chapters/03-architecture.md#runtime-dependency-direction`, `proj-spec/chapters/03-architecture.md#client-runtime-versus-devdependencies`, `proj-spec/chapters/03-architecture.md#sdk-next-composition`, `proj-spec/chapters/03-architecture.md#construction--configuration`, `proj-spec/chapters/03-architecture.md#behavior`, `proj-spec/chapters/03-architecture.md#error-handling`
- **Discovered in:** retrospective chapter write
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no test names that encode Schema→Core/Protocol→Server, Client runtime vs Core/Server, or sdk-next composition. Coverage is unknown outside this slice.
- **Resolution:** *(when resolved)*

## Related chapters

- [README.md](../README.md)
- [6.2 Core](06.2-core.md)
- [6.4 Protocol](06.4-protocol.md)
- [6.5 Server](06.5-server.md)
- [6.7 Client](06.7-client.md)
- [6.9 sdk-next](06.9-sdk-next.md)
- [8 Domain model](08-domain-model.md)
