# Open questions

Inbox for unknowns recorded in `proj-spec/chapters/` during the retrospective greenfield spec (C7, C8). Entries are copied from in-chapter `OQ-*` stubs. This file is not a second product spec.

**Open count:** 294. **Blocking (not `none`):** 0.

REVIEW-SPEC may proceed while these remain `open` with `Blocking: none`. No resolutions are recorded here (retrospective; no reconstructed approvals).

### OQ-1-1: Product one-liner mismatch
- **Tags:** `proj-spec/chapters/01-overview.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Which string is canonical for product identity — README tagline `The open source AI coding agent.` or root `package.json` `description` `AI-powered development tool`? T1 §7 records this as a `product` token contradiction.
- **Resolution:** *(when resolved)*

### OQ-1-2: No tests for overview copy and surface inventory
- **Tags:** `proj-spec/chapters/01-overview.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths (`README.md`, `package.json`, T1 chapter map) name no test module that asserts README tagline, workspace description, surface inventory, documented agents, or root `scripts.test` exit `1`.
- **Resolution:** *(when resolved)*

### OQ-02-1: Product identity string contradiction
- **Tags:** `proj-spec/chapters/02-goals.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** T1 §7 token `product` lists OpenCode with README tagline `The open source AI coding agent.` versus root `package.json` `description` `AI-powered development tool`. Which string is canonical for product positioning?
- **Resolution:** *(when resolved)*

### OQ-02-2: Goals test coverage
- **Tags:** `proj-spec/chapters/02-goals.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Slice allowed-paths (`README.md`, `package.json`, T1 chapter map) include no tests. No named test encodes goals or `non-goal:2` Storybook exclusion.
- **Resolution:** *(when resolved)*

### OQ-02-3: Home for `sdks/vscode` and `.vscode/`
- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** T1 and leaves 6.8/6.9 do not assign `sdks/vscode` or `.vscode/`. Which existing leaf (if any) should own those paths is unknown. This map records them as non-goals. OQ-5-2 does not name them.
- **Resolution:** *(when resolved)*

### OQ-02-4: Home for `nix/`, `flake.nix`, `flake.lock`
- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** Leaf 10.1 does not own `nix/`, `flake.nix`, or `flake.lock`. Whether those paths belong under 10.1 or stay non-goals is unknown. This map records them as non-goals. OQ-5-2 does not name them.
- **Resolution:** *(when resolved)*

### OQ-02-5: Home for `sdks/`
- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** Non-workspace tree `sdks/` is not 6.8 or 6.9. Which existing leaf (if any) should own `sdks/` is unknown. This map records `sdks/` as a non-goal. OQ-5-2 does not name it.
- **Resolution:** *(when resolved)*

### OQ-02-6: Home for root `README.*.md` and `screenshot-uk.png`
- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** Root `README.*.md` and `screenshot-uk.png` are not leaf 6.27 (`packages/web/`). English `README.md` is leaves 1/2. Which existing leaf (if any) should own the localized files and `screenshot-uk.png` is unknown. This map records them as non-goals. OQ-5-2 does not name them.
- **Resolution:** *(when resolved)*

### OQ-02-7: Home for `infra/`, `sst.config.ts`, `sst-env.d.ts`, root `github/`
- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** `infra/`, `sst.config.ts`, `sst-env.d.ts`, and root `github/` are not leaves 6.21–6.25 (`packages/*`). Which existing leaf (if any) should own those paths is unknown. This map records them as non-goals. OQ-5-2 does not name them.
- **Resolution:** *(when resolved)*

### OQ-003-001: Layering tests not in slice sources
- **Tags:** `proj-spec/chapters/03-architecture.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no test names that encode Schema→Core/Protocol→Server, Client runtime vs Core/Server, or sdk-next composition. Coverage is unknown outside this slice.
- **Resolution:** *(when resolved)*

### OQ-4-1: Workspace construction tests
- **Tags:** `proj-spec/chapters/04-stack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that assert `package.json` workspace globs, catalog pins, Turbo task graph, or root script strings.
- **Resolution:** *(when resolved)*

### OQ-4-2: Workspace behavior tests
- **Tags:** `proj-spec/chapters/04-stack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths for Turbo `typecheck`/`build`/`#test` tasks, `bun typecheck` vs `tsc`, runtime dependency direction, or default branch `dev`.
- **Resolution:** *(when resolved)*

### OQ-4-3: Root test-script guard tests
- **Tags:** `proj-spec/chapters/04-stack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `AGENTS.md` names guard `do-not-run-tests-from-root`; no test file is in this slice’s allowed paths, so whether that guard is an automated test is unknown.
- **Resolution:** *(when resolved)*

### OQ-5-1: No tests in allowed-paths for workspace layout
- **Tags:** `proj-spec/chapters/05-file-tree.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed-paths are `package.json`, T0, and T1 only. No test module was in scope that asserts workspace globs, the 36 package paths, generated location strings, or root `scripts.test` exit `1`.
- **Resolution:** *(when resolved)*

### OQ-5-2: On-disk tree beyond workspace packages
- **Tags:** `proj-spec/chapters/05-file-tree.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Root `package.json` names `script/`, `patches/`, and selected `--cwd` package dirs. Full repo layout (CI workflows, other top-level dirs) is outside allowed-paths (C10).
- **Resolution:** *(when resolved)*

### OQ-5-3: Subdirectories of generated ui and stats-core output
- **Tags:** `proj-spec/chapters/05-file-tree.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** T0 §4 names `packages/ui` generated assets and `packages/stats/core` Drizzle output without a subdirectory path. Exact generated folders were not in this leaf’s allowed-paths.
- **Resolution:** *(when resolved)*

### OQ-6.1-1: Construction test coverage
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Help snapshots cover yargs/CLI defaults. Untested construction rows remain: `packages/opencode/package.json` `bin`/`scripts`/`imports`, `packages/script/package.json` exports, heap `LIMIT`/`MINUTE`/`Flag.OPENCODE_AUTO_HEAP_SNAPSHOT`, `ATTACH_FILE_MAX_BYTES`, and `startWithPortFallback` prefer-`4096` when resolved `--port` is `0`.
- **Resolution:** *(when resolved)*

### OQ-6.1-2: Script package tests
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No files matching `packages/script/**/*.{test,spec}.*`. Channel/version/team/bun-range behavior is untested in allowed globs.
- **Resolution:** *(when resolved)*

### OQ-6.1-3: npm bin launcher tests
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/opencode/bin/opencode` platform/musl/AVX2 resolution or the missing-binary stderr string.
- **Resolution:** *(when resolved)*

### OQ-6.1-4: Parent behavior heading vs nested coverage
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Named coverage for `## Behavior` is the help-snapshot sweep of registered commands; it does not independently assert middleware order (`OPENCODE_PRINT_LOGS` / `OPENCODE_LOG_LEVEL` / `OPENCODE_PURE`, then `Heap.start()`, then `AGENT` / `OPENCODE` / `OPENCODE_PID`) or yargs `.fail` throw-vs-`showHelp` vs `process.exit(1)`.
- **Resolution:** *(when resolved)*

### OQ-6.1-5: `opencode generate` tests
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `GenerateCommand` is registered but omitted from `TOP_LEVEL` help snapshots; no test found that asserts OpenAPI stdout.
- **Resolution:** *(when resolved)*

### OQ-6.1-6: Upgrade and uninstall tests
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Help snapshots cover `--help` for `upgrade`/`uninstall`; no tests found for install-method detection, skip-when-same-version, or uninstall dry-run/force paths.
- **Resolution:** *(when resolved)*

### OQ-6.1-7: Console and debug child coverage
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `console` uses `describe: false` and is not in `TOP_LEVEL`. Debug subcommands beyond help text are largely untested as CLI argv (except incidental package tests outside this heading).
- **Resolution:** *(when resolved)*

### OQ-6.1-8: Serve/web password warning tests
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Serve subprocess tests cover listen/health/kill, not the `OPENCODE_SERVER_PASSWORD` unsecured warning, `web` URL printing/`open()`, or `startWithPortFallback` prefer-`4096` when resolved port is `0`. Default TUI `resolveNetworkOptionsNoConfig(args)` with no config (so `config.server` listen fields unused) is also untested as a listen-resolution case.
- **Resolution:** *(when resolved)*

### OQ-6.1-9: Script sources outside slice paths
- **Tags:** `proj-spec/chapters/06.1-agent-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/script/src/index.ts` reads repo-root `package.json` (`packageManager`) and `.github/TEAM_MEMBERS`. Those paths are not in this leaf’s allowed-paths; exact bun pin and team file contents are not cited here.
- **Resolution:** *(when resolved)*

### OQ-6.10-1: Schema package field contracts
- **Tags:** `proj-spec/chapters/06.10-llm.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `ProviderMetadata`, `ToolContent`, `ToolFileContent`, and `ToolTextContent` are imported from `@opencode-ai/schema/llm` in `packages/llm/src/schema/ids.ts` and `messages.ts`. Canonical field-level contracts for those types are outside this slice (C10); specify them in chapter 8.
- **Resolution:** *(when resolved)*

### OQ-6.10-2: Session host adapters
- **Tags:** `proj-spec/chapters/06.10-llm.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/llm/AGENTS.md` names host adapters under `packages/opencode/src/session/llm*`, which are outside allowed-paths for this leaf. How those adapters select native vs other runtimes is for chapters 6.1 / 6.2.
- **Resolution:** *(when resolved)*

### OQ-6.10-3: Recorded-test filter unit tests
- **Tags:** `proj-spec/chapters/06.10-llm.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `RECORDED_*` env filter behavior is implemented in `packages/llm/test/recorded-utils.ts` `matchesSelected`. No dedicated test name was found that asserts those env filters.
- **Resolution:** *(when resolved)*

