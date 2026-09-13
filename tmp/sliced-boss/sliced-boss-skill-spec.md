# Skill spec — sliced-boss (companion to executive-agent)

Process documentation for a future Cursor skill. **Not** a product chapter. **Not** an installed `SKILL.md`. Canonical copy after session close: `tmp/sliced-boss/` (see §13).

Cite `executive-agent` clause ids **D2–D11** rather than restating them. This spec covers gaps that job `opencode-retrospective-spec` filled: inventory→map→bounded slices→waves; instruction packs; thin parameter files; synthesis re-verify; resume via ledger + `tmp/tasks.md`.

---

## 1. Purpose and when to use

**WHAT:** Staff a large body of work as a **sliced boss**: decompose into one-concern slices with allowed-path budgets, write shared instruction files once, dispatch thin per-slice parameter files, check each slice independently, then synthesize.

**WHEN:** The corpus (code, docs, reviews, migrations, audits, data, specs) cannot fit accurately in one agent context; slices can be mapped to independent write targets; the parent already (or will) run `@executive-agent`.

**Proposed `description:` (third person, WHAT + WHEN, trigger terms):**

> Slice large work into one-concern units with allowed-path budgets, shared instruction packs, thin per-task parameter files, independent checkers, and synthesis re-verify. Use when staffing a sliced boss, instruction-pack economy, write waves, inventory-then-map, or when one agent context cannot hold the whole corpus. Invoke with `@executive-agent`; do not replace boss/worker/checker, D6/D7/D8.

**Not only:** spec-driven repos, chapter files, or a named product. Same method applies to any slicable work (audit parts, API surface partitions, doc books, test packs, migration waves).

---

## 2. Relationship to `executive-agent`

**Decision: companion skill** that **MUST** invoke `@executive-agent` and only adds slicing + instruction-file economy.

| Option | Verdict |
|--------|---------|
| Extend `executive-agent` | Rejected |
| **Companion** | **Chosen** |
| Standalone | Rejected — would duplicate D2–D11 |

**Named criterion (why not extend):** **Trigger isolation + always-loaded SKILL.md budget.** `executive-agent` already loads D2–D11, SDD modes, and Task dispatch on every executive job (`executive-agent/SKILL.md` When to use, Phase flow). Slicing is **optional** even when D2–D11 apply (a three-task job needs no inventory/map/waves). Folding the pipeline, instruction-pack layout, wave file-locks, and synthesis re-verify into the base skill would either (a) auto-inject slicing vocabulary into small jobs via `description:` / SKILL body, or (b) hide the method in `reference.md` where it is not discoverable as a distinct WHEN. Companion keeps D-clauses in one skill and slicing triggers in another.

**Named criterion (why not standalone):** Standalone would restate D2–D11. Task constraint: do not replace D6/D7/D8.

**Non-goals**

| Must not | Lives in |
|----------|----------|
| Boss whitelist / authorship exception | D2, D11 |
| Boss model-tier recommendation | D3 |
| Constitution-first | D4 |
| Tiered model routing | D5 |
| Independent checks; no worker self-report; no accept “done” without PASS | D6 |
| Specific-findings retry, attempt bounds, disputes, dispositions | D7 |
| Final independent check of boss artifacts | D8 |
| Ledger + delegation report | D9 |
| SDD-integrated vs standalone paths; no edits to `spec-driven-*` | D10 |
| Boss loads verified summaries, not raw sources | D11 |

Companion **adds:** slice inventory/map/waves; one-concern + allowed-path; indexes after children; instruction pack on disk; thin prompts; part checkers then synthesis that **re-opens sources**; file-lock waves; spawn-many vs mega-context; resume via ledger + `tmp/tasks.md` (plus Task `resume` parent-mismatch → new Task).

---

## 3. Roles

