# 14 Acceptance

> **Spec chapter:** Retrospective done-ness: shipped product surfaces versus T1 non-goals, plus README-published product claims.
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**Files:** none (validation slice; T1 §2 assigns no package to id `14`)

This chapter records **retrospective acceptance** of the shipped product as the T0 surface inventory, filtered by T1 non-goals. It does not invent end-to-end pass/fail harnesses, reconstructed review approvals, or a requirement to refactor code to match this spec. Example entrypoints for surfaces are out of this slice (see [11.1 Surfaces](11.1-surfaces.md)). This pass is retrospective of shipped artifacts listed in allowed sources.

Product naming is inconsistent across sources (T0 contradictions; T1 §7 token `product`): root `README.md` tagline is `The open source AI coding agent.`; root `package.json` `description` is `AI-powered development tool`. This chapter quotes both; it does not choose a single canonical marketing string.

Published CLI bins in this workspace (T1 §7 token `bins`; T0 §3) are `opencode` and `lildax`. How those binaries relate is not stated in allowed paths (T1 OQ-T1-3).

## Construction / configuration

| Parameter | Value | Notes |
|-----------|-------|-------|
| Root package `name` | `opencode` | `package.json` |
| Root package `description` | `AI-powered development tool` | `package.json`; conflicts with README tagline (T0 contradictions) |
| Root `private` | `true` | `package.json` |
| Root `scripts.test` | `echo 'do not run tests from root' && exit 1` | `package.json`; always fails |
| README tagline | `The open source AI coding agent.` | `README.md` (centered paragraph under the logo) |
| npm badge package | `opencode-ai` | `README.md` shield `https://www.npmjs.com/package/opencode-ai` |
| T1 leaf `14` | `14-acceptance.md` | T1 §1: “Retrospective acceptance vs shipped surfaces” |
| Storybook | T1 `non-goal:2` | T1 §3: T0 surface “Storybook (dev)” / purpose “Storybook dev harness” — not a shipped product surface |

## Behavior

### Shipped surfaces

A T0 surface counts toward shipped-product acceptance when T1 §4 maps it to a primary leaf that is **not** `non-goal:2`. T1 §4 (with T0 §3 package/entrypoint citations) is:

| T0 surface | T1 primary leaf | T0 package | T0 entrypoint citation |
|------------|-----------------|------------|------------------------|
| CLI (primary) | 6.1 | `opencode` | `packages/opencode/package.json` `bin.opencode`; dev entry `scripts.dev` → `./src/index.ts` |
| CLI (alternate) | 6.15 | `@opencode-ai/cli` | `packages/cli/package.json` `bin.lildax` |
| TUI | 6.14 | `@opencode-ai/tui` | `exports["."]` → `./src/index.tsx`; composed by `opencode` dep on `@opencode-ai/tui` |
| Desktop | 6.19 | `@opencode-ai/desktop` | `main` → `./out/main/index.js`; `packages/desktop/README.md` "built with Electron" |
| Web app UI | 6.18 | `@opencode-ai/app` | `exports["."]`; root `scripts.dev:web` → `packages/app` |
| Server / HTTP | 6.5 | `@opencode-ai/server` | `exports["./*"]`; runtime deps: `opencode`, `@opencode-ai/cli`, `@opencode-ai/sdk-next` (`package.json` `dependencies`) |
| SDK (legacy HTTP) | 6.8 | `@opencode-ai/sdk` | `exports["."]`, `./v2/client`, `./v2/gen/client` |
| SDK (in-process) | 6.9 | `@opencode-ai/sdk-next` | `exports["."]` (`packages/sdk-next/README.md`) |
| Generated clients | 6.7 | `@opencode-ai/client` | `exports["."]`, `./effect` |
| Plugins | 6.12 | `@opencode-ai/plugin` | `exports["."]`, `./tool`, `./tui` |
| Product docs site | 6.27 | `@opencode-ai/web` | `packages/web/package.json` `scripts` `astro dev/build`; dep `@astrojs/starlight` |
| Cloud console | 6.21 | `@opencode-ai/console-app` | `packages/console/app/package.json` `scripts.dev` |
| Enterprise app | 6.20 | `@opencode-ai/enterprise` | `packages/enterprise/package.json` `scripts.dev` |
| Stats site | 6.23 | `@opencode-ai/stats-app` | `scripts.dev`; root `scripts.dev:stats` |
| Slack integration | 6.26 | `@opencode-ai/slack` | `scripts.dev` → `src/index.ts` |
| Storybook (dev) | `non-goal:2` | `@opencode-ai/storybook` | `scripts.storybook` |

