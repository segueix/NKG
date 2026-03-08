# Phase 3 Bible Generation Template

## Context
Phase 2 NKG output is considered stable enough to begin Narrative Bible generation planning/implementation.

## Mission
Implement Narrative Bible generation on top of stable NKG outputs, without conflating this phase with manuscript writing or unrelated feature growth.

## In scope
- Define and implement Bible-generation inputs derived from NKG outputs.
- Generate structured Bible sections/artifacts with traceable source links.
- Add diagnostics for Bible generation stages and validation checks.
- Document Bible data shape, assumptions, and operator workflow.

## Out of scope
- Manuscript/chapter prose writing functionality.
- Unrelated UI overhauls or roadmap changes.
- Scope unrelated to Bible generation and its direct prerequisites.

## Hard constraints
- Keep generation steps auditable and explicit.
- Preserve compatibility with prior phase state contracts where required.
- Prevent silent degradation when source NKG data is incomplete.
- Keep implementation bounded to Phase 3 Bible objectives.

## Success criteria
- Bible generation executes from stable NKG inputs with clear stage status.
- Output artifacts are structured, inspectable, and reproducible.
- Failure modes are explicit with actionable diagnostics.
- Phase boundaries are respected (no manuscript-writing expansion).

## Deliverables
- Phase 3 Bible generation implementation increment.
- Updated docs for Bible flow, state, diagnostics, and constraints.
- Explicit list of remaining Phase 3 follow-up work.