### OQ-6.11-001: Construction defaults test coverage
- **Tags:** `proj-spec/chapters/06.11-http-recorder.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No dedicated test asserts default `RecorderOptions`, package exports, or engine constraints; those defaults are sourced from package manifests and module code only.
- **Resolution:** *(when resolved)*

### OQ-6.11-002: Public API test coverage
- **Tags:** `proj-spec/chapters/06.11-http-recorder.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No dedicated test asserts the exported `HttpRecorder` surface or type re-exports; callers rely on TypeScript exports from `packages/http-recorder/src/index.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.11-003: Known limits test coverage
- **Tags:** `proj-spec/chapters/06.11-http-recorder.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Known limits (buffering, WebSocket timing, V1 close semantics, migration) are documented in README only; no automated test encodes them.
- **Resolution:** *(when resolved)*

### OQ-6.11-004: Unused interactions finalizer test coverage
- **Tags:** `proj-spec/chapters/06.11-http-recorder.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test exercises the `makeReplayState` scope finalizer for partial or zero interaction consumption.
- **Resolution:** *(when resolved)*

### OQ-6.11-005: Parent Behavior heading coverage
- **Tags:** `proj-spec/chapters/06.11-http-recorder.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Parent `## Behavior` has no unique claims besides the child H3s; named tests are listed on those H3 Spec-Anchor lines, not on `#behavior`.
- **Resolution:** *(when resolved)*

### OQ-6.12-1: No in-package tests
- **Tags:** `proj-spec/chapters/06.12-plugin.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/plugin` contains no `*.{test,spec}.*` files. Named coverage for this leaf is unknown until hosts or a later test package encode the export contracts.
- **Resolution:** *(when resolved)*

### OQ-6.12-2: Host load and hook dispatch
- **Tags:** `proj-spec/chapters/06.12-plugin.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** When a host constructs `PluginInput` / `TuiPluginApi` / v2 `PluginContext`, orders hook callbacks, or rebuilds domains after `transform`/`reload` is not specified in this slice (C10). Those facts belong in consuming chapters, not here.
- **Resolution:** *(when resolved)*

### OQ-6.13-1: Package manifest untested
- **Tags:** `proj-spec/chapters/06.13-codemode.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for the CodeMode package manifest (Spec-Anchor `#package-manifest`).
- **Resolution:** *(when resolved)*

### OQ-6.13-2: Authority split untested
- **Tags:** `proj-spec/chapters/06.13-codemode.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for the CodeMode authority split (Spec-Anchor `#authority-split`).
- **Resolution:** *(when resolved)*

### OQ-6.13-3: Non-goals untested
- **Tags:** `proj-spec/chapters/06.13-codemode.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for CodeMode non-goals / out-of-package scope (Spec-Anchor `#non-goals-out-of-package-scope`).
- **Resolution:** *(when resolved)*

### OQ-6.14-1: Host that constructs `TuiInput` and calls `run`
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Which process builds `TuiInput` (URL, headers, `pluginHost`, `TuiConfig.resolve` options such as `terminalSuspend`) is outside `packages/tui` (C10). T1 maps consumers to 6.1 and 6.15.
- **Resolution:** *(when resolved)*

### OQ-6.14-2: Core `Flag` defaults
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** This slice reads `Flag.OPENCODE_*` from `@opencode-ai/core/flag/flag`. Default env/flag values are not specified here.
- **Resolution:** *(when resolved)*

### OQ-6.14-3: `pluginHost` loader
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `TuiPluginHost.start` / `dispose` are injected. How hosts discover, enable, and instantiate TUI plugins (including `createBuiltinPlugins`) is not in this package.
- **Resolution:** *(when resolved)*

### OQ-6.14-4: TuiInput tests
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts the `TuiInput` field set independently of `run` fixtures.
- **Resolution:** *(when resolved)*

### OQ-6.14-5: Parent Behavior heading coverage
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole; coverage is on nested headings.
- **Resolution:** *(when resolved)*

### OQ-6.14-6: Routing tests
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `RouteProvider`, `OPENCODE_ROUTE` parse, continue/fork navigation, or `PluginRouteMissing`.
- **Resolution:** *(when resolved)*

### OQ-6.14-7: Production prompt submit tests
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/tui/test/cli/tui/prompt-submit-race.test.ts` exercises a local `submit` mirror, not `packages/tui/src/component/prompt/index.tsx`. No test found for `session.create` / `session.prompt` / shell / command branches.
- **Resolution:** *(when resolved)*

### OQ-6.14-8: Attention tests
- **Tags:** `proj-spec/chapters/06.14-tui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createTuiAttention` skip reasons, sound pack KV, or text limits.
- **Resolution:** *(when resolved)*

### OQ-6.15-1: Construction test coverage
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found under `packages/cli/**/*.{test,spec}.*` for `package.json` bins/scripts, command flags/defaults, or compile `define` (`OPENCODE_CLI_NAME`).
- **Resolution:** *(when resolved)*

### OQ-6.15-10: Error-handling tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed tests only assert `Missing path parameter: sessionID` and `rawRequest` undefined for a single operation token. Wrapper exit codes, daemon errors, invalid headers, OpenAPI HTTP failures, and Effect/`NodeRuntime.runMain` exit mapping are untested.
- **Resolution:** *(when resolved)*

### OQ-6.15-11: Publish version vs package.json version
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/cli/package.json` `version` is `1.18.30`; `script/build.ts` / `script/publish.ts` stamp `Script.version` / `Script.channel` from `@opencode-ai/script`, which is outside this slice’s allowed paths.
- **Resolution:** *(when resolved)*

### OQ-6.15-12: Imported workspace contracts (C10)
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Concrete behavior of `Global.Path.state`, `InstallationVersion`, `ServerAuth.headers`, `createOpencodeClient` / `v2.health.get` / `v2.agent.list`, `createRoutes`, `TuiConfig.resolve` / `run`, and `HttpServer.formatAddress` lives in 6.2 / 6.5 / 6.8 / 6.14, not in `packages/cli/`. This chapter only records the call sites.
- **Resolution:** *(when resolved)*

### OQ-6.15-2: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole; named tests cover only `#api-command` helpers.
- **Resolution:** *(when resolved)*

### OQ-6.15-3: Native wrapper tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/cli/bin/lildax.cjs` resolution, AVX2/musl `names` order, `OPENCODE_BIN_PATH`, or the install-failure stderr string.
- **Resolution:** *(when resolved)*

### OQ-6.15-4: Compile and publish tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/cli/script/build.ts` or `packages/cli/script/publish.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.15-5: Daemon tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/cli/src/services/daemon.ts` (password file, `server.json`, health, start spawn, stop signals, register).
- **Resolution:** *(when resolved)*

### OQ-6.15-6: Default TUI command tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/cli/src/commands/handlers/default.ts` or `packages/cli/src/tui.ts` (`legacyDefaults` 404 fallbacks).
- **Resolution:** *(when resolved)*

### OQ-6.15-7: Service command tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `service start|restart|status|stop|password` handlers.
- **Resolution:** *(when resolved)*

### OQ-6.15-8: Serve command tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/cli/src/commands/handlers/serve.ts` (port scan from `4096`, `--register`, listen log).
- **Resolution:** *(when resolved)*

### OQ-6.15-9: Migrate and debug agents tests
- **Tags:** `proj-spec/chapters/06.15-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `migrate` (`No migrations to run.`) or `debug agents` JSON stdout.
- **Resolution:** *(when resolved)*

### OQ-6.16-001: Top-level package configuration untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No package test encodes peer dependencies, side effects, or published `files` list.
- **Resolution:** *(when resolved)*

### OQ-6.16-002: Generated asset regeneration untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test verifies `generate:tailwind`, `generate:v2-oc2`, or Vite spritesheet outputs.
- **Resolution:** *(when resolved)*

### OQ-6.16-003: Component library rendering untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No unit test covers v1/v2 component mount or export resolution.
- **Resolution:** *(when resolved)*

### OQ-6.16-004: Style bundle composition untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts CSS import graph for `styles` or `styles/tailwind`.
- **Resolution:** *(when resolved)*

### OQ-6.16-005: Theme system behavior untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `ThemeProvider`, theme JSON loading, or `loadThemeFromUrl`.
- **Resolution:** *(when resolved)*

### OQ-6.16-006: Shared contexts and hooks untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers dialog stack, worker pool selection, filtered list, or auto-scroll hooks.
- **Resolution:** *(when resolved)*

### OQ-6.16-007: Error paths untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts throws from `useDialog`, `loadThemeFromUrl`, theme variant resolution, or `SegmentedControlItemV2` misuse.
- **Resolution:** *(when resolved)*

### OQ-6.16-008: App icon types regeneration path
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `src/components/app-icons/types.ts` is marked generated but `vite.config.ts` has no spritesheet entry for `src/assets/icons/app/` — regeneration command unknown from allowed sources.
- **Resolution:** *(when resolved)*

### OQ-6.16-009: Scripts untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test verifies `build`, `typecheck`, `test`, `dev`, or generate script wiring.
- **Resolution:** *(when resolved)*

### OQ-6.16-010: Build output untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts declaration-only emit to `dist/`.
- **Resolution:** *(when resolved)*

### OQ-6.16-011: Export map untested
- **Tags:** `proj-spec/chapters/06.16-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test resolves `@opencode-ai/ui/*` export paths from `package.json`.
- **Resolution:** *(when resolved)*

