# Task — SKILL-sliced-boss: Sliced-boss skill specification

## Constitution clauses served
- C8 (retrospective / no fake gates / no product-code demand)
- C10 (stay in allowed paths)
- C11 spirit: README is an index — this spec is process, not a second product spec

## Objective
Write a **skill specification** someone could implement as a Cursor skill: roles, artifacts, dispatch rules, anti-patterns, and checkable “done.” Capture the **slicing method** and **instruction-file economy** practiced on job `opencode-retrospective-spec`. The skill MUST be **generic** for any work that can be sliced. OpenCode / spec-driven examples are optional scenario notes only — not the only mode.

## Inputs (allowed paths — C10)

Read these. Do not open `proj-spec/chapters/*` bodies or package source.

### Process (this job)
- `/home/frederick/repos/opencode/proj-spec/HANDOFF.md` (historical extra-review prompt; do not edit)
- `/home/frederick/repos/opencode/proj-spec/slicing.md`
- `/home/frederick/repos/opencode/tmp/tasks.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/ledger.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/constitution.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/worker-base.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/checker-base.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/chapter-writer.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/chapter-checker.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/review-spec-part.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/extra-review-part.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/review-spec-synthesis.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/slice-coverage-synthesis.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/slice-process-synthesis.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/tasks/T0-inventory.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/tasks/T1-chapter-map.md`
- `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/tasks/T2-leaf-specs.md`
- One example leaf task + check under `tasks/leaves/` and `checks/leaves/` (filenames only + **one** pair opened as the thin-parameter example)
- Directory listings of `instructions/`, `tasks/`, `checks/` (names, not every file body)

### Skills
- `/home/frederick/.cursor/skills/executive-agent/SKILL.md`
- `/home/frederick/.cursor/skills/executive-agent/reference.md`
- `/home/frederick/.cursor/skills-cursor/create-skill/SKILL.md` (SKILL.md frontmatter, progressive disclosure, <500 lines, description WHAT+WHEN)
- `/home/frederick/.cursor/skills/spec-driven-workflow/SKILL.md` — **scenario note only** (phase sequence / resume / gates). Do not fork SDD skills.
- `/home/frederick/.cursor/skills/spec-driven-workflow/reference.md` sections `#resume-protocol`, `#retrospective-migration`, `#tmp-tasks-close` only if needed for scenario notes

### Reviews (process lessons, not chapter rewrites)
- `/home/frederick/repos/opencode/reviews/opencode-slice-process.md`
- `/home/frederick/repos/opencode/reviews/opencode-slice-coverage.md`
- `/home/frederick/repos/opencode/reviews/opencode-spec-r2.md` (findings about process: many part checkers, stale README status, spawn-many)

### Slice granularity evidence (structure only)
- `/home/frederick/repos/opencode/proj-spec/README.md` — Status + chapter **tables** (filenames/ids), not chapter bodies
- Immediate-import hop allowed: list `proj-spec/chapters/*.md` **filenames** to evidence leaf count / numbering (do not read chapter contents)

## Deliverable
Write `/home/frederick/repos/opencode/tmp/sliced-boss-skill-spec.md`.

This is a **spec for a skill**, not necessarily a finished `~/.cursor/skills/*/SKILL.md`. Include an implementation recommendation: file layout for a future skill (SKILL.md vs reference.md) per create-skill progressive disclosure.

Do **not** install the skill under `~/.cursor/skills/` unless this spec’s “Implementation” section explicitly says the first drop is SKILL.md (default: spec-only in `tmp/`).

## Design decision the spec MUST resolve
`executive-agent` already defines boss / worker / checker, constitution-first, D2–D11, ledger, D7 retries, independent checks. **Do not assume a duplicate skill with a new name is better.** The spec MUST recommend one of:

1. **Extend `executive-agent`** (new SKILL.md / reference.md sections: slicing pipeline + instruction-pack economy), or
2. **Companion skill** that MUST invoke `@executive-agent` and only adds slicing + instruction files, with a stated reason the extension would bloat the base skill, or
3. **Standalone** only if (1) and (2) fail a named criterion.

