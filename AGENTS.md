# AGENTS.md — NKG repository instructions

## Mission
Build and maintain NKG as a single-file narrative project generator that supports fiction project foundation work up to a stable pre-NKG checkpoint, then controlled Phase 2 expansion.

## Product roadmap (fixed)
- Phase 1: pre-NKG functional foundation.
- Phase 2: NKG generation.
- Phase 3: Narrative Bible + export.

## Scope (current)
- Phase 1 is closed and must remain stable:
  - `idea`
  - `premise`
  - `structure`
  - `characters`
  - `world`
  - `chapterOutline`
- Repository is ready to start the **first real Phase 2 slice** (`nkgStyleTheme`) for NKG generation.
- Preserve clear state handling and diagnostics while beginning Phase 2 in bounded slices.

## Hard constraints
- Keep the app as a single `index.html` file.
- Do not add frameworks.
- Do not add build tooling.
- Do not add dependencies unless absolutely necessary.
- Prioritize debuggability and traceability.
- Keep rendering logic separated from business/state logic.
- Avoid scattered mutable globals.
- Avoid direct business-logic coupling to DOM shape when avoidable.
- Never allow silent failures.

## Out of scope until later phases
- Full/unbounded NKG generation beyond the current planned slice.
- Bible generation (real implementation)
- Export implementation
- Manuscript/chapter prose writing features

## Forbidden regressions
- Introducing manuscript writing functionality.
- Breaking the defined AppState top-level shape:
  - `meta`, `stages`, `project`, `outputs`, `diagnostics`
- Removing checkpoint visibility for:
  - `cp_01_scope_clean`
  - `cp_02_ui_phase1_only`
  - `cp_03_appstate_ready`
  - `cp_04_stage_runner_ready`
  - `cp_05_phase1_shell_stable`

## Expected output style for future agents
- Keep code sections explicit and readable.
- Use clear naming and comments for architecture boundaries.
- Document any behavior changes in `docs/`.
- If a feature is not implemented by scope, expose it as a placeholder and mark clearly as not implemented.

## Prompt governance
- `AGENTS.md` is reserved for stable, long-lived repository instructions.
- Reusable task prompts must live in `docs/task-templates/`.
- The active working prompt may be copied/adapted in `docs/current-task.md`.
- Temporary task prompts should not be permanently embedded in `AGENTS.md`.
