# Review: R-slice-process — OpenCode
> **Verdict:** PASS
> **Reviewer model:** cursor-grok-4.6-medium
> **Implementer model:** cursor-grok-4.6-medium
> **Artifact reviewed:** proj-spec/slicing.md, T1/T2 map practice, ledger waves, #chapter-breakdown

## Blockers (must fix before progression)
- none

## Findings (non-blocking)
- `proj-spec/slicing.md` Slice rules restate C10 as per-leaf task-spec paths only (package dirs + tests glob + T1 map) and omit constitution C10’s immediate-import exception. Writers who follow slicing.md literally may under-cite import graphs or over-OQ. Mitigations remain: Related-chapter links, shared leaves 6.1/6.3/6.22/6.24, W6 interface leaves, W7 indexes, REVIEW-SPEC, this extra review.
- Greenfield slicing-checklist “no orphan requirements” is not a writer bullet in slicing.md. C3 is package-complete, not requirement-complete. Residual requirement orphans are delegated to W7/REVIEW-SPEC / R-slice-coverage, not a process-rule contradiction with C2.
- `no .mdx` is stricter than C10 and can starve Starlight page prose on leaf 6.27 unless other allowed files encode it. Process does not assign MDX-only content to another leaf.
- `proj-spec/README.md` Status (2026-09-10) still says “Next: REVIEW-SPEC.” Ledger and `reviews/opencode-spec.md` record REVIEW-SPEC PASS; slicing.md already records that. Index lag only — not a dual SoT and not reconstructed approval (status line disclaims gate verdict).
- `findings/T2-wave-index.md` lists W1–W6 only (44 leaves). Matches T2 (“indexes not instantiated here”) and slicing.md W7 = indexes after children.
- T2 `generated-in-slice: yes` includes 7.2 in addition to T1 §5 rows 6.7/6.8/6.16/6.24/10.2 (6.6 producer `no`). Consistent with C5 (interface leaf covering generated SDK surface), not a map-size contradiction.
- Ledger tail `## Delegation report` still says “W1 chapters pending”; Waves section above it is current. Out of slicing.md scope.

## Checklist
- [x] slicing.md matches how the spec was built (or names the delta as a blocker)
- [x] Process is sound for full-repo retrospective (C2/C3/C10 do not silently drop cross-cuts)
- [x] Indexes-after-leaves and package assignment rules held
- [x] No reconstructed approvals / no initial_spec.md (C8)

## Re-verification notes

**RSP-practice stale FAIL not re-confirmed.** `findings/RSP-practice.md` (checker `2b0bbf09`) FAILed `proj-spec/slicing.md` for pipeline heading “already done through T2”, W1 Notes “in progress at handoff”, `14-acceptance-criteria.md`, and REVIEW-SPEC treated as future. Current `proj-spec/slicing.md` (practice-fix worker `3860da3e` / checker `91e5f0bb`) does not contain those phrases: pipeline is `T0 → T1 → T2 → W1–W6 leaves → W7 indexes-after-children → REVIEW-SPEC`; W1 Notes `Complete/PASS`; After all leaves names `14-acceptance.md`; REVIEW-SPEC recorded as wrote `reviews/opencode-spec.md` (verdict PASS) with spec-gate unrecorded. Do not keep those blockers.

**RSP-workflow `7affbf4f` PASS re-confirmed.** T1 Parts I–VI match `#chapter-breakdown` Recommended parts. W7 indexes-after-children matches authoring workflow step 5. C2+C10 can omit consumer-side MUST from the canonical leaf; mitigations exist (immediate imports in constitution; Related links; shared/interface leaves; W7; REVIEW-SPEC). Not FAIL.

Practice on disk: 44 task specs = 44 check specs = 44 chapter files = T1 leaf ids `{1,2,3,4,5,9,6.1–6.27,7.1–7.4,8,10.1,10.2,13,11.1,12.1,14}`. T1 36 packages, 0 duplicate names; `storybook` → `non-goal:2`; shared 6.1 (2), 6.3 (2), 6.22 (5), 6.24 (2). T2 waves W1–W6 unique-cover all 44 leaves; slicing.md wave slice-id lists match. Generated trees named and not hand-authored SoT. Zero `.mdx` entries in allowed-paths (only `MUST NOT cite .mdx`). No `initial_spec.md`. README: How to use, empty Change history, 44 leaf rows once, parent indexes separate, no product MUST/SHALL.