### OQ-6.17-001: Package construction untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test encodes `package.json` name, scripts, dependency pins, or `tsconfig.json` compiler options.
- **Resolution:** *(when resolved)*

### OQ-6.17-002: Export map untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test resolves `@opencode-ai/session-ui/*` export paths.
- **Resolution:** *(when resolved)*

### OQ-6.17-003: Pierre defaults untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts `createDefaultOptions` fields or Pierre `poolSize` `2`.
- **Resolution:** *(when resolved)*

### OQ-6.17-004: DataProvider untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `DataProvider` / `useData`.
- **Resolution:** *(when resolved)*

### OQ-6.17-005: Message UI registry untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `renderable` (`todowrite`, question pending/running), `getTool` aliases, paced text (`TEXT_RENDER_*`), `Message`/`AssistantParts` mount, and `writeClipboard` have no tests in allowed globs.
- **Resolution:** *(when resolved)*

### OQ-6.17-006: v1 review size gate untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `MAX_DIFF_CHANGED_LINES` (`additions + deletions > 500`) in `session-review.tsx` is untested; only v2 `shouldVirtualizeReviewDiff` (`Math.max` of line arrays `> 500`) is tested.
- **Resolution:** *(when resolved)*

### OQ-6.17-007: Worker and sanitize error strings untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test constructs `MarkdownWorkerUnavailableError` / terminate paths, or asserts `"Markdown highlighting worker failed"` / `"Markdown worker response failed"` / `sanitizeMarkdown` empty fallback.
- **Resolution:** *(when resolved)*

### OQ-6.17-008: Tool error and retry copy untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `ToolErrorCard` prefix stripping / i18n tool-name map or `SessionRetry` quota/truncate rules.
- **Resolution:** *(when resolved)*

### OQ-6.17-009: FileSearchBar count label untested
- **Tags:** `proj-spec/chapters/06.17-session-ui.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts `FileSearchBar` shows `"0/0"` when `count` is 0, else `` `${index + 1}/${count}` ``.
- **Resolution:** *(when resolved)*

### OQ-6.18-1: Non-web host of AppInterface
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Who mounts `AppInterface` with `platform: "desktop"`, sidecar/SSH servers, health checks enabled, and `window.api`? Not in `packages/app` allowed paths (T1 OQ-T1-4).
- **Resolution:** *(when resolved)*

### OQ-6.18-2: Construction scripts and Vite defaults
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `package.json` scripts, `vite.config.ts` port `3000`, or `OPENCODE_CHANNEL` mapping in `vite.js`.
- **Resolution:** *(when resolved)*

### OQ-6.18-3: Web entry tests
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `authFromToken` / `authTokenFromCredentials` are covered by `server.test.ts`. No tests found for `entry.tsx` URL selection, `auth_token` stripping, `disableHealthCheck`, or `openExternal` / `notify` rules.
- **Resolution:** *(when resolved)*

### OQ-6.18-4: App shell tests
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `AppBaseProviders`, `AppInterface` provider order, or `BodyDesignClass`.
- **Resolution:** *(when resolved)*

### OQ-6.18-5: ConnectionGate UI tests
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `ConnectionGate` timeout `"10 seconds"`, splash overlay, or `ConnectionError` copy/retry.
- **Resolution:** *(when resolved)*

### OQ-6.18-6: Router composition tests
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No unit tests found for `Routes` in `app.tsx` or `DirectoryLayout` invalid-dir toast; coverage is helper-level plus e2e.
- **Resolution:** *(when resolved)*

### OQ-6.18-7: ErrorPage tests
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `ErrorPage` render or init-error (`MCPFailed` / `ProviderAuthError` / `APIError`) formatting. `errorDescriptionKey` is covered by `error-description.test.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.19-1: Renderer integration / first-launch onboarding IPC untested
- **Tags:** `proj-spec/chapters/06.19-desktop.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for first-launch onboarding IPC (Spec-Anchor `#renderer-integration`).
- **Resolution:** *(when resolved)*

### OQ-6.19-2: Startup and single-instance untested
- **Tags:** `proj-spec/chapters/06.19-desktop.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for main blocking `restoreMainWindows` on loading fiber including v1 health wait (Spec-Anchor `#startup-and-single-instance`).
- **Resolution:** *(when resolved)*

### OQ-6.19-3: Local backend sidecar stall/exit untested
- **Tags:** `proj-spec/chapters/06.19-desktop.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for v1 sidecar stall/exit spawn paths (Spec-Anchors `#local-backend-sidecar`, `#error-handling`).
- **Resolution:** *(when resolved)*

### OQ-6.19-4: Package scripts untested
- **Tags:** `proj-spec/chapters/06.19-desktop.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for desktop package scripts (Spec-Anchor `#package-scripts`).
- **Resolution:** *(when resolved)*

### OQ-6.19-5: Process architecture untested
- **Tags:** `proj-spec/chapters/06.19-desktop.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for desktop process architecture (Spec-Anchor `#process-architecture`).
- **Resolution:** *(when resolved)*

### OQ-6.19-6: Native UX constraints untested
- **Tags:** `proj-spec/chapters/06.19-desktop.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for native UX constraints (Spec-Anchor `#native-ux-constraints`).
- **Resolution:** *(when resolved)*

### OQ-6.2-1: Schema types re-exported by Core
- **Tags:** `proj-spec/chapters/06.2-core.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `SessionSchema.Info`, `PromptInput.Prompt`, and `SessionInput.Delivery` are imported from `@opencode-ai/schema`. Literal deliveries used in Core are `"steer"` and `"queue"`. Full field-level contracts belong in chapter 8 (C10).
- **Resolution:** *(when resolved)*

### OQ-6.2-2: Core `bin.opencode` path missing on disk
- **Tags:** `proj-spec/chapters/06.2-core.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/core/package.json` `bin.opencode` is `./bin/opencode`, but `packages/core/bin/` is absent in this tree. Whether install/CLI packaging lives in 6.1 / 10.1 is outside this slice.
- **Resolution:** *(when resolved)*

### OQ-6.2-3: Complete `Config.Info` field catalog
- **Tags:** `proj-spec/chapters/06.2-core.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `Config.Info` has many optional keys beyond `$schema` / `shell` / `model` / `default_agent`. A full key/default table was not expanded in this leaf.
- **Resolution:** *(when resolved)*

### OQ-6.2-4: Package export-map and dependency-direction tests
- **Tags:** `proj-spec/chapters/06.2-core.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test name was found that asserts the `exports` map or that Core must not depend on Server/Client.
- **Resolution:** *(when resolved)*

### OQ-6.2-5: `Database.path()` env matrix
- **Tags:** `proj-spec/chapters/06.2-core.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `Database.path()` branches on `OPENCODE_DB`, `InstallationChannel`, and `OPENCODE_DISABLE_CHANNEL_DB`. No dedicated test name was found that asserts that table.
- **Resolution:** *(when resolved)*

### OQ-6.20-001: Share payload type contracts live outside this slice
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `Share.Data` uses `z.custom` for `@opencode-ai/sdk/v2` `Session` / `Message` / `Part` / `SnapshotFileDiff` / `Model`. Field-level contracts are outside `packages/enterprise/` allowed paths.
- **Resolution:** *(when resolved)*

### OQ-6.20-002: SST `SUPPORT_API_KEY` binding source
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** The support delete route reads `Resource.SUPPORT_API_KEY.value`. `packages/enterprise/sst-env.d.ts` only references `../../sst-env.d.ts`; how SST binds that key is outside this slice.
- **Resolution:** *(when resolved)*

### OQ-6.20-003: HTTP status for share domain errors and validators
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `/api/share*` does not catch `Share.Errors` or document Hono/`hono-openapi` `validator` failure status. No test in this package hits those routes.
- **Resolution:** *(when resolved)*

### OQ-6.20-004: Package construction untested
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test encodes package scripts, Vite port/host, Nitro Cloudflare preset, or web manifest fields.
- **Resolution:** *(when resolved)*

### OQ-6.20-005: Storage adapter errors and env defaults untested
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Tests only cover `Storage.list` range/limit. No test asserts `s3`/`r2` selection, `No storage adapter configured`, 404→`undefined`, or `Failed to read|write|remove|list` messages.
- **Resolution:** *(when resolved)*

### OQ-6.20-006: HTTP API and share viewer untested
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers Hono routes, share URL construction, OG image query, `session_status` always `idle`, or `ErrorBoundary` / `NotFound` mapping.
- **Resolution:** *(when resolved)*

### OQ-6.20-007: Locale, index, and 404 untested
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `Accept-Language` / `UiI18nBridge`, `/` `Hello World`, or the catch-all `Not Found` page.
- **Resolution:** *(when resolved)*

