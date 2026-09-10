# 2 Goals

> **Spec chapter:** Shipped product goals and explicit non-goals for OpenCode.
> **Parent:** [README](../README.md)
> **Index:** [README.md](../README.md)

**File:** `README.md`, `package.json` (documentary sources; this slice has no implementation module)

This pass is retrospective of shipped documentation and the chapter map. It does not redesign product scope. Component, install, and interface contracts live in other chapters; this file records **goals and non-goals** only.

## Construction / configuration

Product identity strings used by this slice (consistency token `product`):

| Parameter | Value | Source |
|----------|-------|--------|
| Product name | OpenCode | `README.md` (logo `alt` `OpenCode logo`; T1 §7 token `product`) |
| README tagline | `The open source AI coding agent.` | `README.md` (centered subtitle under the logo) |
| Workspace `name` | `opencode` | `package.json` `name` |
| Workspace `description` | `AI-powered development tool` | `package.json` `description` |
| Storybook workspace script | `bun --cwd packages/storybook storybook` | `package.json` `scripts.dev:storybook` |

T1 §7 records a contradiction on token `product`: README tagline `The open source AI coding agent.` versus root `package.json` `description` `AI-powered development tool`. This chapter quotes both; it does not pick a winner (OQ-02-1).

## Behavior

### Product identity

The shipped product name in this slice is **OpenCode** (`README.md`; T1 §7). The root workspace package is named `opencode` (`package.json` `name`). The README npm badge uses package `opencode-ai` (`README.md` badge `https://www.npmjs.com/package/opencode-ai`).

The README tagline is `The open source AI coding agent.` (`README.md`). The root manifest description is `AI-powered development tool` (`package.json` `description`). Those two strings are both present in the allowed sources; which string is canonical for product copy is unresolved (OQ-02-1).

### Documented product capabilities

Root `README.md` presents OpenCode as an AI coding agent with these documented capabilities (install mechanics and agent contracts are not specified here):

| README heading / location | Documented capability |
|---------------------------|------------------------|
| Tagline | Positions the product as `The open source AI coding agent.` |
| Installation | Documents install via `curl -fsSL https://opencode.ai/install \| bash` and named package managers (`npm i -g opencode-ai@latest`, Scoop, Chocolatey, Homebrew, pacman, AUR, mise, Nix) |
| Desktop App (BETA) | States OpenCode is available as a desktop application (downloads named in that section) |
| Agents | Lists built-in agents `build` (default, full-access) and `plan` (read-only), plus a `general` subagent invoked with `@general` |
| Documentation | Points to `https://opencode.ai/docs` for configuration |
| Building on OpenCode | Asks projects that use `opencode` in their name (examples `opencode-dashboard`, `opencode-mobile`) to note they are not built by the OpenCode team and are not affiliated |

Those rows are README statements of product intent. They are not the behavioral home for CLI flags, desktop packaging, or HTTP APIs.

### Non-goals

T1 §3 maps one **workspace package** to a non-goal (`@opencode-ai/storybook` → `non-goal:2`). Extra-workspace first-party trees below are not T1 leaves; this spec does not invent product APIs for them. They are explicit non-goals for this map (C3). Where an existing leaf might still be the right home, that mapping is an open question (OQ-02-3 through OQ-02-7). OQ-5-2 does not name these paths.

| Assigned | Why (map) | Allowed-path evidence |
|----------|-----------|----------------------|
| `@opencode-ai/storybook` → `non-goal:2` | T1 §3: T0 surface “Storybook (dev)” / purpose “Storybook dev harness” — not a shipped product surface. T1 §4: surface `Storybook (dev)` primary leaf `non-goal:2`. | Root `package.json` `scripts.dev:storybook` is `bun --cwd packages/storybook storybook`. T1 §2 assigns package `@opencode-ai/storybook` path `packages/storybook` to `non-goal:2`. |
| `sdks/vscode`, `.vscode/` | Extra-workspace. T1 has no vscode surface. Not leaves 6.8 or 6.9 (`packages/sdk/js`, `packages/sdk-next`). Not a T1 shipped product leaf. | `tmp/executive/opencode-retrospective-spec/findings/RSC-orphan.md` Blockers (`sdks/vscode` + `.vscode/`). |
| `nix/`, `flake.nix`, `flake.lock` | Extra-workspace Nix files. Leaf 10.1 does not own these paths. README Installation *mentions* Nix; that is not a home for `nix/`. | RSC-orphan Blockers (`nix/`, `flake.nix`, `flake.lock`). This chapter’s Installation row cites README package-manager names only. |
| `sdks/` | Extra-workspace SDK tree (not a workspace glob). Workspace SDK homes stay 6.8 and 6.9. | RSC-orphan Blockers (`sdks/`). |
| Root `README.*.md`, `screenshot-uk.png` | Localized README files and screenshot at repo root. Leaf 6.27 is `packages/web/` only. English `README.md` stays leaves 1/2. | RSC-orphan Blockers (root `README.*.md`, `screenshot-uk.png`). |
| `infra/`, `sst.config.ts`, `sst-env.d.ts`, root `github/` | Extra-workspace cloud/SST root files and root `github/` tree. Leaves 6.21–6.25 are `packages/*` only. | RSC-orphan Blockers (`infra/`, `sst.config.ts`, `sst-env.d.ts`, `github/`). |

