# 1 Overview

> **Spec chapter:** Product one-liner and shipped surfaces for OpenCode.
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**Files:** `README.md`, `package.json` (repository root)

This chapter is a retrospective of **shipped** product copy and surface inventory. It does not redesign the product. Package internals, HTTP contracts, CLI flags, and installer implementation are out of this slice (C2).

## Construction / configuration

| Parameter | Default / value | Notes |
|-----------|-----------------|-------|
| Workspace `name` | `opencode` | Root `package.json` `name` |
| Workspace `description` | `AI-powered development tool` | Root `package.json` `description` |
| README tagline | `The open source AI coding agent.` | Root `README.md` (centered paragraph under the logo) |
| `private` | `true` | Root `package.json` |
| `type` | `module` | Root `package.json` |
| `packageManager` | `bun@1.3.14` | Root `package.json` |
| `license` | `MIT` | Root `package.json` |
| `repository.url` | `https://github.com/anomalyco/opencode` | Root `package.json` `repository` |
| npm badge package | `opencode-ai` | Root `README.md` npm badge URL `https://www.npmjs.com/package/opencode-ai` |
| Product site | `https://opencode.ai` | Root `README.md` logo link and docs link |
| Docs URL | `https://opencode.ai/docs` | Root `README.md` heading `Documentation` |
| Download URL (desktop) | `https://opencode.ai/download` | Root `README.md` heading `Desktop App (BETA)` |
| Releases | `https://github.com/anomalyco/opencode/releases` | Root `README.md` heading `Desktop App (BETA)` |

The workspace `product` consistency token is **OpenCode**. Committed sources disagree on the one-liner: README tagline `The open source AI coding agent.` versus root `package.json` `description` `AI-powered development tool` (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §7 token `product`). Both strings are shipped; neither is treated as a rewrite of the other.

Root `package.json` `workspaces.packages` lists `packages/*`, `packages/console/*`, `packages/stats/*`, `packages/sdk/js`, and `packages/slack`. That layout is inventory, not this chapter’s file tree.

## Behavior

### Product identity

The committed root README presents OpenCode as **the open source AI coding agent** (`README.md` tagline). The workspace manifest describes the same repository as an **AI-powered development tool** (`package.json` `description`). The README also shows a terminal UI screenshot (`packages/web/src/assets/lander/screenshot.png`, alt `OpenCode Terminal UI`) linking to `https://opencode.ai`.

README localized copies (`README.zh.md` and siblings linked from the language bar) exist as links from `README.md`. This chapter does not specify their wording (those files are outside this slice’s allowed paths).

### Shipped surfaces

T1 maps first-party **product** surfaces to later leaves. This overview names the inventory only; behavior of each surface is not specified here.

| T0 surface | Primary leaf (T1) | User-facing mention in allowed sources |
|------------|-------------------|----------------------------------------|
| CLI (primary) | 6.1 | Root `package.json` script `dev` → `bun run --cwd packages/opencode src/index.ts`; README install commands use binary name `opencode` |
| CLI (alternate) | 6.15 | Not named in root `README.md`. T1 filename `06.15-cli.md`; binary `lildax` is a C9 token, not claimed by README |
| TUI | 6.14 | README screenshot caption `OpenCode Terminal UI` |
| Desktop | 6.19 | README `Desktop App (BETA)`; `package.json` script `dev:desktop` → `bun --cwd packages/desktop dev` |
| Web app UI | 6.18 | `package.json` script `dev:web` → `bun --cwd packages/app dev` |
| Server / HTTP | 6.5 | Not described in root `README.md` |
| SDK (legacy HTTP) | 6.8 | Not described in root `README.md` |
| SDK (in-process) | 6.9 | Not described in root `README.md` |
| Generated clients | 6.7 | Not described in root `README.md` |
| Plugins | 6.12 | Not described in root `README.md` |
| Product docs site | 6.27 | README `Documentation` → `https://opencode.ai/docs`; screenshot asset under `packages/web/` |
| Cloud console | 6.21 | `package.json` script `dev:console` → `ulimit -n 10240 2>/dev/null; bun run --cwd packages/console/app dev` |
| Enterprise app | 6.20 | Not described in root `README.md` |
| Stats site | 6.23 | `package.json` script `dev:stats` → `bun run --cwd packages/stats/app dev` (via `bun sst shell --stage=production`) |
| Slack integration | 6.26 | Workspace path `packages/slack` in root `package.json` `workspaces.packages`; not described in root `README.md` |
| Storybook (dev) | `non-goal:2` | `package.json` script `dev:storybook` → `bun --cwd packages/storybook storybook`. T1 §3: not a shipped product surface |