Cite `executive-agent` clause ids (D2–D11) rather than restating them at length. Spend words on **gaps this job filled**: slicing inventory→map→bounded slices→waves; instruction packs; thin parameter files; synthesis re-verify; resume via ledger + `tmp/tasks.md`.

## Required sections in the deliverable

1. **Purpose and when to use** — generic; trigger terms for a future `description:` field (third person, WHAT + WHEN).
2. **Relationship to `executive-agent`** — the decision above; non-goals: do not replace D6/D7/D8.
3. **Roles** — boss (orchestrates, does not author deliverables except whitelist / recorded exception); workers; checkers (fresh, no worker self-report); synthesis checkers.
4. **Slicing method** — inventory → map → bounded slices → waves; one concern per slice; allowed-path / context budget; indexes/aggregates **after** children when that applies; parallelize only independent slices; spawn many reviewers rather than one mega-context.
5. **Instruction-pack layout** — shared files on disk (`worker-base`, `checker-base`, plus wave/task overlays). Thin per-task parameter files (paths, slice id, extra coverage rows). Boss MUST NOT regenerate long prompts per agent.
6. **Sub-agent management (token-efficient)** — checkers never receive worker self-reports; fresh checker per check; synthesis re-verifies rather than trusting part reports; resume via ledger + `tmp/tasks.md` rather than chat history; Task `resume` parent-mismatch → new Task.
7. **Success factors (normative for the skill)** — constitution-first; task spec + check spec before dispatch; do not accept “done” without checker PASS (except recorded D7 user/boss-override); D7 retries with **specific** findings; Cursor Task has no `readonly` flag — instruct checkers not to edit except a named findings path.
8. **Artifacts** — constitution, task/check specs, ledger, instruction pack, findings, `tmp/tasks.md`; what the boss loads vs what children load.
9. **Dispatch rules** — staffing by slice independence; part checkers then synthesis; file-lock / sequential waves when slices share write targets.
10. **Anti-patterns** — mega-reviewer; pasting instruction text into every prompt; checker given worker CoT; boss authoring deliverables; boss reading every source; accepting worker “done”; reconstructing chat instead of ledger; one-concern violations / hot-potato gaps (from slice-coverage lessons, generalized).
11. **Checkable done** — observable pass conditions for “the parent acted as a sliced boss” (instruction files exist and prompts are thin; each slice has task+check; checkers are fresh; synthesis cites re-opened sources; ledger records models/verdicts; map covers inventory).
12. **Optional scenario: spec-driven retrospective** — pointer only.
13. **Implementation notes** — proposed `name`, `description`, SKILL.md vs `reference.md` split, `disable-model-invocation` default, do not write scripts/hooks unless justified.

## Constraints
- MUST be implementable (roles, paths, rules, anti-patterns, done).
- MUST NOT rewrite product spec chapters.
- MUST NOT author `implementation-plan.md` or change product packages.
- MUST NOT treat OpenCode filenames as the only slice taxonomy (packages/chapters are an example).
- SHOULD keep the deliverable under ~400 lines; put exhaustive quotes in citations, not dumps.

## Out of scope for this task
- Installing `~/.cursor/skills/`
- Editing `executive-agent` or `spec-driven-*` skill files
- Editing `proj-spec/HANDOFF.md`
- Plan / TDD / REVIEW-FINAL

## Coverage checklist
- [ ] Purpose/when-to-use is generic (not OpenCode-only)
- [ ] Relationship to executive-agent resolved (extend / companion / standalone + reason)
- [ ] Slicing pipeline specified (inventory → map → slices → waves)
- [ ] One concern per slice + allowed-path budget
- [ ] Indexes/aggregates after children when applicable
- [ ] Instruction-pack + thin parameter files (no long regenerated prompts)
- [ ] Checkers: no worker self-report; fresh per check
- [ ] Synthesis re-verifies
- [ ] Resume via ledger + tmp/tasks.md
- [ ] Constitution-first; task+check before dispatch
- [ ] D7 specific findings; no “done” without PASS
- [ ] Spawn many vs mega-context
- [ ] Anti-patterns listed
- [ ] Checkable done listed
- [ ] create-skill constraints reflected in Implementation notes (name, description, progressive disclosure)
- [ ] Optional SDD scenario is optional
- [ ] Citations to allowed sources (paths + headings)