| Role | Does | Does not |
|------|------|----------|
| **Boss** | Orchestrates: constitution (D4), task+check specs **before** dispatch (D6), instruction pack, inventory/map/wave plan, staffing, file-locks, ledger (D9), D7 rulings, integration. Loads indexes and verified summaries (D11). | Author deliverables except D2 whitelist or a **recorded authorship exception** (D11). Read every source or every child findings body. Accept worker “done” without checker PASS (except recorded D7 user/boss-override). |
| **Worker** | Writes only the named deliverable paths. Reads task spec + cited constitution clauses + allowed paths + named instruction overlays. | Edit constitution, task/check specs, ledger, other workers’ files. Claim PASS/FAIL. Roam outside allowed paths (file an OQ stub instead). |
| **Checker** | **Fresh** Task per check. Executes the check spec. Re-opens cited sources. Writes only a named findings path if the check spec allows it. | Receive worker self-report or chain-of-thought (D6). Trust prior PASS as this check. Edit deliverables (except the named findings path). |
| **Synthesis checker** | Fresh Task after **part** checkers. Writes the integrated artifact. **Re-verifies** blockers and cross-slice claims against sources. | Treat part findings as truth. Merge CoT. Skip FAIL parts. |

Boss model fit remains D3 (session model is the chat model). Writers/checkers: cheapest capable per D5; job-specific slug bans belong in the constitution or ledger, not this skill’s forever catalog.

---

## 4. Slicing method

Pipeline (generic names; OpenCode T0–T2/W1–W7 is an instance in §12):

```
Inventory → Map → Bounded slice specs → Write waves → Indexes/aggregates after children → Integrated review (parts + synthesis)
```

| Stage | Produce | Check |
|-------|---------|--------|
| **Inventory** | Condensed, citation-backed list of units (packages, surfaces, modules, doc trees, services). Size hints. Generated/do-not-hand-author roots. No prose of the final work product. | Set-compare names to the authoritative membership list. |
| **Map** | One row per planned artifact: id, path, kind (`leaf` \| `index`/`aggregate`), one-line concern. Assignment of every inventory unit to **exactly one** leaf or **explicit non-goal**. Related edges. Consistency tokens. **Write waves** of independent leaves. | Assignment complete; one concern per leaf; indexes marked not-yet-written. |
| **Bounded slice specs** | One **task spec** + one **check spec** per leaf (not per index). Each task lists `allowed-paths`, slice id, extra coverage rows. | Pair count = leaf count; no specs for index rows; every `allowed-paths` non-empty. |
| **Waves** | Dispatch only **independent** slices in parallel. Sequential when a slice depends on another’s PASS or shares a write target (file-lock). | Do not start wave N+1 until named predecessors PASS or D7 disposition. |
| **Indexes after children** | Parent summaries, READMEs, inboxes, rollups — **after** children exist. | Link coverage; index is not a second source of truth for child contracts. |
| **Integrated review** | Split the corpus into **parts**; spawn many part checkers; then a **fresh synthesis** checker. | Synthesis re-verifies; any confirmed part FAIL → overall FAIL. |

**One concern per slice.** Cross-cutting facts are **links** to a canonical slice, not a second unlabeled home. Tiny units may share a leaf only when they are one concern (say so on the map row).

**Allowed-path / context budget.** A worker reads only paths in its task spec plus **immediate imports** of those paths when required to resolve a cited symbol. No repo-wide dumps. If a needed fact is outside the set, write an **OQ stub** — do not expand scope.

**Parallelize only independent slices.** Independence = disjoint write targets and no “after X PASS” edge on the wave table.

**Spawn many, not mega-context.** Prefer several bounded reviewers over one agent that loads the whole map. If a checker reports context overflow, split the part and re-dispatch.

**Coverage hunt (generalized from slice-coverage, not product-specific):** after leaves exist, staff extra parts for (1) inventory↔map set-compare, (2) **boundary pairs** (two slices that could each treat a fact as the other’s job), (3) **orphans** outside the inventory membership list, (4) **silent dual source of truth**. Synthesis FAILs if an orphan or **hot-potato** gap is unassigned and not an explicit non-goal/OQ.

---

## 5. Instruction-pack layout

Repeatable text lives **on disk** under the job dir. The boss **MUST NOT** regenerate long prompts per agent.

**Job tree (standalone example):**

```
tmp/executive/<job-slug>/
  constitution.md
  ledger.md
  instructions/          # shared pack
    worker-base.md
    checker-base.md
    <wave-or-kind>-overlay.md
  tasks/                 # thin parameter files
  checks/
  findings/
```