### OQ-6.20-008: Some share domain paths untested
- **Tags:** `proj-spec/chapters/06.20-enterprise.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Tests do not assert `AlreadyExists`, `id` as `sessionID.slice(-8)` / `test_` prefix, `remove` InvalidSecret, `syncOld`, or exact `Share.Errors` message strings (invalid secret / missing share use `toThrow()` only).
- **Resolution:** *(when resolved)*

### OQ-6.21-1: Construction test coverage
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `package.json` scripts, Vite/Nitro config, session cookie flags, or `LOCALES`.
- **Resolution:** *(when resolved)*

### OQ-6.21-10: Proxy route tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for docs, `/data` HTML rewrite/cache, `/stats` 308, or `/t` enterprise proxy.
- **Resolution:** *(when resolved)*

### OQ-6.21-11: Download tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `/download/:channel/:platform`.
- **Resolution:** *(when resolved)*

### OQ-6.21-12: Changelog / OpenAPI / OAuth tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `loadChangelog`, `/openapi.json`, or `/oauth/opencode/client.json`.
- **Resolution:** *(when resolved)*

### OQ-6.21-13: Honeycomb webhook tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/console/app/src/routes/honeycomb/webhook.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.21-14: Enterprise form tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for honeypot `alias`, EmailOctopus/Salesforce/AWS fan-out, or DEV-only success.
- **Resolution:** *(when resolved)*

### OQ-6.21-15: Sitemap tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `script/generate-sitemap.ts`. Docs file inventory is read from `packages/web/src/content/docs`, which is outside this slice’s allowed paths.
- **Resolution:** *(when resolved)*

### OQ-6.21-16: Error-handling tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert Zen 401/403/429/499/500 envelopes, Stripe 500, or Honeycomb 401/400/502.
- **Resolution:** *(when resolved)*

### OQ-6.21-17: Zen HTTP mapping tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `handler` catch status codes or `retry-after`.
- **Resolution:** *(when resolved)*

### OQ-6.21-18: Other HTTP error tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for auth callback 500, download 404/502, or changelog 503.
- **Resolution:** *(when resolved)*

### OQ-6.21-19: Non-production docs hostname
- **Tags:** `proj-spec/chapters/06.21-console-app.md`, `proj-spec/chapters/06.27-web.md`
- **Discovered in:** REVIEW-SPEC Part IIIb C9 (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Off production, 6.21 proxies `/docs` and `/s/:id` to `docs.dev.opencode.ai`. 6.27 Astro `site` is `https://${SST_STAGE}.opencode.ai` (`SST_STAGE` default `"dev"` → `https://dev.opencode.ai`) with `base` `/docs`. Is `docs.dev.opencode.ai` a DNS alias of `dev.opencode.ai`, or should both chapters name one matching origin?
- **Resolution:** *(when resolved)*

### OQ-6.21-2: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent Behavior heading as a whole; coverage is only on nested H3s.
- **Resolution:** *(when resolved)*

### OQ-6.21-3: Marketing page tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for landers, `/black` pause, `github()`, EmailOctopus signup, or Discord/Feishu redirects.
- **Resolution:** *(when resolved)*

### OQ-6.21-4: Auth route tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `getActor`, OpenAuth authorize/exchange, logout, or migration redirect.
- **Resolution:** *(when resolved)*

### OQ-6.21-5: Zen handler integration tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Existing tests cover `isPeakPricing`, `getRetryAfterDay`, Muse Spark helpers, provider `extractUsage`/`normalizeUsage`, and `prepareRequestBody` only. No tests found for `handler` auth, billing, provider selection, or HTTP status mapping.
- **Resolution:** *(when resolved)*

### OQ-6.21-6: Models and Go usage HTTP tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `/zen/v1/models`, `/zen/go/v1/models`, or `/zen/go/v1/usage`.
- **Resolution:** *(when resolved)*

### OQ-6.21-7: Inference proxy tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `proxyInference` path map, migrated-workspace forwarding, or `inferenceUnavailable`.
- **Resolution:** *(when resolved)*

### OQ-6.21-8: Stripe webhook tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/console/app/src/routes/stripe/webhook.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.21-9: Support API tests
- **Tags:** `proj-spec/chapters/06.21-console-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for support Bearer auth or action payloads.
- **Resolution:** *(when resolved)*

### OQ-6.22-001: Package construction untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts package names, scripts, or workspace dependency edges for the five console platform packages.
- **Resolution:** *(when resolved)*

### OQ-6.22-002: Resource export map untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers Cloudflare vs Node `Resource` proxy behavior or the missing-link error string.
- **Resolution:** *(when resolved)*

### OQ-6.22-003: Identifier and PlanetScale wiring untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `Identifier.create` prefixes/`given` validation or `Database.use` / `transaction` nesting.
- **Resolution:** *(when resolved)*

### OQ-6.22-004: Billing constants untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts `ITEM_*` strings, reload defaults, `calculateFeeInCents`, or `centsToMicroCents`.
- **Resolution:** *(when resolved)*

### OQ-6.22-005: Actor types untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `Actor.Info` variants, `UserRole`, or OpenAuth `subjects`.
- **Resolution:** *(when resolved)*

### OQ-6.22-006: Parent behavior heading untested as a unit
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No single test module covers the console-platform behavior surface; child headings have mixed coverage.
- **Resolution:** *(when resolved)*

### OQ-6.22-007: Actor/context/database sessions untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts `Context.NotFound`, `Actor.assertAdmin`, or transaction effects.
- **Resolution:** *(when resolved)*

### OQ-6.22-008: Account APIs untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `Account.create` / `remove` / `fromID`.
- **Resolution:** *(when resolved)*

### OQ-6.22-009: Workspace APIs untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers create/update/`setDefaultRegion`/unblock/remove.
- **Resolution:** *(when resolved)*

### OQ-6.22-010: User invite flow untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers invite, join-invited-workspaces, self-guards, or SES send.
- **Resolution:** *(when resolved)*

### OQ-6.22-011: API key generation untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts `sk-` + 64 charset generation, `keyDisplay`, or admin vs member list/remove.
- **Resolution:** *(when resolved)*

### OQ-6.22-012: Stripe billing untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers reload, coupons, checkout URLs, Black/Lite subscribe/unsubscribe, or the combine-currencies retry.
- **Resolution:** *(when resolved)*

### OQ-6.22-013: Quota reset untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `Quota.reset` lite vs subscription counters.
- **Resolution:** *(when resolved)*

### OQ-6.22-014: Referral domain untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `normalizeCode`, reward apply, or self-referral rejection.
- **Resolution:** *(when resolved)*

### OQ-6.22-015: Model disable/list untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `ZenData` `cost200K.threshold` is tested; `Model.enable`/`disable`/`isDisabled` and `ZenData.list` concatenation are not.
- **Resolution:** *(when resolved)*

### OQ-6.22-016: BYOK providers untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `Provider.create`/`list`/`remove`.
- **Resolution:** *(when resolved)*

### OQ-6.22-017: Lite/Black catalog helpers untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers `planToPriceID` / `priceIDToPlan` default `"20"` or `LiteData.planName`.
- **Resolution:** *(when resolved)*

### OQ-6.22-018: OpenAuth issuer untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers GitHub/Google success, `@anoma.ly` non-prod gate, or Default workspace creation.
- **Resolution:** *(when resolved)*

### OQ-6.22-019: Log processor untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers pathname filter, `_metric:` parse, lake ingest, or `ipPrefix`.
- **Resolution:** *(when resolved)*

### OQ-6.22-020: TPS stats worker untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers POST-only 405 or 30-interval aggregation.
- **Resolution:** *(when resolved)*

### OQ-6.22-021: Invite email untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts `InviteEmail` URLs, SES `FromEmailAddress`, or subject string.
- **Resolution:** *(when resolved)*

### OQ-6.22-022: Support lookup untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test covers identifier routing (`wrk_` / `key_` / `sk-` / email) or display formatting.
- **Resolution:** *(when resolved)*

### OQ-6.22-023: Error strings untested
- **Tags:** `proj-spec/chapters/06.22-console-platform.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Redirect allowlist is tested; other thrown/HTTP error strings in this chapter are not.
- **Resolution:** *(when resolved)*

### OQ-6.23-1: Locale primitives live in console app
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/stats/app/src/lib/language.ts` re-exports `LOCALES`, `LOCALE_COOKIE`, `LOCALE_HEADER`, `cookie`, `dir`, `tag`, `localeFromRequest`, and related helpers from `packages/console/app/src/lib/language` (C10 overflow). Exact locale id list, cookie string, and Accept-Language detection belong in the console-app chapter (map id 6.21), not restated here.
- **Resolution:** *(when resolved)*

### OQ-6.23-10: Error-handling tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert newsletter JSON errors, `#app` throw, or in-page not-found copy.
- **Resolution:** *(when resolved)*

### OQ-6.23-11: Stats-core symbols outside this slice
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** App files import `statModel` from `@opencode-ai/stats-core/domain/model-normalization`, `runtime` from `@opencode-ai/stats-core/runtime`, and `getStatsHomeData` / `getStatsLabData` / `getStatsModelData` / `getStatsModelsComparisonData` from `@opencode-ai/stats-core/domain/home` (C10 overflow; those modules are 6.24). Nested keys such as `Go["2M"]` and `leaderboard["All Users"]["2M"]` are observed at the app call site; `statModel` / `runtime.runPromise` behavior and map shapes belong in 6.24.
- **Resolution:** *(when resolved)*

### OQ-6.23-12: Stats public origin
- **Tags:** `proj-spec/chapters/06.21-console-app.md`, `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** REVIEW-SPEC Part IIIb C9 (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** 6.21 `statsProxy` uses `stats.opencode.ai` in production and `stats.dev.opencode.ai` otherwise. 6.23 hardcodes `baseUrl` `https://opencode.ai` with Vite `base` `/data/`. Which public origin (and path) is canonical for the stats site?
- **Resolution:** *(when resolved)*

