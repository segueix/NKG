# NKG

NKG is a **single-file narrative project generator** focused on building a fiction project up to a stable pre-NKG checkpoint, then moving through controlled NKG slices.

## Product boundary
NKG currently supports stable Phase 1 foundation work and is prepared to begin the first real Phase 2 slice. It does **not**:
- write novel/chapter manuscript prose,
- generate Narrative Bible output,
- export project packages.

## Current implementation status
- Phase 1 foundation is closed and stable.
- First Phase 2 style/theme slice can generate and auto-display a primary readable document named **NKG projecte 1** from a simplified flow (author + 3 samples + short setting seed).
- Structured NKG output remains written to `AppState.outputs.nkg` for diagnostics and checkpoint tracking.

### Active foundation flow
`idea → premise → structure → characters → world → chapterOutline`

### Checkpoints
- Legacy Phase 1 visibility: `cp_01_scope_clean`, `cp_02_ui_phase1_only`, `cp_03_appstate_ready`, `cp_04_stage_runner_ready`, `cp_05_phase1_shell_stable`
- Planned first-slice Phase 2: `cp_11_nkg_input_ready`, `cp_12_style_profile_generated`, `cp_13_theme_candidates_generated`, `cp_14_central_theme_selected`, `cp_15_first_nkg_block_written`

## 3-phase plan (fixed)
1. **Phase 1 (closed):** pre-NKG functional foundation.
2. **Phase 2 (next):** NKG generation.
3. **Phase 3 (later):** Narrative Bible + export.

## Repository structure
- `index.html` — single-file app shell.
- `docs/` — scope, roadmap, checkpoints, state model, and review-system docs.
- `docs/review/` — reusable judging rubric and phase/slice review template.
- `docs/task-templates/` — reusable Codex task templates.
- `schemas/` — JSON schemas for state/checkpoint contracts.
- `fixtures/` — sample project seed.
- `tests/` — manual smoke checklists.

## Prompt operations for Codex
- Stable repository rules live in `AGENTS.md`.
- Reusable task prompts live in `docs/task-templates/`.
- `docs/current-task.md` is the temporary per-task working prompt file and is expected to be overwritten between tasks.

## First real Phase 2 slice target
The planned `nkgStyleTheme` task executes a 4-pass pipeline (style analysis → setting expansion → theme ideation → theme selection/normalization) and writes the first official non-empty block to `AppState.outputs.nkg`.
