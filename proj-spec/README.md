# OpenCode Specification — Chapter Index

Retrospective spec of **shipped** behavior on the `production` checkout. Not a redesign. Process: [slicing.md](slicing.md). Successor prompt: [HANDOFF.md](HANDOFF.md).

## How to use these chapters

- Read §1–§3 before writing product code (those leaves are not all written yet).
- Implement §6 in dependency order once those leaves exist and REVIEW-SPEC has passed **and** the user has approved the spec gate.
- Validate with §12 and §14 when those files exist.
- This index is incomplete until W7. Missing map leaves are listed in [slicing.md](slicing.md).

## Change history

| Topic | Spec | Plan | Log |
|-------|------|------|-----|
| *(none yet)* | | | |

## Status (2026-09-09)

W2 of 7 complete (6.4, 6.10). Checker **PASS**: §8, 6.3, 6.4, 6.6, 6.8, 6.10, 6.11, 6.12, 6.13, 6.16, 6.19, 6.22, 6.25, 6.27. W3 remaining (not yet PASS): 6.7, 6.2, 6.24. C11: this README is index-only until W7 (parent indexes, full README, `open-questions.md`).

**Return path:** `@spec-driven-greenfield-spec` / A1 / **W3**. Dispatch chapter writers for 6.7, 6.2, 6.24 (`cursor-grok-4.6-medium`; fresh checker per leaf). Do not start W4–W7. Do not expand this README to full C11. Do not start REVIEW-SPEC.

## Part I — Product Definition

| Chapter | Title | Status |
|---------|-------|--------|
| 1 | Overview | not written |
| 2 | Goals and non-goals | not written |

## Part II — Design

| Chapter | Title | Status |
|---------|-------|--------|
| 3 | Architecture | not written |
| 4 | Stack | not written |
| 5 | File tree | not written |
| 9 | Design decisions | not written |

## Part III — Components

Parent index `06-components.md` is W7.

| Chapter | Title | Status |
|---------|-------|--------|
| [6.3](chapters/06.3-sqlite-adapters.md) | SQLite adapters | PASS |
| [6.4](chapters/06.4-protocol.md) | Protocol | PASS |
| [6.6](chapters/06.6-httpapi-codegen.md) | HTTP API codegen | PASS |
| [6.8](chapters/06.8-sdk.md) | Legacy SDK | PASS |
| [6.10](chapters/06.10-llm.md) | LLM | PASS |
| [6.11](chapters/06.11-http-recorder.md) | HTTP recorder | PASS |
| [6.12](chapters/06.12-plugin.md) | Plugin | PASS |
| [6.13](chapters/06.13-codemode.md) | CodeMode | PASS |
| [6.16](chapters/06.16-ui.md) | UI kit | PASS |
| [6.19](chapters/06.19-desktop.md) | Desktop | PASS |
| [6.22](chapters/06.22-console-platform.md) | Console platform | PASS |
| [6.25](chapters/06.25-function.md) | Function worker | PASS |
| [6.27](chapters/06.27-web.md) | Web / docs site | PASS |
| 6.1–6.2, 6.5, 6.7, 6.9, 6.14–6.15, 6.17–6.18, 6.20–6.21, 6.23–6.24, 6.26 | *(see slicing waves W3–W5)* | not written |

## Part IV — Interface

| Chapter | Title | Status |
|---------|-------|--------|
| [8](chapters/08-domain-model.md) | Domain model (schema) | PASS |
| 7.x | External API | not written |

## Part V — Operations

| Chapter | Title | Status |
|---------|-------|--------|
| 10.x, 13 | Install, generate, performance | not written |

## Part VI — Validation

| Chapter | Title | Status |
|---------|-------|--------|
| 11.x, 12.x, 14 | Examples, testing, acceptance | not written |