### OQ-6.23-2: Construction test coverage
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found under `packages/stats/app/**/*.{test,spec}.*` for package scripts, Vite `base`, Nitro preset, or SST secret wiring.
- **Resolution:** *(when resolved)*

### OQ-6.23-3: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole.
- **Resolution:** *(when resolved)*

### OQ-6.23-4: Locale, theme, and cache tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `strip`/`route`/`localizedUrl`, theme key `opencode:stats-theme`, `setStatsPageCacheHeaders`, or `getGitHubStars`.
- **Resolution:** *(when resolved)*

### OQ-6.23-5: Model catalog tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `loadModelCatalog`, `findModelCatalogEntry`, lab aliases, or search-index HTML parse.
- **Resolution:** *(when resolved)*

### OQ-6.23-6: Home page tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for Go/`2M` slice binding, `priceTokenCostFromCatalog`, leaderboard pairing, or formatters.
- **Resolution:** *(when resolved)*

### OQ-6.23-7: Lab and model page tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for lab/model not-found UI or `glm-5.3-flash` / `ox-alpha` former-name handling.
- **Resolution:** *(when resolved)*

### OQ-6.23-8: Comparison and sitemap tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for family resolution, canonical paths, `?add=` extras, robots `noindex` when `models.length > 2`, or sitemap XML.
- **Resolution:** *(when resolved)*

### OQ-6.23-9: Newsletter and health tests
- **Tags:** `proj-spec/chapters/06.23-stats-app.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `GET` `{ ok: true, app: "stats" }` or EmailOctopus `PUT` / status 400/502.
- **Resolution:** *(when resolved)*

### OQ-6.24-1: Construction test coverage
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found under `packages/stats/core/**/*.{test,spec}.*` or `packages/stats/server/**/*.{test,spec}.*` for package scripts, env defaults, Docker, or generate wiring.
- **Resolution:** *(when resolved)*

### OQ-6.24-10: Error-handling tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert ingest HTTP statuses, `R2SqlQueryError` / `DatabaseError` / `StatsDataError` messages, or CLI exit codes.
- **Resolution:** *(when resolved)*

### OQ-6.24-12: Read-model coverage beyond retention pooling
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `home.test.ts` covers `buildRetentionEntries` only; leaderboard, usage buckets, geo `AQ` filter, query cache, and dataset `'zen'` SQL are untested in allowed test globs.
- **Resolution:** *(when resolved)*

### OQ-6.24-2: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole; coverage is only on nested headings that name tests.
- **Resolution:** *(when resolved)*

### OQ-6.24-3: Lake ingest HTTP tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `/health`, `/ready`, POST `/`, or authorization in `packages/stats/server`.
- **Resolution:** *(when resolved)*

### OQ-6.24-4: Firehose ingest tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `Ingest.write`, `LAKE_TYPE`, or Firehose retry in `packages/stats/server`.
- **Resolution:** *(when resolved)*

### OQ-6.24-5: Stats sync daemon tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/stats/server/src/stat-sync.ts` or `syncStats` in `packages/stats/core/src/stat-sync.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.24-6: Persistence repository tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for Drizzle upserts, `deleteRetiredDimensions`, `RetentionStatRepo.replace`, or `Database.migrate`.
- **Resolution:** *(when resolved)*

### OQ-6.24-7: Athena client tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/stats/core/src/athena.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.24-8: Honeycomb backfill tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/stats/core/src/honeycomb-backfill.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.24-9: Unique-users ensure tests
- **Tags:** `proj-spec/chapters/06.24-stats-backend.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/stats/core/src/ensure-unique-users.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.25-1: HTTP route test coverage
- **Tags:** `proj-spec/chapters/06.25-function.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for Hono HTTP routes in `packages/function`.
- **Resolution:** *(when resolved)*

### OQ-6.25-2: SyncServer test coverage
- **Tags:** `proj-spec/chapters/06.25-function.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for `SyncServer` Durable Object behavior in `packages/function`.
- **Resolution:** *(when resolved)*

### OQ-6.25-3: Construction test coverage
- **Tags:** `proj-spec/chapters/06.25-function.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for package construction/configuration in `packages/function`.
- **Resolution:** *(when resolved)*

### OQ-6.25-4: Behavior heading test coverage
- **Tags:** `proj-spec/chapters/06.25-function.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found that cover the parent `## Behavior` heading as a whole in `packages/function`.
- **Resolution:** *(when resolved)*

### OQ-6.26-1: Construction test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found under `packages/slack` for package construction/configuration.
- **Resolution:** *(when resolved)*

### OQ-6.26-2: Behavior heading test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found that cover the parent `## Behavior` heading as a whole in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.26-3: Process start test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for Bolt App start, `createOpencode({ port: 0 })`, or `app.start()` in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.26-4: Session map test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for session keying `` `${channel}-${thread}` `` in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.26-5: Incoming message test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for `app.message` skip rules, session create/share, prompt, or reply text assembly in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.26-6: Tool completion test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for `message.part.updated` tool posts in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.26-7: `/test` command test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for `app.command("/test")` in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.26-8: Error handling test coverage
- **Tags:** `proj-spec/chapters/06.26-slack.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found for session create/prompt user-facing error strings or swallowed tool `postMessage` failures in `packages/slack`.
- **Resolution:** *(when resolved)*

### OQ-6.27-01: npm scripts untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes `@opencode-ai/web` npm script commands.
- **Resolution:** *(when resolved)*

### OQ-6.27-02: Integrations and content collections untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes Starlight integrations or content collection wiring.
- **Resolution:** *(when resolved)*

### OQ-6.27-03: Build-time config schema generation untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes post-build `configSchema` schema generation.
- **Resolution:** *(when resolved)*

### OQ-6.27-04: Workspace dependency untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes `opencode` workspace type-import usage in share UI.
- **Resolution:** *(when resolved)*

### OQ-6.27-05: Site surfaces untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes docs, landing, share, or plain-text export routes under `/docs`.
- **Resolution:** *(when resolved)*

### OQ-6.27-06: Internationalization untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes locale middleware, cookie writes, or language select behavior.
- **Resolution:** *(when resolved)*

### OQ-6.27-07: Open Graph images untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes docs or share Open Graph image URL selection in `Head.astro`.
- **Resolution:** *(when resolved)*

### OQ-6.27-08: Share viewer client untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes share WebSocket client connection, reconnect, or message handling.
- **Resolution:** *(when resolved)*

### OQ-6.27-09: Robots policy untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes `public/robots.txt` disallow rules vs deployed `/docs/s/` routes.
- **Resolution:** *(when resolved)*

### OQ-6.27-10: Product naming in UI copy untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes English i18n product naming strings.
- **Resolution:** *(when resolved)*

### OQ-6.27-11: HTTP error paths untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes HTTP 404/302 or share client error paths listed under Error handling.
- **Resolution:** *(when resolved)*

### OQ-6.27-12: Construction defaults untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes the Astro site, base, output, adapter, and `config.mjs` defaults in the construction table.
- **Resolution:** *(when resolved)*

### OQ-6.27-13: Behavior summary untested
- **Tags:** `proj-spec/chapters/06.27-web.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated test encodes the H2 Behavior summary for `@opencode-ai/web` site surfaces.
- **Resolution:** *(when resolved)*

### OQ-6.3-1: No tests for Node client construction or package manifests
- **Tags:** `proj-spec/chapters/06.3-sqlite-adapters.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Package manifests/exports and `packages/effect-sqlite-node` constructor wiring have no dedicated test in allowed paths. Drizzle `makeWithDefaults` is covered by `packages/effect-drizzle-sqlite/test/sqlite.test.ts`.
- **Resolution:** *(when resolved)*

### OQ-6.3-2: No tests for Node client operations
- **Tags:** `proj-spec/chapters/06.3-sqlite-adapters.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/effect-sqlite-node` has no `*.test.*` / `*.spec.*` covering Node client operations.
- **Resolution:** *(when resolved)*

### OQ-6.4-001: Protocol package tests cover only session cursor codecs
- **Tags:** `proj-spec/chapters/06.4-protocol.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Under `packages/protocol/`, the only tests found are `session-cursor.test.ts` (`round trips without Node globals`, `decodes numeric paging inputs`). Remaining Protocol `HttpApi` groups, middleware slots, package exports, error classes, and `ProjectCopyError` have no named tests in this package.
- **Resolution:** *(when resolved)*

### OQ-6.5-001: Server package has no tests under allowed paths
- **Tags:** `proj-spec/chapters/06.5-server.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Under `packages/server/`, no `*.test.*` / `*.spec.*` files were found. Auth, CORS, location middleware, route layers, and handler mappings therefore have no named tests in this package.
- **Resolution:** *(when resolved)*

### OQ-6.5-002: PTY connect token string values live in Protocol
- **Tags:** `proj-spec/chapters/06.5-server.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Server compares `PTY_CONNECT_TOKEN_HEADER` / `PTY_CONNECT_TOKEN_HEADER_VALUE` / `PTY_CONNECT_TICKET_QUERY` and calls `hasPtyConnectTicketURL` imported from `@opencode-ai/protocol/groups/pty`. Literal header names, ticket query name, and ticket-URL path pattern are not restated here so Protocol remains the canonical home ([6.4 Protocol](06.4-protocol.md)).
- **Resolution:** *(when resolved)*

