# 9 Design decisions

> **Spec chapter:** Recorded workspace layering and generate rules (retrospective).
> **Parent:** [README.md](../README.md)
> **Index:** [README.md](../README.md)

**File:** `AGENTS.md`

This chapter is a **retrospective** description of shipped workspace rules (C8). T1 assigns this leaf as “Recorded layering and generate rules” (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §1 id `9`, filename `09-design-decisions.md`). It is not a package home. T1 package assignments and generated-tree ownership stay on other leaves (`T1-chapter-map.md` §2, §5). `generated-in-slice` for this leaf is **no** (task spec).

Canonical home for workspace generate **commands** as an operations catalog is T1 leaf `10.2` (`T1-chapter-map.md` §5 row 10.2). This chapter records the **rules** in `AGENTS.md` and the T1 generate token list. It does not claim any one package invokes every generate command.

## Construction / configuration

| Parameter | Default / shipped value | Notes |
|-----------|-------------------------|-------|
| Default branch | `dev` | `AGENTS.md`: “The default branch in this repo is `dev`.” |
| Local `main` | may not exist | `AGENTS.md`: “Local `main` ref may not exist; use `dev` or `origin/dev` for diffs.” |
| generated-in-slice | no | task spec; T1 §2 does not assign a package to id `9` |

### OQ-9-001: Construction coverage

- **Tags:** `proj-spec/chapters/09-design-decisions.md#construction--configuration`
- **Discovered in:** retrospective spec slice 9
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no tests that assert default branch `dev` or local `main` absence.

## Behavior

### Runtime dependency direction

Canonical runtime layering (manifests + direction) is [3 Architecture — Runtime dependency direction](03-architecture.md#runtime-dependency-direction) (T1 **dep direction** token, `T1-chapter-map.md` §7). This leaf does not restate that MUST.

T1 lists the multi-leaf package names `schema`, `core`, `protocol`, `server`, `client`, `sdk`, `sdk-next`, `plugin`, `ui` (`T1-chapter-map.md` §7). This leaf does not re-home those packages.

### Generate and generated trees

After changing the public Protocol or Server `HttpApi`, contributors MUST run `bun run generate` from `packages/client`. Contributors MUST NOT edit `src/generated` or `src/generated-effect` directly (`AGENTS.md`). Those directories are generated; they are not the behavioral source of truth (C5). T1 maps the generator to `packages/client` `scripts.generate` → `script/build.ts` and the same `AGENTS.md` command (`T1-chapter-map.md` §5 leaf 6.7).

To regenerate the legacy JavaScript SDK, run `./packages/sdk/js/script/build.ts` (`AGENTS.md`). T1 maps that script to generated trees `packages/sdk/js/src/v2/gen/` and `packages/sdk/js/dist/` (build output, not in tree) (`T1-chapter-map.md` §5 leaf 6.8). Those trees are generated or build output; they are not the behavioral source of truth (C5).

T1 **generate** token (workspace list; this slice does not invoke all of them): `bun run generate` (`packages/client`); `./packages/sdk/js/script/build.ts`; `generate:tailwind`; `generate:v2-oc2`; `db:generate` / `drizzle-kit generate` (`T1-chapter-map.md` §7). T1 assigns `generate:tailwind` and `generate:v2-oc2` to leaf 6.16 (`packages/ui`); `db:generate` → `drizzle-kit generate` to leaf 6.24 (`packages/stats/core`); ops catalog to 10.2 (`T1-chapter-map.md` §5).

T1 **generated dirs** token: `src/generated`, `src/generated-effect`, `packages/sdk/js/src/v2/gen/`, `packages/sdk/js/dist/` (`T1-chapter-map.md` §7).

### Default branch for diffs

The default branch in this repo is `dev`. When comparing, use `dev` or `origin/dev` if local `main` is missing (`AGENTS.md`).

### OQ-9-002: Behavior coverage

- **Tags:** `proj-spec/chapters/09-design-decisions.md#behavior`
- **Discovered in:** retrospective spec slice 9
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no tests that assert generate commands, do-not-edit generated dirs, or default branch `dev`.

## Error handling

`AGENTS.md` and `T1-chapter-map.md` name no error strings, HTTP statuses, or exit codes for editing generated trees, skipping generate, or using a non-`dev` branch. Layering-violation diagnostics, if any, are not specified on the canonical leaf ([3 Architecture — Error handling](03-architecture.md#error-handling)).

### OQ-9-003: Error-handling coverage

- **Tags:** `proj-spec/chapters/09-design-decisions.md#error-handling`
- **Discovered in:** retrospective spec slice 9
- **Blocking:** none
- **Status:** open
- **Question:** Allowed paths contain no tests for enforcement or diagnostics when these workspace rules are broken. Untestable from this slice’s sources unless enforcement lives outside allowed-paths.

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement and `#spec-coverage-audit`). One tag per line.

- Spec-Anchor: proj-spec/chapters/09-design-decisions.md#construction--configuration
- tests: none found
- Spec-Anchor: proj-spec/chapters/09-design-decisions.md#behavior
- tests: none found
- Spec-Anchor: proj-spec/chapters/09-design-decisions.md#runtime-dependency-direction
- tests: none found
- Spec-Anchor: proj-spec/chapters/09-design-decisions.md#generate-and-generated-trees
- tests: none found
- Spec-Anchor: proj-spec/chapters/09-design-decisions.md#default-branch-for-diffs
- tests: none found
- Spec-Anchor: proj-spec/chapters/09-design-decisions.md#error-handling
- tests: none found

## Related chapters

- [README](../README.md)
- [3 Architecture](03-architecture.md)
- [4 Stack](04-stack.md)
