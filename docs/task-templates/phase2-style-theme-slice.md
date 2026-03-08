# Phase 2 Style/Theme Slice Template

## Context
Phase 2 begins with the first real NKG slice, while preserving established Phase 1 behavior and avoiding Phase 3 scope.

## Mission
Implement the first NKG slice using: author reference + 3 style paragraphs + setting, then a 3-pass flow: style analysis → theme ideation → theme selection.

## In scope
- Add inputs for author reference, three style paragraphs, and setting context.
- Implement pass 1: style analysis output from provided style inputs.
- Implement pass 2: theme ideation based on style analysis + project context.
- Implement pass 3: theme selection with explicit chosen theme artifact.
- Add diagnostics and state traceability for each pass.

## Out of scope
- Full NKG expansion beyond this first slice.
- Narrative Bible generation.
- Export implementation.
- Manuscript/chapter prose writing.

## Hard constraints
- Keep architecture debuggable and traceable.
- Maintain clear separation between rendering and business/state logic.
- Avoid silent failure paths; report pass-level errors and statuses.
- Do not regress Phase 1 stage behavior or checkpoint visibility.
- Keep roadmap unchanged (Phase 2 slice only, no Phase 3 work).

## Success criteria
- User can provide author reference + 3 style paragraphs + setting.
- System runs style analysis, then theme ideation, then theme selection in order.
- Each pass emits inspectable state/diagnostic artifacts.
- Existing Phase 1 workflow remains functional.

## Deliverables
- Minimal, testable implementation for this first Phase 2 slice.
- Updated docs describing inputs, pass flow, and diagnostics.
- Clear note of what is intentionally deferred to later Phase 2 tasks.
