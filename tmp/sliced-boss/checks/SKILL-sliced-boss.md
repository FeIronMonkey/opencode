# Check — SKILL-sliced-boss

## Constitution clauses served
- C8, C10

## Artifact paths under test
- `/home/frederick/repos/opencode/tmp/sliced-boss-skill-spec.md`
- Paired task spec: `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/tasks/SKILL-sliced-boss.md`
- Constitution: `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/constitution.md` (C8, C10)
- Cross-check sources (re-open; do not trust the spec’s summaries):
  - `/home/frederick/.cursor/skills/executive-agent/SKILL.md` (D2, D6, D7, D11, roles)
  - `/home/frederick/repos/opencode/proj-spec/slicing.md` (pipeline heading, waves, indexes-after-children)
  - `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/worker-base.md`
  - `/home/frederick/repos/opencode/tmp/executive/opencode-retrospective-spec/instructions/checker-base.md`
  - `/home/frederick/.cursor/skills-cursor/create-skill/SKILL.md` (frontmatter, <500 lines, description)
  - `/home/frederick/repos/opencode/reviews/opencode-slice-process.md` (process lessons)
  - `/home/frederick/repos/opencode/reviews/opencode-slice-coverage.md` (hot-potato / overlap — generalized anti-pattern)

## Executable verification
1. Confirm the deliverable exists and is markdown.
2. Walk the **Coverage checklist** in the task spec. For each row: pass only if the deliverable has a corresponding normative section or explicit rule (not a vague mention).
3. Re-open `executive-agent/SKILL.md`: FAIL if the spec silently duplicates D2–D11 at length **and** fails to recommend extend vs companion vs standalone with a reason.
4. Re-open `slicing.md` pipeline: FAIL if inventory → map → bounded slices → waves or indexes-after-children is missing.
5. Re-open worker-base + checker-base: FAIL if instruction-pack / “shared files on disk” / “checkers do not receive worker self-report” is missing.
6. Confirm generic: FAIL if the skill’s When-to-use requires OpenCode or `proj-spec/` as the only work type.
7. Confirm Implementation notes mention skill `name` + `description` constraints from create-skill (or an explicit “implementer MUST follow create-skill”).
8. Confirm C8: no reconstructed PLAN/FINAL PASS; no instruction to change product code.
9. Confirm the spec does not instruct editing `proj-spec/HANDOFF.md` or installing a skill unless Implementation says so (default spec-only).
10. Line count: FAIL if >500 lines (create-skill SKILL.md cap; spec should be implementable without a novel).

## Pass conditions
- File exists at the named path
- Every coverage-checklist row is **pass**
- Steps 3–9 do not FAIL
- Findings are empty of blockers (non-blocking notes allowed)

## Checker constraints
- Receive only: this check spec, paired task spec, constitution C8/C10, artifact paths
- MUST NOT receive worker self-report or chain-of-thought
- Execute verification yourself; re-open sources
- MUST NOT edit deliverables
- Write findings only if you must: prefer returning Verdict/Findings/Evidence to the boss. Optional: `tmp/executive/opencode-retrospective-spec/findings/SKILL-sliced-boss.md` — if you write it, that path only
