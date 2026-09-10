# 13 Performance

> **Spec chapter:** Retrospective performance contract for OpenCode, limited to what T0/T1 name.
> **Parent:** [README](../README.md)
> **Index:** [README.md](../README.md)

**File:** none. T1 package assignment has no row with `assigned` = `13` (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §2).

This pass is retrospective of shipped behavior (C8). T1 maps id `13` to this file with concern “Perf only if T0/later sources name it” (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §1 numbering table). Allowed inventory (`tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md`) does not name latency, throughput, memory, CPU, or other performance budgets, SLAs, or dedicated performance test suites.

T0 §7 cluster **13** is “Docs & marketing site — web”. T1 assigns that surface to leaf `6.27`, not this chapter (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §4: Product docs site → `6.27`). This file is the Part V performance leaf, not the docs-site package home.

## Construction / configuration

T0 does not list performance knobs, budgets, or env prefixes. T1 consistency token `env prefixes` is “none named in T0” (`tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` §7).

| Parameter | Default | Notes |
|-----------|---------|-------|
| *(none named)* | — | No performance construction parameters in `tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md` §§1–9 |

### Scope of this leaf

This leaf is not a first-party package cluster. Performance of individual packages, HTTP handlers, CLIs, and UIs is out of this chapter’s concern unless T0/T1 name a cross-cutting perf contract (they do not).

## Behavior

| Method / command | Behavior |
|------------------|----------|
| *(none named)* | T0 does not name performance commands, benchmarks, or SLAs (`tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md` §§2–6) |

T0 §8 Size records approximate `*.ts` / `*.tsx` / `*.go` file counts per package. Those counts are inventory size, not runtime performance requirements (`tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md` §8).

Turbo is named as the workspace task runner (`tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md` §2). T0 does not attach cache, timeout, or throughput SLAs to Turbo.

### Documented performance requirements

Allowed sources do not state numeric or qualitative runtime performance thresholds. This chapter records **no** shipped latency, throughput, or resource-limit contract.

## Error handling

T0 and T1 do not name performance-related errors, timeout SLAs, backpressure, or load-shedding.

### Named performance errors

| Error | Condition | Notes |
|-------|-----------|-------|
| *(none named)* | — | `tmp/executive/opencode-retrospective-spec/findings/T0-inventory.md`; `tmp/executive/opencode-retrospective-spec/findings/T1-chapter-map.md` |

## Open questions (stubs)

### OQ-13-1: Product-code performance tests or budgets
- **Tags:** `proj-spec/chapters/13-performance.md#documented-performance-requirements`
- **Discovered in:** retrospective chapter write (C10 slice budget)
- **Blocking:** none
- **Status:** open
- **Question:** Do first-party packages contain performance tests, benchmarks, or numeric budgets that T0/T1 did not name?

### OQ-13-2: Runtime performance configuration
- **Tags:** `proj-spec/chapters/13-performance.md#construction--configuration`
- **Discovered in:** retrospective chapter write (C10 slice budget)
- **Blocking:** none
- **Status:** open
- **Question:** Are there runtime env vars or config keys for performance that T0 did not inventory?

### OQ-13-3: Performance-related error and timeout behavior
- **Tags:** `proj-spec/chapters/13-performance.md#named-performance-errors`
- **Discovered in:** retrospective chapter write (C10 slice budget)
- **Blocking:** none
- **Status:** open
- **Question:** Do shipped surfaces emit performance-specific errors or timeouts not named in T0/T1?

## Verification

Verification is the **canonical index** for decision ↔ coverage (see workflow `#spec-anchor-format` Placement). One tag per line.

- Spec-Anchor: proj-spec/chapters/13-performance.md#construction--configuration
  tests: none found
- Spec-Anchor: proj-spec/chapters/13-performance.md#scope-of-this-leaf
  tests: none found
- Spec-Anchor: proj-spec/chapters/13-performance.md#behavior
  tests: none found
- Spec-Anchor: proj-spec/chapters/13-performance.md#documented-performance-requirements
  tests: none found
- Spec-Anchor: proj-spec/chapters/13-performance.md#error-handling
  tests: none found
- Spec-Anchor: proj-spec/chapters/13-performance.md#named-performance-errors
  tests: none found

## Related chapters

- [README](../README.md)
