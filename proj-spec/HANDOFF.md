# Handoff prompt — paste as the first message in a new chat

```
@spec-driven-workflow resume
@/home/frederick/.cursor/skills/spec-driven-workflow/SKILL.md
@/home/frederick/.cursor/skills/executive-agent/SKILL.md
@/home/frederick/.cursor/skills/spec-driven-greenfield-spec/SKILL.md

You are the **boss** for job `opencode-retrospective-spec`. Continue from the prior session. Do not restart T0 inventory, T1 chapter map, or T2 leaf specs.

## Original user goal (binding)

This repo was downloaded from an external source and must be properly specified per spec-driven-workflow. Orchestrate writing the spec. Sub-agents: Composer 2.5 or Grok 4.6 as below.

You serve as the boss: **neither write nor read nor review any code or specs** (`proj-spec/` chapter bodies, package source, or worker findings files). Coordinate sub-agents until a full spec exists and has been **fully reviewed** (REVIEW-SPEC PASS). Then **stop** and request user spec-gate approval. Do not write the implementation plan.

Each sub-agent operates on a **slice**: enough context to be accurate, small enough to be token-efficient. Accuracy must not be sacrificed; do not waste tokens. Manage progress in `tmp/tasks.md` so another agent can resume anywhere you stop. If you would repeat instructions with only a few parameters changed, put the repeated text in instruction files and pass parameters. If you would do something different than these instructions to hit the same goals, say so.

Slicing process (committed): `proj-spec/slicing.md`. Partial chapter index: `proj-spec/README.md`. Do not treat README as complete C11 coverage until W7.

## Mode and process

- **Retrospective greenfield**, not change-mode. Workflow `#retrospective-migration`. Do not reconstruct user approvals. Do not create `initial_spec.md`. Do not change product code.
- Current phase: `@spec-driven-greenfield-spec` / A1 / **W1 user-authorized rework** of 6.3, 6.6, 6.27. T0, T1, T2 accepted via PASS. User chose **full-repo** spec.
- Spec-only job. After REVIEW-SPEC PASS: Turn 1 approval request only (no plan handoff in that message).

## Git / branch (do this first)

Confirm branch. Spec work was started from `production` @ `73cfa68b75`. Progress commits belong on a spec branch (e.g. `retrospective-spec`), **not** on `production` (SST/console deploy: `.github/workflows/deploy.yml`). CLI/npm/desktop publish is `.github/workflows/publish.yml` on `dev`/`beta`. Spec this checkout’s tree unless the user says otherwise.

**Commit regularly** as waves/leaves get checker PASS (user 2026-09-09). Conventional commits, e.g. `docs(spec): accept W1 domain and SDK chapters`. Do not commit gitignored `tmp/` unless the user explicitly asks to force-add it. Do not push unless asked. Do not force-push.

`tmp/` is gitignored. Resume requires the local executive job dir: `tmp/executive/opencode-retrospective-spec/` (ledger, constitution, instructions, tasks, checks, findings). If those files are missing, stop and ask the user; do not re-invent T0–T2.

## Boss model / staffing

- Recommended boss tier: high judgment. Prior session model: Cursor Grok 4.6.
- **Chapter writers (remaining leaves): `cursor-grok-4.6-medium` only.** Composer 2.5 failed C1 on nearly every W1 first draft. Do not send remaining chapters to Composer.
- Checkers: **`cursor-grok-4.6-medium` only**. Never `cursor-grok-4.6-high-fast`. Fresh checker every check. Checker prompts must not include worker self-reports.
- Task `resume` cannot change model; new model ⇒ new Task, not resume.
- Cursor Task has no `readonly` flag; instruct checkers not to edit.

## Read first (orchestration only)

- `tmp/tasks.md`
- `tmp/executive/opencode-retrospective-spec/ledger.md`
- `tmp/executive/opencode-retrospective-spec/constitution.md`
- `tmp/executive/opencode-retrospective-spec/instructions/` (worker-base, checker-base, chapter-writer, chapter-checker, chapter-task-template, chapter-check-template)
- Per-leaf specs: `tasks/leaves/{id}.md`, `checks/leaves/{id}.md`

Do **not** read `findings/*.md` bodies, `proj-spec/chapters/*` bodies, or package sources. Consume checker-verified summaries and `proj-spec/README.md` status tables only.

## W1 status (do next)

