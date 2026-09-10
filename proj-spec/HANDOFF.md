# Handoff prompt — paste as the first message in a new chat

```
@spec-driven-workflow resume
@/home/frederick/.cursor/skills/spec-driven-workflow/SKILL.md
@/home/frederick/.cursor/skills/executive-agent/SKILL.md
@/home/frederick/.cursor/skills/spec-driven-greenfield-spec/SKILL.md

You are the **boss** for job `opencode-retrospective-spec`. Continue from the prior session. Do not restart T0 inventory, T1 chapter map, T2 leaf specs, or W1–W6 chapter writes.

## Original user goal (binding)

This repo was downloaded from an external source and must be properly specified per spec-driven-workflow. Orchestrate writing the spec. Sub-agents: Composer 2.5 or Grok 4.6 as below.

You serve as the boss: **neither write nor read nor review any code or specs** (`proj-spec/` chapter bodies, package source, or worker findings files). Coordinate sub-agents until a full spec exists and has been **fully reviewed** (REVIEW-SPEC PASS). Then **stop** and request user spec-gate approval. Do not write the implementation plan.

Each sub-agent operates on a **slice**: enough context to be accurate, small enough to be token-efficient. Accuracy must not be sacrificed; do not waste tokens. Manage progress in `tmp/tasks.md` so another agent can resume anywhere you stop. If you would repeat instructions with only a few parameters changed, put the repeated text in instruction files and pass parameters. If you would do something different than these instructions to hit the same goals, say so.

Slicing process (committed): `proj-spec/slicing.md`. Chapter index: `proj-spec/README.md` (status tables still lag W6; C11 is W7).

## Mode and process

- **Retrospective greenfield**, not change-mode. Workflow `#retrospective-migration`. Do not reconstruct user approvals. Do not create `initial_spec.md`. Do not change product code.
- Current phase: `@spec-driven-greenfield-spec` / A2 / **W7 indexes**. T0, T1, T2 accepted via PASS. User chose **full-repo** spec. Branch: `retrospective-spec`.
- Spec-only job. After REVIEW-SPEC PASS: Turn 1 approval request only (no plan handoff in that message).

## Git / branch (do this first)

Confirm branch **`retrospective-spec`**. Spec work was started from `production` @ `73cfa68b75`. Progress commits belong on `retrospective-spec`, **not** on `production`. Spec this checkout’s tree unless the user says otherwise.

HEAD at last session pause: **`8ecc6badb0`** `docs(spec): accept remaining W6 leaf chapters`. Working tree should be clean of untracked W6 drafts.

**Commit regularly** as waves get checker PASS (user 2026-09-09). Conventional commits, e.g. `docs(spec): accept W7 indexes and open questions`. Do not commit gitignored `tmp/` unless the user explicitly asks to force-add it. Do not push unless asked. Do not force-push.

`tmp/` is gitignored. Resume requires the local executive job dir: `tmp/executive/opencode-retrospective-spec/` (ledger, constitution, instructions, tasks, checks, findings). If those files are missing, stop and ask the user; do not re-invent T0–T2.

## Boss model / staffing

- Recommended boss tier: high judgment. Prior session model: Cursor Grok 4.6.
- Writers and checkers: **`cursor-grok-4.6-medium` only.** Do not use Composer for remaining spec work. Never `cursor-grok-4.6-high-fast`. Fresh checker every check. Checker prompts must not include worker self-reports.
- Task `resume` cannot change model; new model ⇒ new Task. Cross-session `resume` often fails **parent mismatch** — then launch a **new** Task.
- Cursor Task has no `readonly` flag; instruct checkers not to edit.
- Prior W7 worker was **interrupted** — do **not** resume that Task; dispatch a **new** W7 worker.

## Read first (orchestration only)

- `tmp/tasks.md`
- `tmp/executive/opencode-retrospective-spec/ledger.md`
- `tmp/executive/opencode-retrospective-spec/constitution.md`
- `tmp/executive/opencode-retrospective-spec/instructions/` (worker-base, checker-base, **w7-writer**, chapter-writer, chapter-checker, w4-writer, w4-checker)
- W7: `tasks/W7-indexes.md`, `checks/W7-indexes.md`

Do **not** read `findings/*.md` bodies, `proj-spec/chapters/*` bodies, or package sources. Consume checker-verified summaries and `proj-spec/README.md` status tables only.

## Wave status

**W1–W6 complete.** All 44 T2 leaves PASS and committed (leaf 14 path is `proj-spec/chapters/14-acceptance.md`).

**W7 not on disk.** Indexes not written. Interrupted worker produced no parent files. README still says W5 complete / W6 remaining and lists Parts I–II / 7.x / 10.x as not written.

### W7 — do this next (specs already exist)

Dispatch **one** `cursor-grok-4.6-medium` worker with `tasks/W7-indexes.md` + `instructions/w7-writer.md`. Then a **fresh** checker with `checks/W7-indexes.md` (no worker self-report).

T1 index paths (under `proj-spec/`, not `chapters/`):

- `06-components.md` — links 6.1–6.27
- `07-interface.md` — links 7.1–7.4 (and §8)
- `10-operations.md` — links 10.1–10.2
- `11-examples.md` — links 11.1
- `12-testing.md` — links 12.1
- `README.md` — full C11 (every `chapters/*.md` once; How to use; empty Change history; no product MUST/SHALL except navigation)
- `open-questions.md` — workflow `#open-questions` template; ingest in-chapter `OQ-*` stubs (`Blocking: none` unless already blocking)

After W7 checker PASS: commit indexes; then REVIEW-SPEC (parallel Part checkers + one synthesis checker → `reviews/opencode-spec.md`). Stop for user spec-gate approval. Do not start `@spec-driven-plan`.

## Remaining (ids only)

- W7: indexes 6, 7, 10, 11, 12, README, open-questions
- REVIEW-SPEC → user spec-gate Turn 1

## Do not

- Read or write product code or spec chapter bodies yourself
- Use Grok high-fast or Composer for remaining spec
- Start `@spec-driven-plan` without recorded spec-gate approval
- Accept worker “done” without checker PASS (except recorded D7 user accept/drop)
- Reconstruct historical user approvals or treat missing `reviews/` as PASS
- Restart inventory or rewrite W1–W6 leaves
- Start REVIEW-SPEC until W7 checker PASS
- Resume the interrupted W7 Task; launch new

## Suggested process (in force)

Inventory + chapter map before prose. Wave-based chapters. REVIEW-SPEC split by Part plus a synthesis artifact. Commit after each accepted wave (or each PASS leaf if the wave is large).
```
