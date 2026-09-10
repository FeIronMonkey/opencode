# 5 File tree

> **Spec chapter:** Shipped Bun workspace package paths (retrospective). Not a repository dump.
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**File:** `package.json` (workspace root). Package directories are those listed in `tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md` §2 and `tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §2.

This chapter records **where** first-party workspace packages live on disk. Per-package behavior, catalog pins, generate commands, and CLI binaries belong in other leaves. This pass is retrospective of shipped layout (C8). T1 concern for this leaf: “Package paths from T0, not a dump” (`T1-chapter-map.md` §1 id `5`).

T1 **multi-leaf packages** consistency token (names only; this chapter does not re-home their contracts): `schema`, `core`, `protocol`, `server`, `client`, `sdk`, `sdk-next`, `plugin`, `ui` (`T1-chapter-map.md` §7). Their directory paths are in the tables below.

## Construction / configuration

Root workspace identity (`name`, `private`, `type`, `packageManager`) and Bun `workspaces.packages` globs are canonical in [4 Stack — Construction / configuration](04-stack.md#construction--configuration). This leaf records package **paths** only.

### Workspace membership globs

Canonical glob list: [4 Stack](04-stack.md#construction--configuration) (Workspace membership). T0 describes the repo as a monorepo managed by Bun workspaces via that field (`T0-inventory.md` §2). This leaf does not specify catalog versions or Turbo (those are §4).

### Workspace package paths

T0 §2 and T1 §2 list **36** workspace packages. Paths below are copied from those tables (T1 §2 `Path` column; T0 §2 `Path` column). npm `name` is T0 §2 `Package`.

| npm name | Path |
|----------|------|
| `opencode` | `packages/opencode` |
| `@opencode-ai/core` | `packages/core` |
| `@opencode-ai/schema` | `packages/schema` |
| `@opencode-ai/protocol` | `packages/protocol` |
| `@opencode-ai/server` | `packages/server` |
| `@opencode-ai/client` | `packages/client` |
| `@opencode-ai/sdk` | `packages/sdk/js` |
| `@opencode-ai/sdk-next` | `packages/sdk-next` |
| `@opencode-ai/tui` | `packages/tui` |
| `@opencode-ai/cli` | `packages/cli` |
| `@opencode-ai/app` | `packages/app` |
| `@opencode-ai/desktop` | `packages/desktop` |
| `@opencode-ai/ui` | `packages/ui` |
| `@opencode-ai/session-ui` | `packages/session-ui` |
| `@opencode-ai/llm` | `packages/llm` |
| `@opencode-ai/codemode` | `packages/codemode` |
| `@opencode-ai/plugin` | `packages/plugin` |
| `@opencode-ai/httpapi-codegen` | `packages/httpapi-codegen` |
| `@opencode-ai/http-recorder` | `packages/http-recorder` |
| `@opencode-ai/effect-drizzle-sqlite` | `packages/effect-drizzle-sqlite` |
| `@opencode-ai/effect-sqlite-node` | `packages/effect-sqlite-node` |
| `@opencode-ai/script` | `packages/script` |
| `@opencode-ai/function` | `packages/function` |
| `@opencode-ai/enterprise` | `packages/enterprise` |
| `@opencode-ai/web` | `packages/web` |
| `@opencode-ai/storybook` | `packages/storybook` |
| `@opencode-ai/slack` | `packages/slack` |
| `@opencode-ai/console-app` | `packages/console/app` |
| `@opencode-ai/console-core` | `packages/console/core` |
| `@opencode-ai/console-function` | `packages/console/function` |
| `@opencode-ai/console-mail` | `packages/console/mail` |
| `@opencode-ai/console-resource` | `packages/console/resource` |
| `@opencode-ai/console-support` | `packages/console/support` |
| `@opencode-ai/stats-app` | `packages/stats/app` |
| `@opencode-ai/stats-core` | `packages/stats/core` |
| `@opencode-ai/stats-server` | `packages/stats/server` |

Multi-leaf package names map to these paths: `schema` → `packages/schema`; `core` → `packages/core`; `protocol` → `packages/protocol`; `server` → `packages/server`; `client` → `packages/client`; `sdk` → `packages/sdk/js`; `sdk-next` → `packages/sdk-next`; `plugin` → `packages/plugin`; `ui` → `packages/ui` (`T1-chapter-map.md` §2, §7).

### Nested workspace trees

These inventory paths sit under nested globs (not only `packages/*`):

| Tree | Paths |
|------|-------|
| Console | `packages/console/app`, `packages/console/core`, `packages/console/function`, `packages/console/mail`, `packages/console/resource`, `packages/console/support` |
| Stats | `packages/stats/app`, `packages/stats/core`, `packages/stats/server` |
| SDK JS | `packages/sdk/js` |

(`T0-inventory.md` §2; `package.json` `workspaces.packages`.)

T0 flags a naming contradiction: stats README lists package `function` for Lambda handlers; the workspace has `@opencode-ai/stats-server`, not `stats/function` (`T0-inventory.md` Contradictions flagged). `@opencode-ai/function` remains `packages/function` (`T1-chapter-map.md` §2 assigned 6.25; §9 OQ-T1-5).

### Generated path locations

`generated-in-slice` for this leaf is **no**. The paths below are **generated locations** from T0 §4 / T1 §5. They are not hand-authored behavioral source of truth (C5). Generators and commands are specified in other leaves (T1 §5 points 10.2 as ops home).

| Path | As recorded in T0 §4 |
|------|----------------------|
| `packages/client/src/generated/` | Generated tree (`T0-inventory.md` §4) |
| `packages/client/src/generated-effect/` | Generated tree; T0 records `scripts.check:generated` diffs both dirs (`T0-inventory.md` §4) |
| `packages/sdk/js/src/v2/gen/` | Generated tree (`T0-inventory.md` §4) |
| `packages/sdk/js/dist/` | Declared publish target; **not present in tree** — produced by build (`T0-inventory.md` §4) |
| `packages/ui` generated assets | T0 names `generate:tailwind`, `generate:v2-oc2`; no subdirectory (`T0-inventory.md` §4) |
| `packages/stats/core` Drizzle output | T0 names `db:generate` / `drizzle-kit generate`; no subdirectory (`T0-inventory.md` §4) |

T1 `generated?` = `yes` for packages `@opencode-ai/client`, `@opencode-ai/sdk`, `@opencode-ai/ui`, `@opencode-ai/stats-core` (`T1-chapter-map.md` §2). `httpapi-codegen` is the generator, not a generated tree (`T1-chapter-map.md` §2).

### Root layout declared in package.json

These root paths are named by root `package.json` (not a full-tree listing):

| Path / key | How it is named |
|------------|-----------------|
| `script/upgrade-opentui.ts` | `scripts.upgrade-opentui` |
| `script/translate-app.ts` | `scripts.translate:app` |
| `packages/opencode` | `scripts.dev` `--cwd packages/opencode` |
| `packages/desktop` | `scripts.dev:desktop` `--cwd packages/desktop` |
| `packages/app` | `scripts.dev:web` `--cwd packages/app` |
| `packages/console/app` | `scripts.dev:console` `--cwd packages/console/app` |
| `packages/stats/app` | `scripts.dev:stats` `--cwd packages/stats/app` |
| `packages/storybook` | `scripts.dev:storybook` `--cwd packages/storybook` |
| `packages/core` | `scripts.postinstall` `--cwd packages/core` `fix-node-pty` |
| `patches/` | `patchedDependencies` values such as `patches/@dnd-kit%2Fdom@0.5.0.patch` |

Root `dependencies` include workspace packages `@opencode-ai/plugin`, `@opencode-ai/script`, `@opencode-ai/sdk` (`workspace:*`) (`package.json` `dependencies`).

Repo root `docs/**`: **none found** (path absent) (`T0-inventory.md` §6).

Approximate per-package `*.ts` / `*.tsx` / `*.go` counts exist in T0 §8 (excluding `node_modules`, `dist`, `generated`, `generated-effect`). This chapter does not repeat that size table.

## Behavior

The shipped workspace **is** the set of packages and paths in [Workspace package paths](#workspace-package-paths). T1 assigns each package to exactly one leaf or an explicit non-goal (`T1-chapter-map.md` §2, §3). This chapter does not restate those leaf contracts.

T0 §3 maps product surfaces onto those package directories (for example CLI primary → `packages/opencode`; CLI alternate → `packages/cli`; TUI → `packages/tui`). Surface behavior is out of this leaf.

### Non-goal workspace path

`@opencode-ai/storybook` at `packages/storybook` remains a workspace package (`T0-inventory.md` §2). T1 assigns it `non-goal:2` because T0 surface “Storybook (dev)” / purpose “Storybook dev harness” is not a shipped product surface (`T1-chapter-map.md` §3).

## Error handling

Root `scripts.test` failure is canonical in [4 Stack — Error handling](04-stack.md#error-handling). Allowed sources do not name other layout-time errors (missing globs, extra directories). T0 records that `@opencode-ai/core` declares `bin.opencode` but no matching bin file under `packages/core/bin/` (`T0-inventory.md` Contradictions flagged; `T1-chapter-map.md` §9 OQ-T1-2). This leaf does not invent a tree-walk error for that gap.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement). Allowed-paths for this leaf do not include test files.

- Spec-Anchor: proj-spec/chapters/05-file-tree.md#construction--configuration — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#workspace-membership-globs — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#workspace-package-paths — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#nested-workspace-trees — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#generated-path-locations — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#root-layout-declared-in-packagejson — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#behavior — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#non-goal-workspace-path — tests: none found; OQ-5-1
- Spec-Anchor: proj-spec/chapters/05-file-tree.md#error-handling — tests: none found; OQ-5-1

## Related chapters

- [README](../README.md)
- [4 Stack](04-stack.md)

## Open questions

### OQ-5-1: No tests in allowed-paths for workspace layout

- **Tags:** `proj-spec/chapters/05-file-tree.md#verification`
- **Discovered in:** retrospective chapter write (slice 5)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed-paths are `package.json`, T0, and T1 only. No test module was in scope that asserts workspace globs, the 36 package paths, generated location strings, or root `scripts.test` exit `1`.

### OQ-5-2: On-disk tree beyond workspace packages

- **Tags:** `proj-spec/chapters/05-file-tree.md#root-layout-declared-in-packagejson`
- **Discovered in:** retrospective chapter write (slice 5)
- **Blocking:** none
- **Status:** open
- **Question:** Root `package.json` names `script/`, `patches/`, and selected `--cwd` package dirs. Full repo layout (CI workflows, other top-level dirs) is outside allowed-paths (C10).

### OQ-5-3: Subdirectories of generated ui and stats-core output

- **Tags:** `proj-spec/chapters/05-file-tree.md#generated-path-locations`
- **Discovered in:** retrospective chapter write (slice 5)
- **Blocking:** none
- **Status:** open
- **Question:** T0 §4 names `packages/ui` generated assets and `packages/stats/core` Drizzle output without a subdirectory path. Exact generated folders were not in this leaf’s allowed-paths.