Accepted via PASS: **8, 6.8, 6.11, 6.13, 6.16, 6.19, 6.25**.

**User 2026-09-09 authorized rework** of the three remaining W1 FAILs. Record in the ledger: D7 decision = **direct rework**, budget **3 worker attempts per slice** (write → fresh checker → retry with specific findings). Worker and checker: **`cursor-grok-4.6-medium` only** (not Composer, not high-fast). New Task per slice (do not resume Composer workers). Fresh checker every check. Checker prompts must not include worker self-reports. Commit after each slice that PASSes.

Do **not** start W2 until all three are PASS, or this budget is exhausted and you escalate to the user again.

### 6.3 `proj-spec/chapters/06.3-sqlite-adapters.md` — last FAIL `3fbe742c`

- C1: `MigratorInitError { exitCode: "databaseMigrations" }` and `{ exitCode: "localMigrations" }` were unsourced. Cite `packages/effect-drizzle-sqlite/src/sqlite-core/effect/session.ts` `migrate` (init / `exitCode` around the cited lines from that check).
- C1: “original failure is preserved after finalize” is false. `EffectSQLiteSession.withTransaction` finalize is `finalize.pipe(Effect.flatMap(() => exit))` in `packages/effect-drizzle-sqlite/src/effect-sqlite/session.ts`. If the body failed **and** rollback / `rollback to savepoint` also fails, the **rollback error replaces** the original body failure.

### 6.6 `proj-spec/chapters/06.6-httpapi-codegen.md` — last FAIL `684c72a1`

- C4: add a Verification Spec-Anchor for parent heading `#behavior` (`## Behavior`), even though child H3s already have lines. Name covering tests or `tests: none found` + OQ `Blocking: none`.
- Prior C1 (endpoint names / Promise `empty: true` only for `success === "void"`) was already fixed in that check — do not regress.

### 6.27 `proj-spec/chapters/06.27-web.md` — last FAIL `d50d8b7b`

- C1: `#open-graph-images` docs-page title is **not** “Base64-encoded, then truncated to 700 chars.” `packages/web/src/components/Head.astro` does `title.substring(0, 700)`, then `encodeURIComponent`, then `Base64.encode`, then another `encodeURIComponent`. Truncation is on the **raw** title. Same construction for share `encodedTitle` in `s/[id].astro` if that row claims encoding.
- Non-blocking (fix if cheap): share robots meta is `noindex, nofollow, noarchive, nosnippet`, not only `noindex`. `formatNumber` is locale `Intl` without USD; only `formatCurrency` uses `currency: "USD"`.

If any slice still FAILs after 3 worker attempts: **stop that slice**, escalate to the user again (unshippable or another budget). Do not open a fourth pass.

After all three PASS: W2 (6.4, 6.10) → W3 → W4 → W5 → W6 → W7 indexes/README/OQ. After all map leaves + README + §14 + open-questions: REVIEW-SPEC (parallel Part checkers + one synthesis checker → `reviews/opencode-spec.md`).

## Remaining waves (ids only)

- W2: 6.4, 6.10
- W3: 6.7, 6.12, 6.2, 6.22, 6.24
- W4: 6.5, 6.9, 6.14, 6.17, 6.26
- W5: 6.1, 6.15, 6.18, 6.20, 6.21, 6.23
- W6: 7.1, 7.2, 7.3, 7.4, 3, 4, 5, 9, 10.1, 10.2, 13, 11.1, 12.1, 14, 1, 2
- W7: indexes 6, 7, 10, 11, 12, README, open-questions (not in T2 leaf specs)

Chapter-path prefix: `proj-spec/chapters/`. Look up filename/allowed-paths in the leaf task spec.

## Do not

- Read or write product code or spec chapter bodies yourself
- Use Grok high-fast
- Start `@spec-driven-plan` without recorded spec-gate approval
- Accept worker “done” without checker PASS (except recorded D7 user accept/drop)
- Reconstruct historical user approvals or treat missing `reviews/` as PASS
- Restart inventory from scratch
- Treat 6.3 / 6.6 / 6.27 as PASS until a checker on this new budget returns PASS
- Start W2 while any of those three is still FAIL

## Suggested process (in force)

Inventory + chapter map before prose. Wave-based chapters. REVIEW-SPEC split by Part plus a synthesis artifact. Commit after each accepted wave (or each PASS leaf if the wave is large).
```