T0 §3 row “Storybook (dev)” is **excluded** from shipped-product acceptance (T1 §3 / §4). Interface companions in T1 §4 (7.1←6.5, 7.2←6.7/6.8/6.9, 7.3←6.1/6.15, 7.4←6.12) are not extra product surfaces; they are map notes, not a second inventory.

This slice does not restate per-package contracts. Entrypoint examples belong in [11.1 Surfaces](11.1-surfaces.md).

### README-published product claims

Root `README.md` publishes the following user-facing claims. This chapter records them as README text, not as install/agent implementation contracts.

**Installation** (`README.md` heading `### Installation`): documented commands are:

| Channel | Command / note |
|---------|----------------|
| YOLO | `curl -fsSL https://opencode.ai/install \| bash` |
| npm (or bun/pnpm/yarn) | `npm i -g opencode-ai@latest` |
| Scoop | `scoop install opencode` |
| Chocolatey | `choco install opencode` |
| Homebrew tap | `brew install anomalyco/tap/opencode` (comment: macOS and Linux (recommended, always up to date)) |
| Homebrew formula | `brew install opencode` (comment: macOS and Linux (official brew formula, updated less)) |
| Arch stable | `sudo pacman -S opencode` |
| AUR | `paru -S opencode-bin` |
| mise | `mise use -g opencode` |
| Nix | `nix run nixpkgs#opencode` or `github:anomalyco/opencode` for latest dev branch |

README TIP: `Remove versions older than 0.1.x before installing.`

Install-script directory priority (`README.md` `#### Installation Directory`): (1) `$OPENCODE_INSTALL_DIR`, (2) `$XDG_BIN_DIR`, (3) `$HOME/bin` (if it exists or can be created), (4) `$HOME/.opencode/bin` (default fallback). Examples in that section: `OPENCODE_INSTALL_DIR=/usr/local/bin curl -fsSL https://opencode.ai/install | bash` and `XDG_BIN_DIR=$HOME/.local/bin curl -fsSL https://opencode.ai/install | bash`.

**Desktop App (BETA)** (`README.md` heading `### Desktop App (BETA)`): available as a desktop application; download from `https://github.com/anomalyco/opencode/releases` or `https://opencode.ai/download`. Artifact names:

| Platform | Download |
|----------|----------|
| macOS (Apple Silicon) | `opencode-desktop-mac-arm64.dmg` |
| macOS (Intel) | `opencode-desktop-mac-x64.dmg` |
| Windows | `opencode-desktop-windows-x64.exe` |
| Linux | `.deb`, `.rpm`, or `.AppImage` |

Additional desktop install commands in that section: `brew install --cask opencode-desktop`; `scoop bucket add extras; scoop install extras/opencode-desktop`.

**Agents** (`README.md` heading `### Agents`): two built-in agents switched with the `Tab` key — **build** (Default, full-access agent for development work) and **plan** (Read-only agent for analysis and code exploration; denies file edits by default; asks permission before running bash commands). Also a **general** subagent for complex searches and multistep tasks, used internally and invocable with `@general` in messages. README links further agent docs at `https://opencode.ai/docs/agents`.

**Documentation / contributing / naming** (`README.md`): configure via `https://opencode.ai/docs`; contributing via `./CONTRIBUTING.md`; projects using “opencode” in the name that are not built by the OpenCode team should clarify non-affiliation in their README.

Whether in-repo user-facing docs beyond this README exist is not established in allowed paths (T0 §6: repo root `docs/**` none found; T0 §9).

### Excluded from shipped acceptance

| Item | Rule | Source |
|------|------|--------|
| Storybook (dev) | Not a shipped product surface | T1 §3 `storybook` → `non-goal:2`; T1 §4 primary leaf `non-goal:2` |
| Root workspace tests | Root `scripts.test` does not run a suite | `package.json` `scripts.test` |

