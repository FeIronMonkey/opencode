# Review: R-slice-coverage — OpenCode
> **Verdict:** PASS
> **Reviewer model:** cursor-grok-4.6-medium
> **Implementer model:** cursor-grok-4.6-medium
> **Artifact reviewed:** T0/T1 assignment, leaf allowed-paths, chapter Related, non-workspace trees

## Blockers (must fix before progression)
- none

## Findings (non-blocking)
- T1 §3 still lists only `storybook` → `non-goal:2`. Extra-workspace trees are assigned in `02-goals.md` Non-goals plus OQ-02-3 through OQ-02-7, not in the T1 table.
- Inbox `OQ-T1-4` remains `open` with an empty Resolution, while `06.18-app.md` OQ-6.18-1 already points the desktop `AppInterface` host at 6.19. Coverage is assigned; the inbox copy is stale.
- `07.2-sdk-api.md` Construction still lists legacy `createOpencodeServer` hostname/port/timeout literals; spawn/interceptor MUSTs are linked to 6.8. Interface-companion overlap, not a second unlabeled home.
- `11.1-surfaces.md` still names example start commands (Vite/Astro ports, `scripts.dev`) beside per-surface canonical 6.x links. Product contracts (auth, error strings, sidecar stall) are pointer tables, not a second SoT.

## Checklist
- [x] C3: workspace packages ↔ T1 ↔ chapter files
- [x] Boundary pairs each have exactly one canonical chapter or OQ
- [x] Orphan pass outside packages/* is assigned or explicit non-goal/OQ
- [x] No silent dual-SoT overlap (C2)

## Re-verified part blockers (current text)

| Prior finding | Named gap | Current home | Status |
|---------------|-----------|--------------|--------|
| RSC-c3 | 36 packages / storybook | T1 §2 36 rows; `storybook` → `non-goal:2`; 44 leaf files | superseded (was already PASS) |
| RSC-b-cli | `HttpApiApp.createRoutes` | 6.1 `#httpapiapp-createroutes`; 6.5 disclaims it; 6.15 still defers `@opencode-ai/server` `createRoutes` | superseded |
| RSC-b-http | catalog / contract / handler dual SoT | 6.4 contract; 6.5 handlers; 7.1 index + Related 6.4/6.5/8 | superseded |
| RSC-b-sdk | client method/error catalog; C5 mapping | 7.2 catalog; 6.7 generated trees + `script/build.ts`; 10.2 commands | superseded |
| RSC-b-desktop | desktop `main`/packaging; `AppInterface` mount; app exports | 10.1 packaging; 6.19 runtime + mount; 6.18 exports | superseded |
| RSC-b-cloud | public share path | 6.21 `/s/{id}` public path; 6.27 origin `/docs/s/{id}`; 6.25 share HTTP + `url` uses 6.21 path | superseded |
| RSC-b-schema | 8 ↔ 7.1 event boundary; OQ-8-1 | Related both ways; OQ-8-1 is SDK Next beyond 7.1 HTTP unions | superseded |
| RSC-b-examples | 11.1 silent 6.x SoT | Construction/error rows name canonical 6.x; Related lists those leaves | superseded |
| RSC-b-test | `scripts.test` competing canonical | 12.1 SoT; 01/04/05/14 link 12.1 (05 no longer names 4) | superseded |
| RSC-b-install | `bin/opencode`, `lildax.cjs`, desktop packaging, uninstall/upgrade | 10.1 SoT; 6.1/6.15/6.19/7.3 link-only headings | superseded |
| RSC-orphan | `sdks/vscode`, `.vscode/`, `nix/`+flake, `sdks/`, localized README/`screenshot-uk.png`, `infra/`+SST/`github/` | `02-goals.md` non-goals + OQ-02-3…OQ-02-7 (`Blocking: none`) | superseded |

C5: generated client/SDK trees are marked generated; 7.1/6.4/6.7/7.2/10.2 do not treat generated files as behavioral SoT.

## Evidence
- Read: checker-base, slice-coverage-synthesis, constitution C2/C3/C5, tasks/checks RSC-synthesis, ledger T0 (36 packages; storybook → `non-goal:2`), `findings/T1-chapter-map.md` §§1–6, `findings/T0-inventory.md` §§2–4, all `findings/RSC-*.md` listed in the task, `proj-spec/open-questions.md` OQ-02-3…7 / OQ-8-1 / OQ-6.18-1 / OQ-T1-4
- Workspace: 36 `packages/**/package.json` names match T1 §2 (including nested console/stats and `packages/sdk/js`); unmatched set empty
- Chapters re-opened for named blockers: `06.1-agent-cli.md`, `06.4-protocol.md`, `06.5-server.md`, `06.7-client.md`, `06.15-cli.md`, `06.18-app.md`, `06.19-desktop.md`, `06.21-console-app.md`, `06.25-function.md`, `06.27-web.md`, `07.1-http-api.md`, `07.2-sdk-api.md`, `07.3-cli.md`, `08-domain-model.md`, `10.1-install.md`, `11.1-surfaces.md`, `01-overview.md`, `02-goals.md`, `04-stack.md`, `05-file-tree.md`, `12.1-workspace.md`, `14-acceptance.md`
- Hunt rows: C3 package/leaf/README set — pass; boundary canonical homes — pass; extra-workspace orphans — pass (non-goal + OQ); C2 silent dual SoT — pass (prior copies now declare a canonical chapter)
