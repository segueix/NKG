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
`idea → premise → structure → characters → world → chapterOutline`

### Phase 1 checkpoints
- `cp_01_scope_clean`
- `cp_02_ui_phase1_only`
- `cp_03_appstate_ready`
- `cp_04_stage_runner_ready`
- `cp_05_phase1_shell_stable`

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