| File | Audience | Contents |
|------|----------|----------|
| `worker-base.md` | Every worker | Role, allowed-path rule, do-not-edit list, output to boss (paths + OQ stubs, no self-grade). |
| `checker-base.md` | Every checker | Execute check spec; no worker narration; PASS/FAIL + specific findings; no-edit except named findings path. |
| Overlays | Kind of work | e.g. chapter-writer, part-reviewer, synthesis-writer. Parameters the **task spec** must supply. |
| Per-task file | One Task | Paths, slice id, extra coverage-checklist rows, deliverable path. Point at base + overlay by path — **do not paste them**. |

**Thin parameter example (structure):** a filled leaf task is a Parameters block (`slice-id`, `chapter-path`/`artifact-path`, `parent-path`, `allowed-paths` bullets, `related-ids`, tokens, flags) plus “Follow `instructions/<overlay>.md` and `worker-base.md`.” The paired check repeats those parameters and “Follow `checker-base.md` + overlay.” Source of this pattern: `instructions/chapter-task-template.md`, `chapter-check-template.md`, and filled pair `tasks/leaves/6.11.md` / `checks/leaves/6.11.md` (OpenCode instance; any domain uses the same shape).

**Boss prompt to Task:** role one-liner + paths to constitution excerpt, task spec, check spec (checkers), instruction files. No pasted instruction bodies. On D7 retry: attach **specific checker findings**, never “try again” (D7).

---

## 6. Sub-agent management (token-efficient)

| Rule | Why |
|------|-----|
| Checkers **never** receive worker self-reports or CoT (D6) | Independent execution |
| **Fresh checker** per check (new Task) | No contaminated context; HANDOFF / ledger staffing lesson |
| Synthesis **re-verifies** blockers; does not trust part reports | `slice-coverage-synthesis.md`, `slice-process-synthesis.md`, `review-spec-synthesis.md` |
| Resume via **ledger** + **`tmp/tasks.md`**, not chat history | D9; workflow `#resume-protocol` / `#tmp-tasks-close` as session scratch |
| Task `resume` cannot change model; new model ⇒ new Task | HANDOFF “Boss model / staffing” |
| Cross-session `resume` **parent mismatch** ⇒ **new** Task | Ledger: resume of `dc9a9626` failed; new worker `a8a5961d` |
| Cursor Task has **no `readonly` flag** in this harness | Instruct checkers not to edit except a named findings path (D6 intent). Do not document `readonly=true` as if the API exists. |
| Boss does not read every source or every findings body | D11; consume checker-verified summaries |

`tmp/tasks.md` is the **session** checklist (phase, wave, PASS ids). The ledger is the **job** record (models, verdicts, D7, exceptions). Do not reconstruct “done” from conversation.

---

## 7. Success factors (normative for the skill)

1. **Constitution-first (D4)** before any worker dispatch. Every task/check spec cites clauses it serves.
2. **Task spec + check spec before dispatch (D6).** No “just go write.”
3. **Do not accept “done” without checker PASS**, except recorded **D7** boss-override or user accept/drop/direct-rework.
4. **D7 retries carry specific findings** (path, missing claim, contradicted source) — never a bare retry.
5. **Checkers MUST NOT edit** deliverables, constitution, specs, or ledger except the **named findings/review path** in the check spec.
6. **Instruction files exist**; prompts are thin (see §5, §11).
7. **Spawn many bounded reviewers** rather than one mega-reviewer (HANDOFF “Suggested process”; `reviews/opencode-spec-r2.md` process finding: many part checkers, not one agent reading every chapter).
8. **Map covers inventory** (every unit assigned or explicit non-goal). Indexes after children when the map marks them as indexes.

---

## 8. Artifacts

| Artifact | Author | Children load? | Boss loads? |
|----------|--------|----------------|-------------|
| Constitution | Boss (D2) | Excerpt of cited clauses | Full (judgment) |
| Task specs / check specs | Boss (D2) | Own spec only | Full (author) |
| Instruction pack | Boss (or worker under a meta-task) | Named files only | Names + when editing pack |
| Ledger | Boss (D9) | No | Yes (resume) |
| `tmp/tasks.md` | Boss session | No | Yes (resume) |
| Inventory / map findings | Worker | Only if listed in allowed-paths | Checker-verified summary, not body-dump |
| Leaf / part deliverables | Worker | No (other slices) | No bodies (D11) |
| Part findings | Checker | Synthesis may **re-open** named blockers, not trust | Summaries / verdicts |
| Integrated review artifact | Synthesis checker | n/a | Verdict line + blockers |

