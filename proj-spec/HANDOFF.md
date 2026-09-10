# Handoff prompt — paste as the first message in a new chat

```
@spec-driven-workflow resume
@/home/frederick/.cursor/skills/spec-driven-workflow/SKILL.md
@/home/frederick/.cursor/skills/executive-agent/SKILL.md
@/home/frederick/.cursor/skills/spec-driven-greenfield-spec/SKILL.md
@/home/frederick/.cursor/skills/spec-driven-adversarial-review/SKILL.md

You are the **boss** for job `opencode-retrospective-spec`. Continue from the prior session. Do not restart T0 inventory, T1 chapter map, T2 leaf specs, W1–W7 writes, or REVIEW-SPEC from scratch.

## Original user goal (binding)

This repo was downloaded from an external source and must be properly specified per spec-driven-workflow. Orchestrate writing the spec. Sub-agents: `cursor-grok-4.6-medium` only for remaining work.

You serve as the boss: **neither write nor read nor review any code or spec chapter bodies** (`proj-spec/chapters/*`, package source, or worker findings file bodies). Coordinate sub-agents. Manage progress in `tmp/tasks.md`. If you would repeat instructions with only a few parameters changed, put the repeated text in instruction files and pass parameters. If you would do something different than these instructions to hit the same goals, say so.

Slicing process (committed): `proj-spec/slicing.md`. Chapter index: `proj-spec/README.md`. Official REVIEW-SPEC artifact: `reviews/opencode-spec.md` (PASS 2026-09-10; **does not** skip the extra reviews below).

## Mode and process

- **Retrospective greenfield**, not change-mode. Workflow `#retrospective-migration`. Do not reconstruct user approvals. Do not create `initial_spec.md`. Do not change product code.
- Current phase: `@spec-driven-greenfield-spec` / A3 / **post-REVIEW-SPEC extra reviews** (user-directed; unusual). T0–T2 and W1–W7 accepted via PASS. REVIEW-SPEC PASS exists. User has **not** approved the spec gate. Branch: `retrospective-spec`.
- Spec-only job. Do **not** start `@spec-driven-plan`. Do **not** request spec-gate approval until the extra reviews below have checker PASS (and REVIEW-SPEC is re-run if chapters change). After that: Turn 1 approval request only (no plan handoff in that message).

## Git / branch (do this first)

Confirm branch **`retrospective-spec`**. Spec work was started from `production` @ `73cfa68b75`. Progress commits belong on `retrospective-spec`, **not** on `production`. Spec this checkout’s tree unless the user says otherwise.

HEAD at last session pause: **`06aa148977`** `docs(spec): record REVIEW-SPEC PASS` (W7 indexes `1d6afafa7c`; REVIEW-SPEC artifact + Part-fix chapters). Working tree should be clean of untracked spec drafts.

**Commit regularly** as extra-review waves get checker PASS (user 2026-09-09). Conventional commits, e.g. `docs(spec): accept slice-process review`. Do not commit gitignored `tmp/` unless the user explicitly asks to force-add it. Do not push unless asked. Do not force-push.

`tmp/` is gitignored. Resume requires the local executive job dir: `tmp/executive/opencode-retrospective-spec/` (ledger, constitution, instructions, tasks, checks, findings). If those files are missing, stop and ask the user; do not re-invent T0–T2.

## Boss model / staffing

- Recommended boss tier: high judgment. Prior session model: Cursor Grok 4.6.
- Writers and checkers: **`cursor-grok-4.6-medium` only.** Do not use Composer. Never `cursor-grok-4.6-high-fast`. Fresh checker every check. Checker prompts must not include worker self-reports.
- Task `resume` cannot change model; new model ⇒ new Task. Cross-session `resume` often fails **parent mismatch** — then launch a **new** Task.
- Cursor Task has no `readonly` flag; instruct checkers not to edit (except a named findings/review path).
- Spawn **as many parallel reviewers as needed** for accuracy without stuffing one context. Prefer several bounded slices over one mega-reviewer.

## Read first (orchestration only)

- `tmp/tasks.md`
- `tmp/executive/opencode-retrospective-spec/ledger.md`
- `tmp/executive/opencode-retrospective-spec/constitution.md`
- `tmp/executive/opencode-retrospective-spec/instructions/` (worker-base, checker-base, chapter-writer, chapter-checker, review-spec-part, review-spec-synthesis)
- Process docs (not chapter bodies): `proj-spec/slicing.md`, `proj-spec/README.md` status/tables of contents only, `reviews/opencode-spec.md` verdict line only

Do **not** read `findings/*.md` bodies, `proj-spec/chapters/*` bodies, or package sources. Consume checker-verified summaries only.

## Done (do not redo)

- T0 inventory, T1 map, T2 leaf specs — accepted via PASS
- W1–W6: all 44 leaves PASS (leaf 14 is `proj-spec/chapters/14-acceptance.md`)
- W7: parent indexes §6/§7/§10/§11/§12, README C11, `open-questions.md` — checker `a2de02b8` PASS; commit `1d6afafa7c`
- REVIEW-SPEC: Part checkers + synthesis `66b649ca` PASS → `reviews/opencode-spec.md`; commit `06aa148977`
- REVIEW-SPEC was **not** one agent reading every chapter; it was Parts (III split IIIa 6.1–6.13 / IIIb 6.14–6.27) plus synthesis. First Part round FAIL then D7 chapter fixes then re-check then synthesis.

## Unusual extra reviews — do this next (user 2026-09-10)

These are **in addition to** REVIEW-SPEC. They audit the **slicing system**, not a repeat of C1 line-by-line chapter vs code (already done per leaf + REVIEW-SPEC). Author task spec + check spec **before** dispatch (executive D4/D6). Findings under `tmp/executive/opencode-retrospective-spec/findings/`. Optional committed write-up under `reviews/` only after checker PASS (e.g. `reviews/opencode-slice-process.md`, `reviews/opencode-slice-coverage.md`).

If extra reviews require chapter edits: workers fix; checkers PASS; **re-run REVIEW-SPEC** (prior PASS superseded). Then spec-gate Turn 1. Do not treat extra-review FAIL as “still ship REVIEW-SPEC PASS.”

### R-slice-process — slicing process as documented

**Question:** Does the documented slicing process actually match how the spec was built, and is that process sound for a full-repo retrospective?

**Inputs (reviewers may read these; boss still does not read chapter bodies):** `proj-spec/slicing.md`; T1/T2 findings paths by name; `tmp/.../tasks/leaves/` and `checks/leaves/` filenames; wave notes in the ledger; greenfield `#chapter-breakdown`; constitution C2/C3/C10/C11; `proj-spec/README.md` index structure.

**Hunt:** process vs practice (waves, indexes-after-leaves, package→exactly-one-leaf-or-non-goal, generated-tree rule, no `.mdx`); missing/weak process steps; `slicing.md` stale vs disk (W7/REVIEW-SPEC already happened); whether one-concern-per-leaf and allowed-path rules would systematically drop cross-cutting behavior.

**Staffing:** at least **two** parallel checkers (process-doc vs workflow; process-doc vs T1/T2/ledger practice) plus a **fresh** synthesis checker that writes the process-review artifact. Add more if a checker reports context overflow.

### R-slice-coverage — overlap and gaps between slices

**Question:** What shipped behavior was omitted or dual-homed because it looked like it belonged to **another** slice too, or to **no** slice?

**Inputs:** T0 package/surface list (checker-verified summary in ledger); T1 assignment table; per-leaf `allowed-paths` in T2 task specs; workspace `packages/*` names; bins/scripts/CI/docs/non-workspace trees; chapter **Related** / parent indexes (reviewers open chapters; boss does not).

**Hunt (must be specific: path or symbol + which slices wrongly claimed / none claimed):**
- **Gaps / orphans:** package, bin, script, surface, or generated tree with no leaf and no explicit non-goal (C3 holes beyond `storybook` → `non-goal:2`)
- **Hot-potato omissions:** behavior on a boundary (e.g. CLI listen vs `packages/server`, generate vs httpapi-codegen, HTTP catalog vs handlers, share HTTP vs web client, workspace test guard vs acceptance) that each slice could treat as the other’s job — confirm it is specified in **exactly one** canonical chapter or filed as OQ
- **Silent overlap:** two leaves specifying the same MUST as SoT without a canonical link (C2)
- **Scope leftover:** T0 clusters / repo paths never assigned (vscode extras, `script/`, `patches/`, CI, marketing copy, cloud-only, etc.)

**Staffing (parallel; spawn more if a slice is too large):**
- C3 re-set-compare: workspace packages ↔ T1 ↔ chapter files
- Boundary pairs (separate reviewers): 6.1/6.5/6.15 (agent CLI / server / lildax); 6.4/6.5/7.1 (protocol / server / HTTP catalog); 6.6/6.7/6.8/6.9/7.2/10.2 (codegen / client / SDKs / generate); 6.18/6.19 (app / desktop); 6.21/6.23/6.25/6.27 (console / stats / function / web); 8 vs 7.1 (schema vs events/HTTP); 11.1 vs 6.x surfaces; 12.1 vs 14 (`scripts.test`); 10.1 vs 6.1/6.15/6.19 install
- Orphan pass: globs outside `packages/*` workspace members
- **Fresh synthesis** checker: merge findings; `reviews/opencode-slice-coverage.md`; FAIL if any orphan or hot-potato gap is unassigned and not an explicit non-goal/OQ

Do not accept “done” without checker PASS. Do not have synthesis trust part self-reports — re-verify blockers.

## After extra reviews PASS

1. Commit review artifacts (and any accepted spec fixes).
2. If chapters changed: full REVIEW-SPEC again → new or `-rN` artifact.
3. Stop for **user spec-gate Turn 1** only. Do not write `implementation-plan.md`.

## Remaining (ids only)

- R-slice-process
- R-slice-coverage (overlap / hot-potato / orphans)
- Re-REVIEW-SPEC if spec files change
- User spec-gate Turn 1
- Plan — blocked

## Do not

- Read or write product code or spec chapter bodies yourself
- Use Grok high-fast or Composer for remaining spec
- Start `@spec-driven-plan` without recorded spec-gate approval
- Treat `reviews/opencode-spec.md` PASS as skipping R-slice-process or R-slice-coverage
- Accept worker “done” without checker PASS (except recorded D7 user accept/drop)
- Reconstruct historical user approvals
- Restart inventory or rewrite W1–W7 unless an extra-review FAIL names specific files
- Request spec-gate approval before extra-review PASS

## Suggested process (in force)

Inventory + chapter map before prose. Wave-based chapters. REVIEW-SPEC split by Part plus synthesis. **Then** (this pause) process-slicing review + overlap/gap review with many parallel checkers. Commit after each accepted wave.
```
