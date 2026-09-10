# Review: REVIEW-SPEC — OpenCode (r2)
> **Verdict:** PASS
> **Reviewer model:** cursor-grok-4.6-medium
> **Implementer model:** cursor-grok-4.6-medium
> **Artifact reviewed:** proj-spec/chapters/* (current tree after R-slice-process and R-slice-coverage chapter fixes), proj-spec/README.md, proj-spec/14 path, proj-spec/open-questions.md, parent indexes

Retrospective greenfield (`#retrospective-migration`, C8). Scope: `#review-spec-scope-greenfield`. This-round part findings `RS-I.md`, `RS-II.md`, `RS-IIIa.md`, `RS-IIIb.md`, `RS-IV.md`, `RS-V.md`, `RS-VI.md` all Verdict PASS; blockers and whole-spec hunt re-verified independently. Prior `reviews/opencode-spec.md` PASS is superseded by this r2 artifact as the latest REVIEW-SPEC gate file.

## Blockers (must fix before progression)
- none

## Findings (non-blocking)
- **C2 (Part I):** Product one-liner, agents `build`/`plan`/`general`, install list, Desktop BETA, Building on OpenCode, and Storybook-as-non-goal remain restated in both `01-overview.md` and `02-goals.md` without a Related-chapters link naming a canonical leaf. Values agree. Duplicate OQs `OQ-1-1` and `OQ-02-1` ask the same `product` token question.
- **C2 / map metadata:** `06.2-core.md` T1 consumed-by list still omits 6.17 while Related chapters names 6.17. Map-edge only.
- **C4 format:** Several leaves put `tests: none found` on a following bullet rather than the same Spec-Anchor line (`09-design-decisions.md`, `08-domain-model.md`). Headings still have Spec-Anchor lines. `06.12-plugin.md` Verification is `tests: none found` on every heading while `OQ-6.12-1` tags only `#verification`. `12.1-workspace.md` Verification lines say `tests: none found` without OQ ids on those lines; OQ-12.1-1–4 exist with `Blocking: none`.
- **C4 complementary anchors:** `06.11-http-recorder.md` has two Spec-Anchor lines for `#error-handling` (named tests, then `tests: none found` for unused-interaction finalizer). Complementary, not opposing.
- **C7 inbox lag:** Chapter `07.3-cli.md` `OQ-7.3-2` is **resolved** (canonical 10.1); inbox `OQ-7.3-2` is still **open**. Inbox OQ-7.1-1/2/4/8 bodies still describe pre-rewrite 7.1 concerns. All remain `Blocking: none`.
- **C9 explained (OQ, Blocking none):** Non-production docs hostname `docs.dev.opencode.ai` (6.21) vs Astro `site` `https://${SST_STAGE}.opencode.ai` default `https://dev.opencode.ai` (6.27) — `OQ-6.21-19`. Stats public origin `stats.opencode.ai` / `stats.dev.opencode.ai` (6.21) vs 6.23 `baseUrl` `https://opencode.ai` + Vite `base` `/data/` — `OQ-6.23-12`. Product one-liner README vs `package.json` description — `OQ-1-1` / `OQ-02-1` / §14. App Vite port `3000` vs `AGENTS.md` `4444` — `OQ-11.1-3`.
- **C9 in-slice, labeled:** `OPENCODE_CHANNEL=latest` → `prod` in app `vite.js` and desktop electron-vite; electron-builder IIFE maps unset/other → `dev` (`06.19-desktop.md` `#release-channel`, `10.1-install.md` table). CLI yargs `--port` `0` vs SDK spawn `4096` vs listen fallback `4096` vs `lildax serve` scan from `4096` are labeled per surface (6.1, 6.8, 6.15, 7.3). `http://opencode.internal` (6.1 TUI) vs `http://opencode.local` (6.9) are different hosts. Session list default 50: Protocol description vs Server `DefaultSessionsLimit` agree as contract vs handler.
- **Navigation only:** `07-interface.md` lists §8 as a child; `08-domain-model.md` Parent is README; T1 parent→children is `7→7.1–7.4` only.
- **README Status line:** `proj-spec/README.md` Status (2026-09-10) still says W7/A2 complete and next REVIEW-SPEC. Explicitly not a gate verdict or reconstructed approval (C8). Stale relative to extra-review + this r2 re-run.

## Checklist
- [x] All chapters for the map exist
- [x] README index complete (C11)
- [x] Acceptance chapter present
- [x] No blocking open questions
- [x] No unexplained cross-chapter contradictions on shared tokens
- [x] No initial_spec.md / no reconstructed approvals
