# Phase 2 NKG Expansion Template

## Context
The first Phase 2 slice exists. Additional NKG capabilities now need controlled expansion without introducing Phase 3 features.

## Mission
Expand NKG generation scope incrementally after the initial style/theme slice, while keeping architecture stable and observable.

## In scope
- Extend NKG inputs, processing passes, or output structure in small, verifiable increments.
- Improve Phase 2 state transitions, diagnostics, and failure reporting.
- Refine orchestration between Phase 1 outputs and Phase 2 generation steps.
- Document each new Phase 2 capability and its boundaries.

## Out of scope
- Narrative Bible generation features.
- Export pipeline implementation.
- Manuscript/chapter prose writing tools.
- Large unbounded rewrites that reduce debuggability.

## Hard constraints
- Preserve single-file app constraints unless explicitly changed by maintainers.
- Keep business/state logic distinct from UI rendering logic.
- Do not break existing Phase 1 behavior.
- Maintain explicit diagnostics for every added Phase 2 step.
- Keep roadmap sequencing intact: Phase 2 work only.

## Success criteria
- New Phase 2 capability works end-to-end with inspectable state.
- Added paths fail loudly and clearly when inputs are invalid.
- Documentation clearly states what was added and what remains deferred.
- No accidental Bible/export/manuscript scope is introduced.

## Deliverables
- Incremental Phase 2 implementation changes.
- Matching docs updates for new flow/state/diagnostics.
- Brief deferred-work list for the next expansion task.