### OQ-6.6-001: Package manifest defaults untested
- **Tags:** `proj-spec/chapters/06.6-httpapi-codegen.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Package name, `private`, exports map, and dependency version pins in `packages/httpapi-codegen/package.json` have no dedicated behavioral test in this package.
- **Resolution:** *(when resolved)*

### OQ-6.6-002: Workspace generate token strings untested here
- **Tags:** `proj-spec/chapters/06.6-httpapi-codegen.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** C9 consistency token `generate` strings are recorded from `tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md`; this package has no test that those workspace commands exist or invoke `@opencode-ai/httpapi-codegen`.
- **Resolution:** *(when resolved)*

### OQ-6.7-001: Manifest and generate-token coverage
- **Tags:** `proj-spec/chapters/06.7-client.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/client/package.json` name, exports, dependency pins, `check:generated`, `typecheck`, and C9 generate-token strings other than this package’s `bun run generate` have no dedicated test under `packages/client/`.
- **Resolution:** *(when resolved)*

### OQ-6.7-002: README vs `script/build.ts` compile input
- **Tags:** `proj-spec/chapters/06.7-client.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/client/README.md` states the build compiler reads `@opencode-ai/server/api`; `packages/client/script/build.ts` compiles `ClientApi` from `packages/client/src/contract.ts`. Equivalence to Server is asserted in `"client and Server contracts generate identically"`, not as the generate script’s compile argument.
- **Resolution:** *(when resolved)*

### OQ-6.7-003: Untested contract rename rows
- **Tags:** `proj-spec/chapters/06.7-client.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `groupNames` and `endpointNames` rows other than those asserted in `"exposes every standard HTTP API group"` are specified only by `packages/client/src/contract.ts`; no test names every mapping.
- **Resolution:** *(when resolved)*

### OQ-6.7-004: Other `ClientError` reasons
- **Tags:** `proj-spec/chapters/06.7-client.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Promise tests name `ClientError` reason `"MalformedResponse"` only. Other reason strings, if any, are emitted by generated `src/generated` code and are not specified here as source of truth (C5).
- **Resolution:** *(when resolved)*

### OQ-6.8-1: `bun dev generate` OpenAPI input outside slice
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `script/build.ts` invokes an external `bun dev generate` step outside this slice’s allowed paths; the authoritative OpenAPI contract for that input is not specified here.
- **Resolution:** *(when resolved)*

### OQ-6.8-2: Construction test coverage
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Named coverage for construction is the Session history numeric-query patch test; package exports, launcher option defaults (including `port` `4096`), client config, and the v2 `data` helper are untested in allowed paths.
- **Resolution:** *(when resolved)*

### OQ-6.8-3: Package exports tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/sdk/js/package.json` export subpaths or published `files` `dist`.
- **Resolution:** *(when resolved)*

### OQ-6.8-4: Server/TUI launcher option defaults
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createOpencodeServer` defaults `hostname` `"127.0.0.1"`, `port` `4096`, `timeout` `5000`, or `TuiOptions` flag forwarding.
- **Resolution:** *(when resolved)*

### OQ-6.8-5: Client config tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createOpencodeClient` `fetch` timeout wrapper, `x-opencode-directory` / `x-opencode-workspace` headers, or `createOpencode` passing `server.url`.
- **Resolution:** *(when resolved)*

### OQ-6.8-6: v2 `data` helper tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `data.message.user` placeholder ids `"asdasd"` or `role: "user"`.
- **Resolution:** *(when resolved)*

### OQ-6.8-7: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that encode `## Behavior` as a whole (HTTP facades, interceptors, local server/TUI launchers, process utilities).
- **Resolution:** *(when resolved)*

### OQ-6.8-8: HTTP client facade tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createOpencodeClient` wrapping generated `OpencodeClient` with interceptors.
- **Resolution:** *(when resolved)*

### OQ-6.8-9: Request interceptor tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for v1/v2 `rewrite` GET/HEAD directory/workspace query rewrite or header strip.
- **Resolution:** *(when resolved)*

### OQ-6.8-10: v2 HTML response interceptor tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for the v2 `text/html` error `"Request is not supported by this version of OpenCode Server (Server responded with text/html)"`.
- **Resolution:** *(when resolved)*

### OQ-6.8-11: Local server launcher tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createOpencodeServer` spawn of `opencode serve`, listen-line URL parse, timeout, or early-exit errors.
- **Resolution:** *(when resolved)*

### OQ-6.8-12: TUI launcher tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createOpencodeTui` spawn flags, `stdio: "inherit"`, or `close()`.
- **Resolution:** *(when resolved)*

### OQ-6.8-13: Process utility tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `stop` Windows `taskkill` vs `proc.kill()`, or `bindAbort` cleanup.
- **Resolution:** *(when resolved)*

### OQ-6.8-14: SDK error-handling tests
- **Tags:** `proj-spec/chapters/06.8-sdk.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `createOpencodeServer` timeout/parse/exit errors, v2 HTML interceptor, or `wrapClientError` `throwOnError` formatting.
- **Resolution:** *(when resolved)*

### OQ-6.9-001: Manifest, SST stub, and constructor options
- **Tags:** `proj-spec/chapters/06.9-sdk-next.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/sdk-next/package.json` name, export map, scripts, and `sst-env.d.ts` have no dedicated test. Constructor fields `baseUrl`, `disableLogger`, `preconnect`, and the Service identifier are specified by `packages/sdk-next/src/opencode.ts` only.
- **Resolution:** *(when resolved)*

### OQ-6.9-002: README claims without in-slice tests
- **Tags:** `proj-spec/chapters/06.9-sdk-next.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test in `packages/sdk-next/test/` asserts absence of a TCP listener, `web.dispose` / Scope teardown, Location `ToolRegistry` overlay, or `sessions.events` `after` replay. Router/middleware/codec equivalence is named in `packages/sdk-next/README.md` and implemented via `createEmbeddedRoutes` / Client `OpenCode.make`; those symbols’ internals are specified in [6.5 Server](06.5-server.md) and [6.7 Client](06.7-client.md), not in this slice’s sources.
- **Resolution:** *(when resolved)*

### OQ-6.9-003: Full client method catalog
- **Tags:** `proj-spec/chapters/06.9-sdk-next.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `OpenCode.create` spreads the Client Effect instance (`packages/sdk-next/src/opencode.ts`). Methods other than those named in `packages/sdk-next/test/embedded.test.ts` are not enumerated in this slice.
- **Resolution:** *(when resolved)*

### OQ-6.9-004: Other error tags
- **Tags:** `proj-spec/chapters/06.9-sdk-next.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Only `SessionNotFoundError` and `MessageNotFoundError` are asserted in `packages/sdk-next/test/embedded.test.ts`. Other router/client error `_tag` values, if any, are not specified from this slice.
- **Resolution:** *(when resolved)*

### OQ-7.1-1: Construction test coverage
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No automated tests found under `packages/server/**/*.{test,spec}.*` or `packages/protocol/**/*.{test,spec}.*` for package manifests, `HttpApi.make("server")` OpenAPI annotations, `openapiPath`, auth env defaults, or `createRoutes` / `createEmbeddedRoutes`.
- **Resolution:** *(when resolved)*

### OQ-7.1-2: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole; named coverage is only `SessionsCursor` / `SessionHistoryQuery` under a nested heading.
- **Resolution:** *(when resolved)*

### OQ-7.1-3: HttpApi composition tests
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for group registration order or middleware placement in `packages/protocol/src/api.ts`.
- **Resolution:** *(when resolved)*

### OQ-7.1-4: Endpoint catalog tests
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert HTTP methods, paths, or OpenAPI identifiers for the catalog in allowed test globs.
- **Resolution:** *(when resolved)*

### OQ-7.1-5: Location middleware tests
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `location[directory]` / `x-opencode-directory` / `process.cwd()` selection or session-location `Invalid session ID` / `Session not found` mapping.
- **Resolution:** *(when resolved)*

### OQ-7.1-6: Authentication tests
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for Basic `/^Basic\s+(.+)$/i`, `auth_token`, `Authentication required`, `www-authenticate`, or PTY ticket auth skip.
- **Resolution:** *(when resolved)*

### OQ-7.1-7: Event SSE and PTY connect tests
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `server.connected` SSE, heartbeat, CORS origin allowlist, `x-opencode-ticket`, or PTY connect empty 404/403.
- **Resolution:** *(when resolved)*

### OQ-7.1-8: Error-handling tests
- **Tags:** `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert `httpApiStatus` values or the emitted error strings in the table above.
- **Resolution:** *(when resolved)*

### OQ-7.2-001: Export maps and factory options untested as a catalog
- **Tags:** `proj-spec/chapters/07.2-sdk-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test in `packages/client/`, `packages/sdk/js/`, or `packages/sdk-next/` asserts `package.json` `exports` keys, `files: ["dist"]`, or the full `ServerOptions` / `TuiOptions` / `createOpencodeClient` option tables.
- **Resolution:** *(when resolved)*

### OQ-7.2-002: Untested client group methods
- **Tags:** `proj-spec/chapters/07.2-sdk-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Tests name method keys only for `messages`, `integrations`, `files`, `ptys`, `sessions` (listed methods), and `events.subscribe`. Other groups (`health`, `location`, `agents`, `models`, `providers`, `credentials`, `permissions`, `commands`, `skills`, `questions`, `references`, `projectCopies`) are asserted as object keys only. Remaining endpoint names come from `endpointNames` / generated emission and are not enumerated here as source of truth (C5).
- **Resolution:** *(when resolved)*

### OQ-7.2-003: Legacy `OpencodeClient` method catalog
- **Tags:** `proj-spec/chapters/07.2-sdk-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No in-slice test lists `OpencodeClient` resource methods. v1 methods come from checked-in `packages/sdk/js/src/gen/` (not emitted by `script/build.ts`). v2 methods in `src/v2/gen/` are generated from an OpenAPI document produced outside this slice’s allowed paths. Exhaustive method names are therefore not specified here.
- **Resolution:** *(when resolved)*

