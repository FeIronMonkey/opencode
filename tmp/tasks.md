# OpenCode — Task List

## Session
- Skill: `@spec-driven-workflow` → `@spec-driven-greenfield-spec` (A1)
- Mode: **retrospective greenfield** — implementation exists; write chapters that describe shipped behavior. Not change-mode (no behavior evolution).
- Topic slug: none (greenfield session label)
- Job ledger: `tmp/executive/opencode-retrospective-spec/ledger.md`
- Constitution: `tmp/executive/opencode-retrospective-spec/constitution.md`
- Started: 2026-09-09
- Resume phase: **job close / spec-only** (2026-09-13). Spec gate **approved**. Do not write a plan. Do not start `@spec-driven-plan` or `@spec-driven-tdd`. Future product work starts `@spec-driven-change`.

- Handoff prompt for extra-review successor (historical): `proj-spec/HANDOFF.md` — do not follow it as current next steps.

## Commit strategy
User confirmed 2026-09-09: commit regularly to track spec-writing. One conventional-commit per accepted wave (or per PASS leaf if large). Spec on branch `retrospective-spec` (not `production`). Do not commit gitignored `tmp/` unless asked. Do not push unless asked.

## Boss / executive
- Recommended boss tier: high judgment
- Actual session model: Cursor Grok 4.6
- Remaining chapter writers: `cursor-grok-4.6-medium` only (Composer retired after W1 C1 FAILs)
- Checkers: `cursor-grok-4.6-medium` only (do not use high-fast)
- Instruction pack: `tmp/executive/opencode-retrospective-spec/instructions/`

## Spec phase (greenfield / retrospective)
- [x] T0 inventory findings accepted (`findings/T0-inventory.md`) — 2026-09-09 checker `cf88183c` PASS
- [x] T1 chapter map accepted (`findings/T1-chapter-map.md`) — 2026-09-09 checker `890ac622` PASS
- [x] User decision: full-repo spec vs bounded first product — **full-repo** 2026-09-09
- [x] T2 per-leaf task/check specs accepted — checker `07654190` PASS
- [x] Chapters written (all 44 map leaves) — 2026-09-09
- [x] README index (C11; W7) — 2026-09-10 checker `a2de02b8` PASS
- [x] `proj-spec/chapters/14-acceptance.md` (leaf 14 PASS; not `14-acceptance-criteria.md`)
- [x] `open-questions.md` (no blocking opens) — W7 checker PASS 2026-09-10
- [x] REVIEW-SPEC r2 (`reviews/opencode-spec-r2.md`) — PASS `c56aa9a3` (commit `41f8a7d85e`); prior `opencode-spec.md` superseded
- [x] R-slice-process PASS (`reviews/opencode-slice-process.md`) — 2026-09-10 synthesis `949673bc`
- [x] R-slice-coverage PASS (`reviews/opencode-slice-coverage.md`) — 2026-09-10 synthesis `7643d84a` path check `c0832ac2`
- [x] User approved spec gate — 2026-09-13

### Extra-review parts (2026-09-10)
- [x] RSP-workflow findings — PASS `7affbf4f`
- [x] RSP-practice findings — FAIL `2b0bbf09` then fix PASS `91e5f0bb`
- [x] RSC-c3 — PASS `e10c0978` (36/36; storybook non-goal:2; unmatched ∅)
- [x] RSC-b-test (12.1 vs 14) — FAIL then fix PASS `048bab3e`
- [x] RSC-b-cli (6.1/6.5/6.15) — FAIL then http-cli-fix PASS `381b68b1`
- [x] RSC-b-http (6.4/6.5/7.1) — FAIL then http-cli-fix PASS `381b68b1`
- [x] RSC-b-desktop (6.18/6.19) — FAIL then install-desktop-fix PASS `13785099`
- [x] RSC-b-schema (8 vs 7.1) — FAIL then fix PASS `27920236`
- [x] RSC-b-install (10.1 vs 6.1/6.15/6.19) — FAIL then install-desktop-fix PASS `13785099`
- [x] RSC-b-examples (11.1 vs 6.x) — FAIL then fix PASS `c9b3288d`
- [x] RSC-orphan — FAIL then fix PASS `09ee715f`
- [x] RSC-b-sdk (6.6–6.9/7.2/10.2) — FAIL then fix PASS `01129d9b`
- [x] RSC-b-cloud (6.21/6.23/6.25/6.27) — FAIL then fix PASS `bda6d988`
- [x] RSC-b-examples (11.1 vs 6.x) — FAIL then fix PASS `c9b3288d`
- [x] RSC-orphan — FAIL then fix PASS `09ee715f`
- [x] RSP-synthesis PASS `949673bc` (`reviews/opencode-slice-process.md`)
- [x] RSC-synthesis PASS `7643d84a` + path `c0832ac2` (`reviews/opencode-slice-coverage.md`)
- [x] RS-r2-I — PASS `32c05bf0`
- [x] RS-r2-II — PASS `c56d4f4a`
- [x] RS-r2-IIIa — PASS `2d5612fb`
- [x] RS-r2-IIIb — PASS `89066e20`
- [x] RS-r2-IV — PASS `5f79ce80`
- [x] RS-r2-V — FAIL `1a0ab678` then upgrade PASS `6116a64e`; hunt FAIL `8696ae3e`; OQ-10.1-9 PASS `661f545d`; Part V re-check **PASS** `bfbb3aa3`
- [x] RS-V-r2-oq — PASS `d9f88046` (inbox already in `27b50ebf8a`)
- [x] RS-r2-VI — FAIL `5248bb82` then fix PASS `a0c9b351`; Part VI re-check **PASS** `38db5674`
- [x] RS-r2-synthesis — PASS `c56aa9a3` (`reviews/opencode-spec-r2.md`, `41f8a7d85e`)

