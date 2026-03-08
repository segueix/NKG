# NKG

NKG is a **single-file narrative project generator** focused on building a fiction project up to a stable **pre-NKG checkpoint**.

## Product boundary
NKG currently supports only pre-generation foundation work. It does **not**:
- write novel/chapter manuscript prose,
- generate NKG output,
- generate Bible output,
- export project packages.

## Current implementation status
This repository currently implements **Phase 1 only**.

### Phase 1 visible flow
`idea → premise → structure → characters → world → chapter outline`

### Phase 1 checkpoints
- `cp_01_scope_clean`
- `cp_02_ui_phase1_only`
- `cp_03_appstate_ready`
- `cp_04_stage_runner_ready`
- `cp_05_phase1_shell_stable`

## 3-phase plan (high level)
1. **Phase 1 (current):** shell + app state + stage runner + diagnostics for pre-NKG foundation.
2. **Phase 2 (future):** deepen phase-1 workflow behavior and checkpoint quality without generating final NKG/Bible artifacts.
3. **Phase 3 (future):** implement NKG generation, Bible generation, and export systems.

## Repository structure
- `index.html` — single-file app shell.
- `docs/` — scope, roadmap, checkpoints, and state model docs.
- `schemas/` — JSON schemas for phase-1 app state and checkpoint payloads.
- `fixtures/` — sample phase-1 project seed.
- `tests/` — manual smoke checklist for phase-1 shell verification.
