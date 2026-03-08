# NKG

NKG is a **single-file narrative project generator** focused on building a fiction project up to a stable **pre-NKG checkpoint**.

## Product boundary
NKG currently supports only pre-generation foundation work. It does **not**:
- write novel/chapter manuscript prose,
- generate NKG output,
- generate Bible output,
- export project packages.

## Current implementation status
This repository includes a stable Phase 1 foundation plus the **first official Phase 2 NKG style/theme slice**.

### Active flow
`idea → premise → structure → characters → world → chapterOutline → nkgStyleTheme`

### Checkpoints
- Legacy Phase 1 visibility: `cp_01`..`cp_05`
- Active first-slice Phase 2: `cp_11_nkg_input_ready`, `cp_12_style_profile_generated`, `cp_13_theme_candidates_generated`, `cp_14_central_theme_selected`, `cp_15_first_nkg_block_written`

## 3-phase plan (fixed)
1. **Phase 1 (current):** pre-NKG functional foundation.
2. **Phase 2 (future):** NKG generation.
3. **Phase 3 (future):** Narrative Bible + export.

## Repository structure
- `index.html` — single-file app shell.
- `docs/` — scope, roadmap, checkpoints, and state model docs.
- `schemas/` — JSON schemas for phase-1 app state and checkpoint payloads.
- `fixtures/` — sample phase-1 project seed.
- `tests/` — manual smoke checklist for phase-1 shell verification.

## Prompt operations for Codex
- Stable repository rules live in `AGENTS.md`.
- Reusable task prompts live in `docs/task-templates/`.
- `docs/current-task.md` is the temporary per-task working prompt file and is expected to be overwritten between tasks.


## First official Phase 2 slice
The `nkgStyleTheme` stage executes a 3-pass pipeline (style analysis → theme ideation → theme selection/normalization) and writes the first official non-empty block to `AppState.outputs.nkg`.