T0 §1 product one-liner paraphrases both README and `package.json`; this chapter does not treat that paraphrase as a third independent string.

## Error handling

| Condition | Behavior | Source |
|-----------|----------|--------|
| Root `scripts.test` invoked | Prints `do not run tests from root` and exits `1` | `package.json` `scripts.test`: `echo 'do not run tests from root' && exit 1` |

Install-script failure modes, desktop installer errors, and agent permission denials are not specified in allowed paths for this slice.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement and `#spec-coverage-audit`). One tag per line. Allowed paths for this slice do not include test files.

- Spec-Anchor: proj-spec/chapters/14-acceptance.md#construction--configuration — tests: none found (OQ-14-1, Blocking: none)
- Spec-Anchor: proj-spec/chapters/14-acceptance.md#behavior — tests: none found (OQ-14-2, Blocking: none)
- Spec-Anchor: proj-spec/chapters/14-acceptance.md#shipped-surfaces — tests: none found (OQ-14-3, Blocking: none)
- Spec-Anchor: proj-spec/chapters/14-acceptance.md#readme-published-product-claims — tests: none found (OQ-14-4, Blocking: none)
- Spec-Anchor: proj-spec/chapters/14-acceptance.md#excluded-from-shipped-acceptance — tests: none found (OQ-14-5, Blocking: none)
- Spec-Anchor: proj-spec/chapters/14-acceptance.md#error-handling — tests: none found (OQ-14-6, Blocking: none)

### OQ-14-1: Construction test coverage

- **Tags:** `proj-spec/chapters/14-acceptance.md#construction--configuration`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths (`README.md`, root `package.json`, T0, T1) contain no test module that asserts root `name`/`description`, `scripts.test`, or T1 non-goal assignment.

### OQ-14-2: Parent behavior heading coverage

- **Tags:** `proj-spec/chapters/14-acceptance.md#behavior`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that encode slice-14 acceptance as a whole.

### OQ-14-3: Shipped-surface inventory tests

- **Tags:** `proj-spec/chapters/14-acceptance.md#shipped-surfaces`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that assert the T0 §3 / T1 §4 surface list or that Storybook is excluded.

### OQ-14-4: README claim tests

- **Tags:** `proj-spec/chapters/14-acceptance.md#readme-published-product-claims`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths for README install commands, desktop artifact filenames, or the `build` / `plan` / `general` agent names.

### OQ-14-5: Non-goal exclusion tests

- **Tags:** `proj-spec/chapters/14-acceptance.md#excluded-from-shipped-acceptance`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that treat Storybook as out of shipped-product acceptance.

### OQ-14-6: Root test-script error tests

- **Tags:** `proj-spec/chapters/14-acceptance.md#error-handling`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** No tests found in allowed paths that assert root `scripts.test` prints `do not run tests from root` and exits `1`.

### OQ-14-7: Product string contradiction

- **Tags:** `proj-spec/chapters/14-acceptance.md#construction--configuration`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** README tagline `The open source AI coding agent.` vs root `package.json` `description` `AI-powered development tool` (T0 contradictions; T1 §7 `product`). Which string, if either, is canonical for product identity is not decided in allowed paths.

### OQ-14-8: `opencode` vs `lildax`

- **Tags:** `proj-spec/chapters/14-acceptance.md#shipped-surfaces`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** T0 flags two CLI binaries `opencode` and `lildax`; relationship is not stated in allowed paths (T1 OQ-T1-3). Acceptance treats both as shipped surfaces without a stated substitution or wrapper rule.

### OQ-14-9: In-repo product documentation location

- **Tags:** `proj-spec/chapters/14-acceptance.md#readme-published-product-claims`
- **Discovered in:** retrospective spec slice 14
- **Blocking:** none
- **Status:** open
- **Question:** T0 §6/§9: root `docs/**` absent; README links `https://opencode.ai/docs` only. Whether additional in-repo docs are required for product acceptance is unsourced.

## Related chapters

- [README.md](../README.md)
- [11.1 Surfaces](11.1-surfaces.md)