---

## 9. Dispatch rules

1. **Staff by slice independence.** Parallel Task calls iff disjoint writes and no predecessor PASS edge.
2. **File-lock / sequential waves** when slices share a write target (ledger example: install+desktop queued until http-cli-fix). One writer per locked path.
3. **Part checkers, then synthesis.** Do not dispatch synthesis until parts have returned. Synthesis FAIL if any re-confirmed part FAIL.
4. **D7:** resume same worker Task when parent is valid; else new Task with findings attached. Escalation per D7 bounds.
5. **Integrated review is not one reader.** Split by map parts (example: REVIEW-SPEC Parts + IIIa/IIIb split — HANDOFF “Done”). Spawn more if overflow.
6. **After extra/process coverage reviews that change children:** re-run the integrated review; prior PASS is superseded (`reviews/opencode-spec-r2.md` supersession sentence).

---

## 10. Anti-patterns

| Anti-pattern | Instead |
|--------------|---------|
| Mega-reviewer loads the whole corpus | Spawn many part checkers + synthesis |
| Paste instruction text into every prompt | Paths to `instructions/` + thin parameters |
| Checker given worker CoT / “I verified…” | D6 attach list only |
| Boss authors leaf deliverables | D2 whitelist; exception recorded in ledger |
| Boss reads every source | D11 research-as-tasks |
| Accept worker “done” | Wait for checker PASS or recorded D7 |
| Reconstruct status from chat | Ledger + `tmp/tasks.md` |
| One-concern violations (same MUST in two leaves unlabeled) | Canonical link; coverage hunt |
| Hot-potato gaps (each slice assumes the other owns it) | Boundary-pair reviewers; assign or OQ/non-goal |
| Inventory orphans with no non-goal | Map assignment (C3-class completeness) |
| Indexes written before children | Wave: indexes last |
| Stale index/status as dual SoT | Index is navigation; do not treat stale “Next:” as a gate verdict (`reviews/opencode-slice-process.md`, `opencode-spec-r2.md` README Status findings) |
| Synthesis trusts part self-reports | Re-verify blockers |
| `resume` across sessions hoping the parent matches | New Task on parent mismatch |
| Treating one taxonomy (e.g. packages/chapters) as the only slice kinds | Inventory whatever units the job has |

---

## 11. Checkable done (“parent acted as a sliced boss”)

Observable; a checker can execute without worker narration:

| # | Pass condition |
|---|----------------|
| 1 | `instructions/` contains at least `worker-base` + `checker-base` (or named equivalents). Sampled Task prompts are path-thin (no full overlay paste). |
| 2 | Every map **leaf** has a paired task spec and check spec. Index rows do not have leaf specs. |
| 3 | Each check used a **fresh** checker Task id (ledger). Checker prompts omit worker self-reports. |
| 4 | Synthesis artifact **cites re-opened sources** for blockers/cross-slice claims (not “parts said PASS”). |
| 5 | Ledger records per-task worker model, checker model, verdicts, retries, final D7 disposition. |
| 6 | Map assignment set-equals inventory (unmatched empty) or unmatched items are explicit non-goals/OQs. |
| 7 | Wave table: indexes/aggregates scheduled after children; parallel groups are independent. |
| 8 | No accepted leaf without checker PASS unless ledger records D7 override/user decision. |
| 9 | Allowed-path lists exist per leaf; citations outside the list have OQ stubs. |

---

## 12. Optional scenario: spec-driven retrospective

Pointer only. **Do not fork** `spec-driven-*` skills (D10).

If the work is a **retrospective greenfield spec** of shipped code: `@spec-driven-workflow` `#retrospective-migration` (no reconstructed approvals, no `initial_spec.md`, do not demand code to match a prettier spec). Resume: `#resume-protocol` + `tmp/tasks.md` (scratch; `#tmp-tasks-close` is for REVIEW-FINAL, not this companion’s default close). Extra process/coverage reviews are **user-directed**, not a substitute for REVIEW-SPEC. Example instance: `proj-spec/slicing.md` pipeline T0→T1→T2→W1–W6 leaves→W7 indexes→REVIEW-SPEC; 44 leaves / 7 indexes as structure evidence in `proj-spec/README.md` tables + `proj-spec/chapters/*.md` **filenames** (44 chapter files).

