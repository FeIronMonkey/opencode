# 4 Stack

> **Spec chapter:** Bun workspaces, Turbo pipeline, and workspace catalog pins for the OpenCode monorepo.
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**Files:** `package.json`, `turbo.json`, `AGENTS.md`

This slice is the **workspace toolchain**: root package identity, Bun workspace globs, the `workspaces.catalog` pin set, Turbo tasks, and the root scripts and agent rules that operate that workspace. Package internals, regeneration commands, and binary install surfaces are out of scope. This pass is retrospective of shipped files.

## Construction / configuration

Root package identity (`package.json`):

| Parameter | Value | Notes |
|-----------|-------|-------|
| `name` | `opencode` | Root workspace package |
| `description` | `AI-powered development tool` | `package.json` `description` |
| `private` | `true` | |
| `type` | `module` | |
| `packageManager` | `bun@1.3.14` | |
| `license` | `MIT` | |
| `$schema` | `https://json.schemastore.org/package.json` | |
| `repository.url` | `https://github.com/anomalyco/opencode` | `type` `git` |

Workspace membership (`package.json` `workspaces.packages`):

| Glob | Notes |
|------|-------|
| `packages/*` | First-level packages under `packages/` |
| `packages/console/*` | Nested console packages |
| `packages/stats/*` | Nested stats packages |
| `packages/sdk/js` | Explicit SDK JS package path |
| `packages/slack` | Explicit Slack package path |

Workspace catalog pins (`package.json` `workspaces.catalog`). Values are the catalog strings as shipped:

| Catalog name | Pin |
|--------------|-----|
| `@effect/opentelemetry` | `4.0.0-beta.83` |
| `@effect/platform-node` | `4.0.0-beta.83` |
| `@effect/sql-sqlite-bun` | `4.0.0-beta.83` |
| `@npmcli/arborist` | `9.4.0` |
| `@types/bun` | `1.3.13` |
| `@types/cross-spawn` | `6.0.6` |
| `@octokit/rest` | `22.0.0` |
| `@hono/standard-validator` | `0.2.0` |
| `@hono/zod-validator` | `0.4.2` |
| `@opentui/core` | `0.4.5` |
| `@opentui/keymap` | `0.4.5` |
| `@opentui/solid` | `0.4.5` |
| `@tanstack/solid-virtual` | `3.13.32` |
| `@shikijs/stream` | `4.2.0` |
| `ulid` | `3.0.1` |
| `@kobalte/core` | `0.13.11` |
| `@corvu/drawer` | `0.2.4` |
| `@types/luxon` | `3.7.1` |
| `@types/node` | `24.12.2` |
| `@types/semver` | `7.7.1` |
| `@tsconfig/node22` | `22.0.2` |
| `@tsconfig/bun` | `1.0.9` |
| `@cloudflare/workers-types` | `4.20251008.0` |
| `@openauthjs/openauth` | `0.0.0-20250322224806` |
| `@pierre/diffs` | `1.2.10` |
| `opentui-spinner` | `0.0.7` |
| `@solid-primitives/storage` | `4.3.3` |
| `@tailwindcss/vite` | `4.1.11` |
| `diff` | `8.0.2` |
| `dompurify` | `3.3.1` |
| `drizzle-kit` | `1.0.0-rc.2` |
| `drizzle-orm` | `1.0.0-rc.2` |
| `effect` | `4.0.0-beta.83` |
| `ai` | `6.0.168` |
| `cross-spawn` | `7.0.6` |
| `hono` | `4.10.7` |
| `hono-openapi` | `1.1.2` |
| `fuzzysort` | `3.1.0` |
| `luxon` | `3.6.1` |
| `marked` | `18.0.7` |
| `marked-shiki` | `1.2.1` |
| `remend` | `1.3.0` |
| `@playwright/test` | `1.59.1` |
| `semver` | `7.7.4` |
| `typescript` | `5.8.2` |
| `@typescript/native-preview` | `7.0.0-dev.20251207.1` |
| `zod` | `4.1.8` |
| `remeda` | `2.26.0` |
| `sst` | `4.13.1` |
| `shiki` | `4.2.0` |
| `solid-list` | `0.3.0` |
| `tailwindcss` | `4.1.11` |
| `vite` | `7.1.4` |
| `@solidjs/meta` | `0.29.4` |
| `@solidjs/router` | `0.15.4` |
| `@solidjs/start` | `https://pkg.pr.new/@solidjs/start@dfb2020` |
| `@sentry/solid` | `10.36.0` |
| `@sentry/vite-plugin` | `4.6.0` |
| `solid-js` | `1.9.10` |
| `solid-sonner` | `0.3.1` |
| `vite-plugin-solid` | `2.11.10` |
| `@lydell/node-pty` | `1.2.0-beta.12` |

Root `dependencies` (`package.json`):