### OQ-7.2-004: sdk-next methods beyond embedded tests
- **Tags:** `proj-spec/chapters/07.2-sdk-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `OpenCode.create` spreads the Client Effect instance. Methods other than those named in `packages/sdk-next/test/embedded.test.ts` are not listed in this slice. `Tool.make` / `Failure` / `RegistrationError` semantics live in `@opencode-ai/core/tool/tool`, which is outside this chapter’s allowed paths except as a re-export.
- **Resolution:** *(when resolved)*

### OQ-7.2-005: Untested SDK error strings and other `ClientError` reasons
- **Tags:** `proj-spec/chapters/07.2-sdk-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Legacy server/TUI/`wrapClientError` / v2 HTML interceptor strings have no test under `packages/sdk/js/`. Promise tests name `ClientError` reason `"MalformedResponse"` only; other reason strings, if any, are emitted by generated client code and are not specified here as source of truth (C5).
- **Resolution:** *(when resolved)*

### OQ-7.3-1: Construction / wrapper env tests
- **Tags:** `proj-spec/chapters/07.3-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found under allowed `packages/opencode/**/*.{test,spec}.*` or `packages/cli/**/*.{test,spec}.*` for `package.json` `bin` fields, `OPENCODE_BIN_PATH`, AVX2/musl package-name lists, or `OPENCODE_CLI_NAME`.
- **Resolution:** *(when resolved)*

### OQ-7.3-2: Native wrapper spawn tests
- **Tags:** `proj-spec/chapters/07.3-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/opencode/bin/opencode` or `packages/cli/bin/lildax.cjs` (signal forwarding, missing-binary stderr, exit-code passthrough).
- **Resolution:** *(when resolved)*

### OQ-7.3-3: Default TUI flag rejection tests
- **Tags:** `proj-spec/chapters/07.3-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Help snapshots and `thread.test.ts` cover `--help` text, `--replay-limit requires --mini`, `--port cannot be used with --mini`, and `--no-replay` parse forms. No tests found that assert `--replay is not supported; replay is enabled by default` or the non-`--mini` message `--fork requires --continue or --session`.
- **Resolution:** *(when resolved)*

### OQ-7.3-4: Network resolution vs config tests
- **Tags:** `proj-spec/chapters/07.3-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `serve-process.test.ts` exercises `serve`; no tests found in allowed globs for `resolveNetworkOptionsNoConfig` (CLI vs `config.server`, mDNS hostname `0.0.0.0`, CORS concat).
- **Resolution:** *(when resolved)*

### OQ-7.3-5: `lildax` command coverage beyond `api`
- **Tags:** `proj-spec/chapters/07.3-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed `packages/cli` tests cover only `resolveOperation` / `rawRequest`. No tests found for `serve`, `service *`, default TUI, `migrate`, or daemon start/stop strings.
- **Resolution:** *(when resolved)*

### OQ-7.3-6: Parser-fail and `lildax` daemon errors
- **Tags:** `proj-spec/chapters/07.3-cli.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `FormatError` is tested; no tests found for yargs `.fail` (throw-when-`err` vs `showHelp` then `process.exit(1)`), wrapper missing-package stderr, or daemon messages `Registered server is not healthy` / `Failed to start server`.
- **Resolution:** *(when resolved)*

### OQ-7.4-1: In-package tests for plugin export surface
- **Tags:** `proj-spec/chapters/07.4-plugin-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed path `packages/plugin/**/*.{test,spec}.*` contains no files. Named tests for this export surface, if any, live outside this slice.
- **Resolution:** *(when resolved)*

### OQ-7.4-2: Host implementation of plugin hooks
- **Tags:** `proj-spec/chapters/07.4-plugin-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Call order, defaults, and HTTP/status behavior of hosts that consume these types are not in `packages/plugin/` (except v2 README text cited above). Canonical host behavior belongs in [6.12 Plugin](06.12-plugin.md) or other slices.
- **Resolution:** *(when resolved)*

### OQ-8-1: SDK Next event publication
- **Tags:** `proj-spec/chapters/08-domain-model.md`, `proj-spec/chapters/07.1-http-api.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Which Schema event types SDK Next exposes beyond the Protocol HTTP unions in [7.1 HTTP API](chapters/07.1-http-api.md) (`EventManifest.ServerDefinitions` plus HTTP-synthetic `server.connected` on `/api/event`; `SessionEvent.Durable` on `/api/session/:sessionID/event`). Protocol `/api/...` event publication is specified in 7.1, not unknown.
- **Resolution:** *(when resolved)*

### OQ-8-2: Duplicate event definition throws
- **Tags:** `proj-spec/chapters/08-domain-model.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test in `packages/schema/test/` asserts `Duplicate latest event definition` or `Duplicate durable event definition`.
- **Resolution:** *(when resolved)*

### OQ-9-001: Construction coverage
- **Tags:** `proj-spec/chapters/09-design-decisions.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no tests that assert default branch `dev` or local `main` absence.
- **Resolution:** *(when resolved)*

### OQ-9-002: Behavior coverage
- **Tags:** `proj-spec/chapters/09-design-decisions.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no tests that assert dependency direction, generate commands, do-not-edit generated dirs, or default branch `dev`.
- **Resolution:** *(when resolved)*

### OQ-9-003: Error-handling coverage
- **Tags:** `proj-spec/chapters/09-design-decisions.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no tests for enforcement or diagnostics when these workspace rules are broken. Untestable from this slice’s sources unless enforcement lives outside allowed-paths.
- **Resolution:** *(when resolved)*

### OQ-10.1-1: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole; named tests attach to nested headings.
- **Resolution:** *(when resolved)*

### OQ-10.1-2: Workspace script tests
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for root `postinstall` / `prepare`, or desktop `predev`/`prebuild` including `bun run install-electron`. `install-electron` is not a script in `packages/desktop/package.json` or root `package.json`.
- **Resolution:** *(when resolved)*

### OQ-10.1-3: `opencode` wrapper and postinstall tests
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/opencode/bin/opencode` or `packages/opencode/script/postinstall.mjs`.
- **Resolution:** *(when resolved)*

### OQ-10.1-4: `lildax` wrapper tests
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `packages/cli/bin/lildax.cjs`.
- **Resolution:** *(when resolved)*

### OQ-10.1-5: `InstallationChannel` / `InstallationVersion` literals
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Exact `InstallationChannel` / `InstallationVersion` / `Script.channel` strings live in `@opencode-ai/core/installation/version` and `@opencode-ai/script`, outside this slice’s allowed paths. Tests use `InstallationChannel` in the npm registry URL without asserting its value.
- **Resolution:** *(when resolved)*

### OQ-10.1-6: `Installation.method` tests
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found for `Installation.method` path heuristics (`.opencode/bin`, `.local/bin`) or global-list detection of `opencode` vs `opencode-ai`.
- **Resolution:** *(when resolved)*

### OQ-10.1-7: Uninstall handler tests
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Help snapshot covers flags only. No tests found for directory deletion, shell-rc filtering, or package-manager uninstall commands. `Global.Path.*` directory locations are defined in `@opencode-ai/core/global` (outside allowed paths).
- **Resolution:** *(when resolved)*

### OQ-10.1-8: Desktop packaging protocol tests
- **Tags:** `proj-spec/chapters/10.1-install.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Builder Linux identities and extraResources CLI are covered by `electron-builder.config.test.ts`. No tests found in this slice for `protocols.schemes` `opencode` or `artifactName` `opencode-desktop-${os}-${arch}.${ext}`. Runtime lock/protocol/sidecar tests belong to `proj-spec/chapters/06.19-desktop.md`.
- **Resolution:** *(when resolved)*

### OQ-10.1-9: `UpgradeCommand` handler tests
- **Tags:** `proj-spec/chapters/10.1-install.md#opencode-upgrade`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Help snapshot covers `upgrade [target]`, `--method`/`-m` choices (`curl`/`npm`/`pnpm`/`bun`/`brew`/`choco`/`scoop`, no `yarn`). No tests found for leading-`v` strip, unknown-method `Install anyways?` (`initialValue: false`), skip-when-same-version warn `opencode upgrade skipped: ${target} is already installed`, or choco UI `Please run the terminal as Administrator and try again`.
- **Resolution:** *(when resolved)*

### OQ-10.2-1: Workspace orchestrator for generate scripts
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Whether a repo-root or Turbo pipeline runs these generate scripts is outside this slice’s allowed paths.
- **Resolution:** *(when resolved)*