## Plan phase
**Out of scope for this job** (user 2026-09-13: no plan for changes). Do not author `proj-spec/implementation-plan.md` or any change-plan from this session.
- [x] Plan written — N/A not this job (2026-09-13). Not a reconstructed PASS.
- [x] REVIEW-PLAN PASS — N/A not this job. No plan review artifact.
- [x] User approved plan gate — N/A not this job.

## Implementation / change stages
Not in scope for this job (spec-only retrospective). Historical TDD / REVIEW-STAGE gates were never run — see workflow `#retrospective-migration`. Do not reconstruct them as PASS. Do not demand code changes because those gates were skipped.
- [x] Stage 0…N / REVIEW-STAGE — N/A not this job (2026-09-13)

## Close
- [x] Spec-only close — 2026-09-13. This pass produced `proj-spec/` + `reviews/opencode-spec-r2.md`, `reviews/opencode-slice-process.md`, `reviews/opencode-slice-coverage.md`. Historical implementation predates the spec.
- [x] REVIEW-FINAL — N/A not this job. Missing FINAL is **not** PASS (`#retrospective-migration`). Spec-only analogue of `#tmp-tasks-close` applied 2026-09-13.
- [x] TDD stages / REVIEW-STAGE — N/A not this job
- [x] Skill spec kept: `tmp/sliced-boss/` (checker `a48f4d94` PASS 2026-09-13)
- [x] Session scratch pad complete — ready for `#tmp-tasks-close` commit then delete (2026-09-13)
- Later product changes: start `@spec-driven-change`, not greenfield plan from this job. Record retrospective vs gate-complete in that change log.

## Wave checklist (full-repo)
- [x] W1: 10/10 chapter PASS (8, 6.3, 6.6, 6.8, 6.11, 6.13, 6.16, 6.19, 6.25, 6.27) — 2026-09-09
- [x] W2: 6.4, 6.10 PASS — 2026-09-09
- [x] W3: 6.7, 6.12, 6.2, 6.22, 6.24 PASS — 2026-09-09
- [x] W4: 6.5, 6.9, 6.14, 6.17, 6.26 PASS — 2026-09-09
- [x] W5: 6.1, 6.15, 6.18, 6.20, 6.21, 6.23 PASS — 2026-09-09
- [x] W6: 7.1–7.4, 3, 4, 5, 9, 10.1, 10.2, 13, 11.1, 12.1, 14, 1, 2 PASS — 2026-09-09
- [x] W7 indexes: §6, §7, §10, §11, §12, README, OQ — 2026-09-10 `1d6afafa7c`



## Resume instructions for a successor boss
This job is **closed (spec-only)**. `#tmp-tasks-close` removes this file from the tree after the snapshot commit. Durable product record: `proj-spec/` + `reviews/opencode-spec-r2.md`. Sliced-boss skill spec: `tmp/sliced-boss/`. Local executive job dir may remain gitignored under `tmp/executive/opencode-retrospective-spec/`. Product behavior changes: `@spec-driven-change`.