| Name | Pin |
|------|-----|
| `@aws-sdk/client-s3` | `3.933.0` |
| `@opencode-ai/plugin` | `workspace:*` |
| `@opencode-ai/script` | `workspace:*` |
| `@opencode-ai/sdk` | `workspace:*` |
| `heap-snapshot-toolkit` | `1.1.3` |
| `typescript` | `catalog:` |

Root `devDependencies` (`package.json`):

| Name | Pin |
|------|-----|
| `@actions/artifact` | `5.0.1` |
| `@tsconfig/bun` | `catalog:` |
| `@types/mime-types` | `3.0.1` |
| `@typescript/native-preview` | `catalog:` |
| `glob` | `13.0.5` |
| `husky` | `9.1.7` |
| `oxlint` | `1.60.0` |
| `oxlint-tsgolint` | `0.21.0` |
| `prettier` | `3.6.2` |
| `semver` | `^7.6.0` |
| `sst` | `catalog:` |
| `turbo` | `2.10.2` |

Root `overrides` (`package.json`):

| Name | Pin |
|------|-----|
| `@ai-sdk/anthropic` | `3.0.111` |
| `@opentui/core` | `catalog:` |
| `@opentui/keymap` | `catalog:` |
| `@opentui/solid` | `catalog:` |
| `@types/bun` | `catalog:` |
| `@types/node` | `catalog:` |

Root `patchedDependencies` (`package.json`):

| Package | Patch path |
|---------|------------|
| `@dnd-kit/dom@0.5.0` | `patches/@dnd-kit%2Fdom@0.5.0.patch` |
| `@npmcli/agent@4.0.2` | `patches/@npmcli%2Fagent@4.0.2.patch` |
| `@silvia-odwyer/photon-node@0.3.4` | `patches/@silvia-odwyer%2Fphoton-node@0.3.4.patch` |
| `@standard-community/standard-openapi@0.2.9` | `patches/@standard-community%2Fstandard-openapi@0.2.9.patch` |
| `solid-js@1.9.10` | `patches/solid-js@1.9.10.patch` |
| `@ai-sdk/xai@3.0.102` | `patches/@ai-sdk%2Fxai@3.0.102.patch` |
| `@ai-sdk/mistral@3.0.51` | `patches/@ai-sdk%2Fmistral@3.0.51.patch` |
| `gcp-metadata@8.1.2` | `patches/gcp-metadata@8.1.2.patch` |
| `pacote@21.5.0` | `patches/pacote@21.5.0.patch` |
| `@ai-sdk/google@3.0.73` | `patches/@ai-sdk%2Fgoogle@3.0.73.patch` |
| `@pierre/trees@1.0.0-beta.4` | `patches/@pierre%2Ftrees@1.0.0-beta.4.patch` |
| `@modelcontextprotocol/sdk@1.29.0` | `patches/@modelcontextprotocol%2Fsdk@1.29.0.patch` |
| `effect@4.0.0-beta.83` | `patches/effect@4.0.0-beta.83.patch` |
| `@tanstack/virtual-core@3.17.3` | `patches/@tanstack%2Fvirtual-core@3.17.3.patch` |
| `@ai-sdk/openai-compatible@2.0.41` | `patches/@ai-sdk%2Fopenai-compatible@2.0.41.patch` |
| `@ai-sdk/groq@3.0.31` | `patches/@ai-sdk%2Fgroq@3.0.31.patch` |
| `@ai-sdk/anthropic@3.0.111` | `patches/@ai-sdk%2Fanthropic@3.0.111.patch` |
| `@ai-sdk/amazon-bedrock@4.0.166` | `patches/@ai-sdk%2Famazon-bedrock@4.0.166.patch` |
| `@ai-sdk/openai@3.0.88` | `patches/@ai-sdk%2Fopenai@3.0.88.patch` |

`trustedDependencies` (`package.json`): `esbuild`, `node-pty`, `protobufjs`, `tree-sitter`, `tree-sitter-bash`, `tree-sitter-powershell`, `web-tree-sitter`, `electron`.

Root Prettier (`package.json` `prettier`): `semi` `false`, `printWidth` `120`.

Turbo (`turbo.json`): `$schema` `https://v2-8-13.turborepo.dev/schema.json`. `globalEnv` and `globalPassThroughEnv` are both `CI` and `OPENCODE_DISABLE_SHARE`.

| Turbo task | `dependsOn` | `outputs` | Other |
|------------|-------------|-----------|-------|
| `typecheck` | *(omitted)* | *(omitted)* | empty task object |
| `build` | `[]` | `["dist/**"]` | |
| `opencode#test` | `["^build"]` | `[]` | `passThroughEnv` `["*"]` |
| `@opencode-ai/core#test` | `["^build"]` | `[]` | |
| `@opencode-ai/function#test` | *(omitted)* | `[]` | |
| `@opencode-ai/app#test` | `["^build"]` | `[]` | |
| `@opencode-ai/ui#test` | `["^build"]` | `[]` | |
| `@opencode-ai/session-ui#test` | `["^build"]` | `[]` | |

Root scripts (`package.json` `scripts`):

