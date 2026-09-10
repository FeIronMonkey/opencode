# Review: REVIEW-SPEC — OpenCode
> **Verdict:** PASS
> **Reviewer model:** cursor-grok-4.6-medium
> **Implementer model:** cursor-grok-4.6-medium
> **Artifact reviewed:** proj-spec/chapters/*, proj-spec/README.md, proj-spec/14 path, proj-spec/open-questions.md, parent indexes

Retrospective greenfield (`#retrospective-migration`, C8). Scope: `#review-spec-scope-greenfield`. Part findings RS-I, RS-II, RS-IIIa, RS-IIIb, RS-IV, RS-V, RS-VI all Verdict PASS; re-verified blockers and cross-part C9 samples independently.

## Blockers (must fix before progression)
- none

## Findings (non-blocking)
- **C2 (Part I):** Product one-liner, agents `build`/`plan`/`general`, install list, Desktop BETA, Building on OpenCode, and Storybook-as-non-goal are restated in both `01-overview.md` and `02-goals.md` without a Related-chapters link naming a canonical leaf. Values agree. Duplicate OQs `OQ-1-1` and `OQ-02-1` ask the same `product` token question.
- **C2 (slice):** `01-overview.md` Error handling specifies root `scripts.test` echo + exit `1` (sourced in `package.json`; canonical home is `12.1-workspace.md` / §14).
- **C2 / map metadata:** `06.2-core.md` Runtime dependency direction cites T1 consumed-by `6.5, 6.9, 6.14, 6.15, 6.18, 6.20`, while Related chapters also names 6.17. T1 §6 both omits 6.17 from the 6.2 consumed-by row and lists `6.17 depends 6.2`. Map-edge only.
- **C4 format:** Several leaves put `tests: none found` on a following bullet rather than the same Spec-Anchor line (`09-design-decisions.md`, `08-domain-model.md`). Headings still have Spec-Anchor lines. `06.12-plugin.md` Verification is `tests: none found` on every heading while `OQ-6.12-1` tags only `#verification`.
- **C4 complementary anchors:** `06.11-http-recorder.md` has two Spec-Anchor lines for `#error-handling` (named tests, then `tests: none found` for unused-interaction finalizer). Complementary, not opposing.
- **C5 wording:** `06.22-console-platform.md` says `Generated-in-slice: no` while naming drizzle-kit `out` `./migrations/`; schema `*.sql.ts` is cited as intent, not migration SQL as SoT (contrast 6.24).
- **C9 explained (OQ, Blocking none):** Non-production docs hostname `docs.dev.opencode.ai` (6.21) vs Astro `site` `https://${SST_STAGE}.opencode.ai` default `https://dev.opencode.ai` (6.27) — `OQ-6.21-19`. Stats public origin `stats.opencode.ai` / `stats.dev.opencode.ai` (6.21) vs 6.23 `baseUrl` `https://opencode.ai` + Vite `base` `/data/` — `OQ-6.23-12`. Product one-liner README vs `package.json` description — `OQ-1-1` / `OQ-02-1` / §14. App Vite port `3000` vs `AGENTS.md` `4444` — `OQ-11.1-3`.
- **C9 in-slice, labeled:** `OPENCODE_CHANNEL=latest` → `prod` in app `vite.js` and desktop electron-vite; electron-builder IIFE maps `latest`/other → `dev` (`06.19-desktop.md` `#release-channel`, `10.1-install.md` table). CLI yargs `--port` `0` vs SDK spawn `4096` vs listen fallback `4096` vs `lildax serve` scan from `4096` are labeled per surface (6.1, 6.8, 6.15, 7.3). `http://opencode.internal` (6.1 TUI) vs `http://opencode.local` (6.9) are different hosts. Session list default 50: Protocol description vs Server `DefaultSessionsLimit` agree as contract vs handler. Interrupt: Core domain no-op vs HTTP `SessionNotFoundError` via session-location middleware (6.5/6.9) — different layers.
- **Navigation only:** `07-interface.md` lists §8 as a child; `08-domain-model.md` Parent is README; T1 parent→children is `7→7.1–7.4` only. `OQ-8-1` is stale relative to `07.1-http-api.md` `/api/event` (`EventManifest.ServerDefinitions` + `server.connected` variant). 6.21 Related omits 6.20 (`/t` proxy) and 6.19 (`#desktop-downloads`); 6.19 Related omits 6.18 despite hosting `@opencode-ai/app`.
- **Incomplete error path (not a false claim):** `07.1-http-api.md` Authentication documents missing `:` → empty credentials; `decodeCredential` also uses `emptyCredential()` on Base64 decode failure. Construction row `webHandler` omits `() => HttpRouter.toWebHandler(...)`.
- **README drift (sourced, not invented):** Overview cites README screenshot `packages/web/src/assets/lander/screenshot.png`; file is absent from the tree.
- **README Status line:** `proj-spec/README.md` Status (2026-09-10) records W7/A2 complete and next REVIEW-SPEC. Explicitly not a gate verdict or reconstructed approval (C8).

## Checklist
- [x] All chapters for the map exist
- [x] README index complete (C11)
- [x] Acceptance chapter present
- [x] No blocking open questions
- [x] No unexplained cross-chapter contradictions on shared tokens
- [x] No initial_spec.md / no reconstructed approvals