---

## 13. Implementation notes

**This spec does not install a skill.** Do not write `~/.cursor/skills/` or edit `executive-agent` / `spec-driven-*` until a later task says so.

| Field | Value |
|-------|--------|
| Proposed `name` | `sliced-boss` (lowercase, hyphens; ≤64 chars) |
| `description` | §1 proposed string (WHAT+WHEN, third person, trigger terms) |
| `disable-model-invocation` | **Default `true`** (create-skill: explicit `@sliced-boss` / user ask). Omit later only if unique triggers should auto-load. |
| Scripts / hooks | **None.** Same as `executive-agent` (markdown only). Instruction packs are job files, not skill scripts. |
| Storage when implemented | Personal `~/.cursor/skills/sliced-boss/` or project `.cursor/skills/sliced-boss/` — never `~/.cursor/skills-cursor/` |

**Progressive disclosure** (create-skill: SKILL.md <500 lines; references one level deep):

```
sliced-boss/
  SKILL.md         # purpose, @executive-agent, pipeline, roles delta, success factors, anti-patterns short, checkable done, link to reference
  reference.md     # instruction-pack templates, thin task/check skeleton, wave/file-lock, synthesis rules, artifact table, optional SDD scenario
```

Do **not** copy D2–D11 into SKILL.md. Link: “Follow `@executive-agent`.” Keep SKILL.md under 500 lines; this spec’s §4–§11 belong mostly in `reference.md`.

---

## Citations

| Claim | Source |
|-------|--------|
| D2–D11, roles, Task dispatch | `~/.cursor/skills/executive-agent/SKILL.md` headings Roles through Context economy; `reference.md` templates |
| Frontmatter, <500 lines, WHAT+WHEN, progressive disclosure, `disable-model-invocation` | `~/.cursor/skills-cursor/create-skill/SKILL.md` SKILL.md Structure, Writing Effective Descriptions, Keep SKILL.md Under 500 Lines, Progressive Disclosure |
| Inventory→map→waves; indexes after children; one concern; allowed paths | `proj-spec/slicing.md` Pipeline, Slice rules, Write waves |
| Instruction files + parameters; spawn many; no chapter bodies for boss; resume parent-mismatch; no Task `readonly` | `proj-spec/HANDOFF.md` Original user goal, Boss model / staffing, Suggested process |
| Thin leaf parameters | `instructions/chapter-task-template.md`, `tasks/leaves/6.11.md`, `checks/leaves/6.11.md` |
| worker-base / checker-base / overlays | `instructions/worker-base.md`, `checker-base.md`, `chapter-writer.md`, `review-spec-part.md`, `extra-review-part.md`, `*-synthesis.md` |
| T0/T1/T2 objectives | `tasks/T0-inventory.md`, `T1-chapter-map.md`, `T2-leaf-specs.md` |
| Ledger: dispatch policy, resume mismatch, file-locks, D9 | `tmp/executive/opencode-retrospective-spec/ledger.md` Job meta, Pause/resume, Dispatch policy |
| Session resume checklist | `tmp/tasks.md` Session, Spec phase |
| Slice-process / coverage lessons | `reviews/opencode-slice-process.md`, `reviews/opencode-slice-coverage.md` |
| Many part checkers; stale README status | `reviews/opencode-spec-r2.md` Findings (non-blocking) Navigation/README Status |
| C10 slice budget; C2 one concern; C11 README index | `constitution.md` C2, C10, C11 |
| Optional SDD | `spec-driven-workflow/SKILL.md` Phase sequence; `reference.md` `#resume-protocol`, `#retrospective-migration`, `#tmp-tasks-close` |
| Map size / filenames (structure) | `proj-spec/README.md` Status + Part tables; `proj-spec/chapters/*.md` filenames (44 files; bodies unread) |

**OQ stubs:** none (all required facts were in the allowed-path set).