| Script | Command |
|--------|---------|
| `dev` | `bun run --cwd packages/opencode src/index.ts` |
| `dev:desktop` | `bun --cwd packages/desktop dev` |
| `dev:web` | `bun --cwd packages/app dev` |
| `dev:console` | `ulimit -n 10240 2>/dev/null; bun run --cwd packages/console/app dev` |
| `dev:stats` | `bun sst shell --stage=production -- bun run --cwd packages/stats/app dev` |
| `dev:storybook` | `bun --cwd packages/storybook storybook` |
| `lint` | `oxlint` |
| `typecheck` | `bun turbo typecheck` |
| `upgrade-opentui` | `bun run script/upgrade-opentui.ts` |
| `postinstall` | `bun run --cwd packages/core fix-node-pty` |
| `prepare` | `husky` |
| `random` | `echo 'Random script'` |
| `sso` | `aws sso login --sso-session=opencode --no-browser` |
| `translate:app` | `bun run script/translate-app.ts` |
| `test` | `echo 'do not run tests from root' && exit 1` |

## Behavior

The workspace is a private Bun module monorepo named `opencode` with `packageManager` `bun@1.3.14` (`package.json`). Member packages are those matching `workspaces.packages`. Shared versions for catalog consumers are the `workspaces.catalog` pins above. Root `overrides` and `patchedDependencies` apply the listed pins and patch files. `trustedDependencies` is present with the names listed under Construction (`package.json`).

`prepare` runs `husky`. `postinstall` runs `bun run --cwd packages/core fix-node-pty`. `lint` runs `oxlint`. `typecheck` at the repo root runs `bun turbo typecheck` (`package.json` `scripts`). Turbo `typecheck` has an empty task body (`turbo.json`). Turbo `build` records `outputs` `dist/**` and `dependsOn` `[]`.

Named Turbo test tasks are only `opencode#test`, `@opencode-ai/core#test`, `@opencode-ai/function#test`, `@opencode-ai/app#test`, `@opencode-ai/ui#test`, and `@opencode-ai/session-ui#test` (`turbo.json`). `opencode#test` sets `passThroughEnv` to `["*"]`. Turbo `globalEnv` and `globalPassThroughEnv` both include `CI` and `OPENCODE_DISABLE_SHARE`.

Type checking (`AGENTS.md` Type Checking): always run `bun typecheck` from package directories (example `packages/opencode`); never `tsc` directly.

Testing (`AGENTS.md` Testing): tests cannot run from repo root (guard: `do-not-run-tests-from-root`); run from package dirs like `packages/opencode`. The root `test` script prints `do not run tests from root` and exits `1` (`package.json` `scripts.test`).

Runtime dependency direction (`AGENTS.md`): Keep runtime dependencies directed from Schema to Core and Protocol, then from Core and Protocol to Server. Client runtime code may depend on Schema and Protocol but never Core or Server; `sdk-next` composes Client, Core, and Server.

Default branch (`AGENTS.md`): The default branch in this repo is `dev`. Local `main` ref may not exist; use `dev` or `origin/dev` for diffs.

## Error handling

The root `test` script is `echo 'do not run tests from root' && exit 1` (`package.json` `scripts.test`). That is the shipped root-test failure: stdout/stderr from that `echo`, process exit code `1`.

Allowed sources do not name exit codes or error strings for `lint`, `typecheck`, Turbo tasks, `postinstall`, or other root scripts.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement and `#spec-coverage-audit`). One tag per line. Allowed paths for this slice do not include test files.

- Spec-Anchor: proj-spec/chapters/04-stack.md#construction--configuration — tests: none found (OQ-4-1, Blocking: none)
- Spec-Anchor: proj-spec/chapters/04-stack.md#behavior — tests: none found (OQ-4-2, Blocking: none)
- Spec-Anchor: proj-spec/chapters/04-stack.md#error-handling — tests: none found (OQ-4-3, Blocking: none)

### OQ-4-1: Workspace construction tests

- **Tags:** `proj-spec/chapters/04-stack.md#construction--configuration`
- **Discovered in:** retrospective spec slice 4
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that assert `package.json` workspace globs, catalog pins, Turbo task graph, or root script strings.

### OQ-4-2: Workspace behavior tests

- **Tags:** `proj-spec/chapters/04-stack.md#behavior`
- **Discovered in:** retrospective spec slice 4
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths for Turbo `typecheck`/`build`/`#test` tasks, `bun typecheck` vs `tsc`, runtime dependency direction, or default branch `dev`.

### OQ-4-3: Root test-script guard tests

- **Tags:** `proj-spec/chapters/04-stack.md#error-handling`
- **Discovered in:** retrospective spec slice 4
- **Blocking:** none
- **Status:** open
- **Question:** `AGENTS.md` names guard `do-not-run-tests-from-root`; no test file is in this slice’s allowed paths, so whether that guard is an automated test is unknown.

## Related chapters

- [README.md](../README.md)
