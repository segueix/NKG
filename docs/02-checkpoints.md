# 02 — Checkpoints

## Phase 1 checkpoints (active)

### cp_01_scope_clean
- The shell enforces Phase 1-only scope.
- No manuscript writing, NKG generation, Bible generation, or export behavior is implemented.

### cp_02_ui_phase1_only
- UI exposes only the six Phase 1 stages:
  - idea, premise, structure, characters, world, chapterOutline.

### cp_03_appstate_ready
- AppState exists with top-level keys:
  - meta, stages, project, outputs, diagnostics.
- Stage state shape includes lifecycle/error fields.

### cp_04_stage_runner_ready
- A stage runner can start/complete/fail stage execution.
- Stage statuses are restricted to: idle | running | ok | error.

### cp_05_phase1_shell_stable
- All prior checkpoints pass.
- Shell supports consistent diagnostics and basic checkpoint shell payload generation.

## Future checkpoints (not implemented)

### Phase 2 (planned)
- cp_06_validation_depth
- cp_07_checkpoint_restore_hardening
- cp_08_cross_stage_consistency

### Phase 3 (planned)
- cp_09_nkg_generation_live
- cp_10_bible_generation_live
- cp_11_export_live
