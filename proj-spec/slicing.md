# How this spec is sliced

> **Process note (not a behavioral contract).** Product MUST/SHALL live in chapter files. This page records how the retrospective spec was decomposed so writers stay token-bounded and C3 (every workspace package has a home) stays checkable.

**Mode:** retrospective greenfield (`@spec-driven-greenfield-spec`). Implementation already exists; chapters describe **shipped** behavior. Workflow `#retrospective-migration` applies. No `initial_spec.md`. Product code is not changed for this job.

**Orchestration:** executive-agent job `opencode-retrospective-spec` (closed spec-only 2026-09-13). Historical task/check specs, constitution, and ledger may remain locally under gitignored `tmp/executive/opencode-retrospective-spec/`. Sliced-boss skill spec (kept): `tmp/sliced-boss/`. Accepted map details were `findings/T1-chapter-map.md` (checker PASS). Wave cards: `findings/T2-wave-index.md`.

## Why slice

A single agent cannot load this monorepo accurately. Inventory found **36** workspace packages. Largest approximate `*.ts`/`*.tsx`/`*.go` counts (excluding `node_modules`, `dist`, generated): `opencode` ~678, `app` ~596, `core` ~479, `ui` ~247, `tui` ~204.

Generated trees are not hand-authored source of truth: `packages/client/src/generated/`, `packages/client/src/generated-effect/`, `packages/sdk/js/src/v2/gen/` (`sdk/js/dist` was absent at inventory). Runtime layering (AGENTS.md): Schema → Core and Protocol → Server; Client never Core/Server; `sdk-next` composes Client+Core+Server. Package `opencode` does not runtime-depend on `core` (`devDependency` only).

## Pipeline (T0 → T1 → T2 → W1–W6 leaves → W7 indexes-after-children → REVIEW-SPEC)

1. **T0 inventory** — package list, surfaces, generated roots, dependency-direction quotes, size, slice-hint clusters. No chapter prose. Checker set-compared workspace names.
2. **T1 chapter map** — greenfield `#chapter-breakdown` numbering (Parts I–VI: §1–2 product, §3–5+§9 design, §6.x components, §7.x+§8 interface, §10.x+§13 ops, §11.x+§12.x+§14 validation). Every T0 package assigned to **exactly one leaf or explicit non-goal**. Indexes vs leaves distinguished. Write waves listed. User chose **full-repo** (not a bounded first product).
3. **T2 leaf specs** — one task spec + one check spec per **leaf** under `tmp/.../tasks/leaves/` and `checks/leaves/`. Chapter paths: `proj-spec/chapters/{T1 filename}`. Indexes (parent §6, §7, §10, §11, §12, README, open-questions) are **W7**, after children exist.
4. **W1–W6 leaves** — one worker per leaf; checker is a **fresh** `cursor-grok-4.6-medium` (never high-fast). Parallelize only independent slices. Do not accept a chapter without checker PASS (unless recorded D7 user accept / drop).
5. **W7 indexes-after-children** — parent §6, §7, §10, §11, §12, `README.md`, `open-questions.md` after leaf chapters exist.
6. **REVIEW-SPEC** — latest artifact `reviews/opencode-spec-r2.md` (PASS). Spec gate approved 2026-09-13. No plan from this job.

## Map size (checker-verified)

- **51** numbering rows: **7** indexes (README, open-questions, §6, §7, §10, §11, §12) + **44** leaves.
- **36/36** packages assigned; `storybook` → explicit **non-goal** (`non-goal:2`). Shared leaves include 6.1, 6.3, 6.22, 6.24.
- **Leaf ids:** 1, 2, 3, 4, 5, 9, 6.1–6.27, 7.1–7.4, 8, 10.1, 10.2, 13, 11.1, 12.1, 14.

## Write waves (T2)

| Wave | Slice ids | Notes |
|------|-----------|--------|
| W1 | 8, 6.3, 6.6, 6.8, 6.11, 6.13, 6.16, 6.19, 6.25, 6.27 | Independent. Complete/PASS. |
| W2 | 6.4, 6.10 | After W1 6.3 / 6.6 / 6.27 PASS (user rework budget 3× Grok medium) |
| W3 | 6.7, 6.12, 6.2, 6.22, 6.24 | |
| W4 | 6.5, 6.9, 6.14, 6.17, 6.26 | |
| W5 | 6.1, 6.15, 6.18, 6.20, 6.21, 6.23 | |
| W6 | 7.1–7.4, 3, 4, 5, 9, 10.1, 10.2, 13, 11.1, 12.1, 14, 1, 2 | Architecture + product + acceptance last |
| W7 | indexes only | §6, §7, §10, §11, §12, `README.md`, `open-questions.md` |

W1 filenames on disk: `08-domain-model.md`, `06.3-sqlite-adapters.md`, `06.6-httpapi-codegen.md`, `06.8-sdk.md`, `06.11-http-recorder.md`, `06.13-codemode.md`, `06.16-ui.md`, `06.19-desktop.md`, `06.25-function.md`, `06.27-web.md`.

## Slice rules for writers

- One concern per leaf (C2). Allowed paths come from the per-leaf task spec (package dirs + tests glob + T1 map). No `.mdx` citations.
- Generated trees: describe as generated; generator/script is the source of truth (C5).
- Every normative heading (including parent H2 **and** nested H3) needs a Verification Spec-Anchor: named test or `tests: none found` plus an in-chapter OQ with `Blocking: none` unless untestable.
- Related-chapter links from `proj-spec/chapters/` are **same-directory** (`10.1-install.md`), not `../chapters/…`.
- Cite the symbol that **emits** the string (regex, encoding, HTTP status on the handler that returns it).

## Staffing lesson (in force)

Composer 2.5 is too lossy for C1 on first draft. **All remaining chapter writers and all checkers: `cursor-grok-4.6-medium`.** Do not use `cursor-grok-4.6-high-fast`. Fresh checker every check. Checker prompts must not include worker self-reports.

## After all leaves

README index (C11), `14-acceptance.md`, `open-questions.md` (no blocking opens unless truly blocking). Extra reviews PASS (`reviews/opencode-slice-process.md`, `reviews/opencode-slice-coverage.md`). Latest REVIEW-SPEC is `reviews/opencode-spec-r2.md` (PASS `c56aa9a3`, commit `41f8a7d85e`); prior `reviews/opencode-spec.md` superseded. User **approved the spec gate 2026-09-13**. This job is **spec-only** — do not write `implementation-plan.md` from this pass; later product changes start `@spec-driven-change`. Session scratch `tmp/tasks.md` is closed per workflow `#tmp-tasks-close` (spec-only analogue; REVIEW-FINAL was not run and is not PASS).