### OQ-10.2-2: `bun dev generate` OpenAPI document
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/sdk/js/script/build.ts` invokes `bun dev generate` with cwd `packages/opencode`, which is outside this slice’s allowed paths; the emitted OpenAPI document is not specified here.
- **Resolution:** *(when resolved)*

### OQ-10.2-3: Construction and command-table tests
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert package.json generate script strings, `AGENTS.md` generate instructions, or drizzle-kit `out` against this chapter’s command table.
- **Resolution:** *(when resolved)*

### OQ-10.2-4: Client generate script write coverage
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test found that runs `packages/client/script/build.ts` or `check:generated`. `"client and Server contracts generate identically"` asserts `emitPromise` equality, not the write of `src/generated` / `src/generated-effect`.
- **Resolution:** *(when resolved)*

### OQ-10.2-5: SDK generate patches beyond history query types
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `packages/sdk/js/test/session-history.test.ts` `"uses numeric Session history positions"` types `V2SessionHistoryData` query `after`/`limit` as numbers. No tests found for SessionNext pruning, the three throw messages, the SseFn patch, Prettier, `tsc`, or deletion of `openapi.json`.
- **Resolution:** *(when resolved)*

### OQ-10.2-6: UI generate tests
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found under `packages/ui/**/*.{test,spec}.*` for `generate:tailwind` or `generate:v2-oc2`.
- **Resolution:** *(when resolved)*

### OQ-10.2-7: Stats `db:generate` tests
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found under `packages/stats/core/**/*.{test,spec}.*` for `db:generate` / `drizzle-kit generate`.
- **Resolution:** *(when resolved)*

### OQ-10.2-8: SDK and UI generate error tests
- **Tags:** `proj-spec/chapters/10.2-generate.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that assert SDK `script/build.ts` throw strings, UI `Missing ${mode} OC-2 tokens`, or `check:generated` `git diff --exit-code` behavior.
- **Resolution:** *(when resolved)*

### OQ-11.1-1: Construction test coverage
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#construction--configuration`, `proj-spec/chapters/11.1-surfaces.md#example-start-hosts`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests in allowed globs assert package `bin` / `scripts.dev` / Vite-Astro start commands as a surface-entrypoint matrix.
- **Resolution:** *(when resolved)*

### OQ-11.1-2: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#behavior`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test names the parent `## Behavior` heading as a whole.
- **Resolution:** *(when resolved)*

### OQ-11.1-3: Start-script coverage deferred to 6.x
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#example-start-hosts`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** After extra-review, 11.1 only names start commands and points at canonical leaves. Desktop `electron-vite`/`predev`/sidecar and app Vite/`PLAYWRIGHT_*` contracts are owned by 6.19 and 6.18, not by this example-host leaf. This id is not a 11.1 Verification target.
- **Resolution:** *(when resolved)*

### OQ-11.1-4: In-repo SDK example tests
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#in-repo-example-file`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found that execute `packages/sdk/js/example/example.ts` as an example host.
- **Resolution:** *(when resolved)*

### OQ-11.1-5: Hosted-site start coverage deferred to 6.x
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#example-start-hosts`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Astro `astro dev`, console/enterprise/stats `vite dev` ports, and `SST_STAGE` / Astro `site` URL selection are owned by 6.27, 6.21, 6.20, and 6.23. 11.1 only points at those start scripts. This id is not a 11.1 Verification target.
- **Resolution:** *(when resolved)*

### OQ-11.1-6: Slack bot coverage deferred to 6.x
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#example-start-hosts`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Bolt startup, session create/prompt, and `/test` are owned by 6.26. 11.1 only names `bun run src/index.ts` as the example start. This id is not a 11.1 Verification target.
- **Resolution:** *(when resolved)*

### OQ-11.1-7: Primary CLI serve/web/TUI coverage deferred to 6.x
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#example-start-hosts`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** `bin/opencode`, default TUI, `serve` listen, and `web` open behavior are owned by 6.1 (alternate `lildax api` by 6.15). 11.1 only names those bins/scripts. This id is not a 11.1 Verification target.
- **Resolution:** *(when resolved)*

### OQ-11.1-8: Example-leaf error coverage
- **Tags:** `proj-spec/chapters/11.1-surfaces.md#error-handling`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** This chapter only points at 6.x error tables. No tests encode an 11.1-owned error string because this leaf no longer owns those strings.
- **Resolution:** *(when resolved)*

### OQ-12.1-1: Root test command coverage
- **Tags:** `proj-spec/chapters/12.1-workspace.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test under `packages/**/*.{test,spec}.*` asserts root `scripts.test` prints `do not run tests from root` or exits `1`.
- **Resolution:** *(when resolved)*

### OQ-12.1-2: Package test-script coverage
- **Tags:** `proj-spec/chapters/12.1-workspace.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts the shipped `scripts.test` / `test:*` command strings, bun flags, `./src` / `./test-browser` path arguments, or playwright configs.
- **Resolution:** *(when resolved)*

### OQ-12.1-3: Location inventory coverage
- **Tags:** `proj-spec/chapters/12.1-workspace.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No workspace-level test asserts which packages contain `*.test.*` / `*.spec.*` files or that packages listed without tests remain empty of those globs.
- **Resolution:** *(when resolved)*

### OQ-12.1-4: App chain-fail coverage
- **Tags:** `proj-spec/chapters/12.1-workspace.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No test asserts that `packages/app` `scripts.test` (or `test:stability`) stops on the first failing `&&` operand.
- **Resolution:** *(when resolved)*

### OQ-13-1: Product-code performance tests or budgets
- **Tags:** `proj-spec/chapters/13-performance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Do first-party packages contain performance tests, benchmarks, or numeric budgets that T0/T1 did not name?
- **Resolution:** *(when resolved)*

### OQ-13-2: Runtime performance configuration
- **Tags:** `proj-spec/chapters/13-performance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Are there runtime env vars or config keys for performance that T0 did not inventory?
- **Resolution:** *(when resolved)*

### OQ-13-3: Performance-related error and timeout behavior
- **Tags:** `proj-spec/chapters/13-performance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Do shipped surfaces emit performance-specific errors or timeouts not named in T0/T1?
- **Resolution:** *(when resolved)*

### OQ-14-1: Construction test coverage
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths (`README.md`, root `package.json`, T0, T1) contain no test module that asserts root `name`/`description`, `scripts.test`, or T1 non-goal assignment.
- **Resolution:** *(when resolved)*

### OQ-14-2: Parent behavior heading coverage
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that encode slice-14 acceptance as a whole.
- **Resolution:** *(when resolved)*

### OQ-14-3: Shipped-surface inventory tests
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that assert the T0 §3 / T1 §4 surface list or that Storybook is excluded.
- **Resolution:** *(when resolved)*

### OQ-14-4: README claim tests
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths for README install commands, desktop artifact filenames, or the `build` / `plan` / `general` agent names.
- **Resolution:** *(when resolved)*

### OQ-14-5: Non-goal exclusion tests
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that treat Storybook as out of shipped-product acceptance.
- **Resolution:** *(when resolved)*

### OQ-14-6: Root test-script error tests
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that assert root `scripts.test` prints `do not run tests from root` and exits `1`.
- **Resolution:** *(when resolved)*

### OQ-14-7: Product string contradiction
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** README tagline `The open source AI coding agent.` vs root `package.json` `description` `AI-powered development tool` (T0 contradictions; T1 §7 `product`). Which string, if either, is canonical for product identity is not decided in allowed paths.
- **Resolution:** *(when resolved)*

### OQ-14-8: `opencode` vs `lildax`
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** T0 flags two CLI binaries `opencode` and `lildax`; relationship is not stated in allowed paths (T1 OQ-T1-3). Acceptance treats both as shipped surfaces without a stated substitution or wrapper rule.
- **Resolution:** *(when resolved)*

### OQ-14-9: In-repo product documentation location
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter Verification / Open questions (retrospective)
- **Blocking:** none
- **Status:** open
- **Question:** T0 §6/§9: root `docs/**` absent; README links `https://opencode.ai/docs` only. Whether additional in-repo docs are required for product acceptance is unsourced.
- **Resolution:** *(when resolved)*

### OQ-T1-2: `packages/core` `bin.opencode` on disk
- **Tags:** `proj-spec/chapters/05-file-tree.md`, `proj-spec/chapters/06.2-core.md`
- **Discovered in:** leaf chapter (cites T1 map §9)
- **Blocking:** none
- **Status:** open
- **Question:** Is `packages/core` `bin.opencode` a second CLI surface? T0: bin in manifest, no `packages/core/bin/` on disk.
- **Resolution:** *(when resolved)*

### OQ-T1-3: How `opencode` and `lildax` relate
- **Tags:** `proj-spec/chapters/14-acceptance.md`
- **Discovered in:** leaf chapter (cites T1 map §9)
- **Blocking:** none
- **Status:** open
- **Question:** How `opencode` and `lildax` relate? T0 flags two binaries; no relationship in allowed paths.
- **Resolution:** *(when resolved)*

### OQ-T1-4: Does desktop wrap `app`?
- **Tags:** `proj-spec/chapters/06.18-app.md`
- **Discovered in:** leaf chapter (cites T1 map §9)
- **Blocking:** none
- **Status:** open
- **Question:** Who mounts `AppInterface` with `platform: "desktop"`, sidecar/SSH servers, health checks enabled, and `window.api`? Not in `packages/app` allowed paths. T0: `app` is desktop `devDependency` only; runtime wrap unsourced.
- **Resolution:** *(when resolved)*

### OQ-T1-5: `@opencode-ai/function` vs stats
- **Tags:** `proj-spec/chapters/05-file-tree.md`
- **Discovered in:** leaf chapter (cites T1 map §9)
- **Blocking:** none
- **Status:** open
- **Question:** Should `@opencode-ai/function` live with stats? T0 contradiction: `packages/stats/README.md` vs workspace `stats-server`; assigned 6.25 per T0 cluster 12.
- **Resolution:** *(when resolved)*
