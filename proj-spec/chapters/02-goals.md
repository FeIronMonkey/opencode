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

| Assigned | Why (map) | Allowed-path evidence |
|----------|-----------|----------------------|
| `@opencode-ai/storybook` → `non-goal:2` | T1 §3: T0 surface “Storybook (dev)” / purpose “Storybook dev harness” — not a shipped product surface. T1 §4: surface `Storybook (dev)` primary leaf `non-goal:2`. | Root `package.json` `scripts.dev:storybook` is `bun --cwd packages/storybook storybook`. T1 §2 assigns package `@opencode-ai/storybook` path `packages/storybook` to `non-goal:2`. |

Storybook is a workspace script and mapped package. It is **not** a shipped product surface in this map.

T1 §3 contains only that one `non-goal:` row. This chapter does not invent further non-goals.

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

Documentary product copy in `README.md` / `package.json` is not shown as covered by automated tests in this slice’s allowed paths. That gap is untestable from those paths (OQ-02-2).

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

## Related chapters

- [README](../README.md)
