# Phase 1 Closeout Template

## Context
NKG is in Phase 1 (pre-NKG foundation) and must remain a single-file app (`index.html`) with clear checkpoints, diagnostics, and stable state handling.

## Mission
Close and stabilize Phase 1 without starting Phase 2 work.

## In scope
- Finalize or harden Phase 1 stages: `idea`, `premise`, `structure`, `characters`, `world`, `chapterOutline`.
- Improve Phase 1 state/diagnostic reliability and checkpoint visibility.
- Fix Phase 1 bugs, gaps, and UX issues that block stable checkpoint completion.
- Update docs that describe Phase 1 behavior and constraints.

## Out of scope
- Any real NKG generation implementation.
- Any Narrative Bible generation implementation.
- Any export implementation.
- Any manuscript/chapter prose writing features.
- Any scope expansion beyond Phase 1 foundations.

## Hard constraints
- Keep app architecture in a single `index.html` file.
- Do not add frameworks or build tooling.
- Keep business/state logic decoupled from DOM specifics where possible.
- Preserve AppState top-level shape: `meta`, `stages`, `project`, `outputs`, `diagnostics`.
- Never introduce silent failures; surface diagnostics explicitly.

## Success criteria
- Phase 1 flow runs cleanly end-to-end.
- Checkpoints remain visible and accurate:
  - `cp_01_scope_clean`
  - `cp_02_ui_phase1_only`
  - `cp_03_appstate_ready`
  - `cp_04_stage_runner_ready`
  - `cp_05_phase1_shell_stable`
- No Phase 2/3 functionality is added.

## Deliverables
- Focused Phase 1 code changes only.
- Updated docs for changed Phase 1 behavior.
- Concise summary of what was stabilized and what remains deferred.