Source for the surface→leaf column: `tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §4. Source for README/script cells: `README.md`, `package.json` `scripts`.

README documents **installation** (curl installer, npm/`opencode-ai@latest`, scoop, choco, brew, pacman, AUR, mise, nix) and an install-directory priority (`$OPENCODE_INSTALL_DIR`, `$XDG_BIN_DIR`, `$HOME/bin`, `$HOME/.opencode/bin`). Those commands and env names are committed README text. This slice does not specify installer runtime.

README documents **desktop** artifact names:

| Platform | Download name (`README.md` table) |
|----------|-----------------------------------|
| macOS (Apple Silicon) | `opencode-desktop-mac-arm64.dmg` |
| macOS (Intel) | `opencode-desktop-mac-x64.dmg` |
| Windows | `opencode-desktop-windows-x64.exe` |
| Linux | `.deb`, `.rpm`, or `.AppImage` |

Desktop package-manager commands in README: `brew install --cask opencode-desktop`; `scoop bucket add extras; scoop install extras/opencode-desktop`.

### Documented agents

Under README heading `Agents` (`README.md`):

| Agent | README statement |
|-------|------------------|
| `build` | Default, full-access agent for development work |
| `plan` | Read-only agent for analysis and code exploration; denies file edits by default; asks permission before running bash commands |
| `general` | Subagent for complex searches and multistep tasks; used internally; can be invoked using `@general` in messages |

Switching between the two built-in agents uses the `Tab` key (`README.md` `Agents`). This chapter does not specify agent implementation.

### Building on OpenCode (naming)

If a related project uses `opencode` as part of its name, README asks that project’s README to clarify it is not built by the OpenCode team and is not affiliated (`README.md` heading `Building on OpenCode`).

## Error handling

Root `package.json` `scripts.test` / do-not-run-tests-from-root is canonical in [12.1 Workspace — Root test command](12.1-workspace.md#root-test-command). This chapter does not specify that command.

README does not define product error codes, HTTP statuses, or CLI exit codes.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement). Allowed sources for this slice do not name tests that encode these headings.

- Spec-Anchor: proj-spec/chapters/01-overview.md#construction--configuration — tests: none found
- Spec-Anchor: proj-spec/chapters/01-overview.md#behavior — tests: none found
- Spec-Anchor: proj-spec/chapters/01-overview.md#product-identity — tests: none found
- Spec-Anchor: proj-spec/chapters/01-overview.md#shipped-surfaces — tests: none found
- Spec-Anchor: proj-spec/chapters/01-overview.md#documented-agents — tests: none found
- Spec-Anchor: proj-spec/chapters/01-overview.md#building-on-opencode-naming — tests: none found
- Spec-Anchor: proj-spec/chapters/01-overview.md#error-handling — tests: none found

## Related chapters

- [README](../README.md)
- [12.1 Workspace](12.1-workspace.md) — canonical for root `scripts.test`

## Open questions

### OQ-1-1: Product one-liner mismatch
- **Tags:** `proj-spec/chapters/01-overview.md#product-identity`, `proj-spec/chapters/01-overview.md#construction--configuration`
- **Discovered in:** retrospective chapter write (slice 1)
- **Blocking:** none
- **Status:** open
- **Question:** Which string is canonical for product identity — README tagline `The open source AI coding agent.` or root `package.json` `description` `AI-powered development tool`? T1 §7 records this as a `product` token contradiction.

### OQ-1-2: No tests for overview copy and surface inventory
- **Tags:** `proj-spec/chapters/01-overview.md#construction--configuration`, `proj-spec/chapters/01-overview.md#behavior`, `proj-spec/chapters/01-overview.md#product-identity`, `proj-spec/chapters/01-overview.md#shipped-surfaces`, `proj-spec/chapters/01-overview.md#documented-agents`, `proj-spec/chapters/01-overview.md#building-on-opencode-naming`, `proj-spec/chapters/01-overview.md#error-handling`
- **Discovered in:** retrospective chapter write (slice 1)
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths (`README.md`, `package.json`, T1 chapter map) name no test module that asserts README tagline, workspace description, surface inventory, documented agents, or root `scripts.test` exit `1`.