Storybook is a workspace script and mapped package. It is **not** a shipped product surface in this map.

## Error handling

Root `README.md` and `package.json` do not define runtime errors, HTTP statuses, or process exit codes for product goals or non-goals. Affiliation wording under README `Building on OpenCode` is a request to third-party README authors, not an OpenCode runtime error.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement and `#spec-coverage-audit`). One tag per line. Allowed source paths for this slice contain no test files.

- Spec-Anchor: proj-spec/chapters/02-goals.md#construction--configuration — tests: none found
- Spec-Anchor: proj-spec/chapters/02-goals.md#behavior — tests: none found
- Spec-Anchor: proj-spec/chapters/02-goals.md#product-identity — tests: none found
- Spec-Anchor: proj-spec/chapters/02-goals.md#documented-product-capabilities — tests: none found
- Spec-Anchor: proj-spec/chapters/02-goals.md#non-goals — tests: none found
- Spec-Anchor: proj-spec/chapters/02-goals.md#error-handling — tests: none found

Documentary product copy in `README.md` / `package.json` is not shown as covered by automated tests in this slice’s allowed paths. That gap is untestable from those paths (OQ-02-2). Extra-workspace non-goals above have no tests in this slice (same gap).

### OQ-02-1: Product identity string contradiction

- **Tags:** `proj-spec/chapters/02-goals.md#construction--configuration`, `proj-spec/chapters/02-goals.md#product-identity`
- **Discovered in:** retrospective spec slice 2
- **Blocking:** none
- **Status:** open
- **Question:** T1 §7 token `product` lists OpenCode with README tagline `The open source AI coding agent.` versus root `package.json` `description` `AI-powered development tool`. Which string is canonical for product positioning?

### OQ-02-2: Goals test coverage

- **Tags:** `proj-spec/chapters/02-goals.md#construction--configuration`, `proj-spec/chapters/02-goals.md#behavior`, `proj-spec/chapters/02-goals.md#product-identity`, `proj-spec/chapters/02-goals.md#documented-product-capabilities`, `proj-spec/chapters/02-goals.md#non-goals`, `proj-spec/chapters/02-goals.md#error-handling`
- **Discovered in:** retrospective spec slice 2
- **Blocking:** none
- **Status:** open
- **Question:** Slice allowed-paths (`README.md`, `package.json`, T1 chapter map) include no tests. No named test encodes goals or `non-goal:2` Storybook exclusion.

### OQ-02-3: Home for `sdks/vscode` and `.vscode/`

- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** T1 and leaves 6.8/6.9 do not assign `sdks/vscode` or `.vscode/`. Which existing leaf (if any) should own those paths is unknown. This map records them as non-goals. OQ-5-2 does not name them.

### OQ-02-4: Home for `nix/`, `flake.nix`, `flake.lock`

- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** Leaf 10.1 does not own `nix/`, `flake.nix`, or `flake.lock`. Whether those paths belong under 10.1 or stay non-goals is unknown. This map records them as non-goals. OQ-5-2 does not name them.

### OQ-02-5: Home for `sdks/`

- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** Non-workspace tree `sdks/` is not 6.8 or 6.9. Which existing leaf (if any) should own `sdks/` is unknown. This map records `sdks/` as a non-goal. OQ-5-2 does not name it.

### OQ-02-6: Home for root `README.*.md` and `screenshot-uk.png`

- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** Root `README.*.md` and `screenshot-uk.png` are not leaf 6.27 (`packages/web/`). English `README.md` is leaves 1/2. Which existing leaf (if any) should own the localized files and `screenshot-uk.png` is unknown. This map records them as non-goals. OQ-5-2 does not name them.

### OQ-02-7: Home for `infra/`, `sst.config.ts`, `sst-env.d.ts`, root `github/`

- **Tags:** `proj-spec/chapters/02-goals.md#non-goals`
- **Discovered in:** RSC-orphan (checker 8e2c65e0)
- **Blocking:** none
- **Status:** open
- **Question:** `infra/`, `sst.config.ts`, `sst-env.d.ts`, and root `github/` are not leaves 6.21–6.25 (`packages/*`). Which existing leaf (if any) should own those paths is unknown. This map records them as non-goals. OQ-5-2 does not name them.

## Related chapters

- [README](../README.md)
