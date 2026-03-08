# 02 — Checkpoints

## Phase 1 checkpoints (active)

### cp_01_scope_clean
True only when the runtime remains in strict Phase 1 boundary:
- `meta.phase === "phase1"`
- Exactly the six Phase 1 stage IDs are active
- Outputs remain placeholders (`outputs.nkg === null` and `outputs.bible === null`)
- Trace messages do not indicate manuscript/prose-writing behavior

### cp_02_ui_phase1_only
True only when rendered UI stage cards exactly match these IDs in order:
- `idea, premise, structure, characters, world, chapterOutline`

### cp_03_appstate_ready
True only when centralized AppState is coherent:
- Top-level keys are exactly: `meta`, `stages`, `project`, `outputs`, `diagnostics`
- `meta` includes `currentStage` and `lastSuccessfulStage`
- Every stage entry includes all required lifecycle/error fields and allowed status values

### cp_04_stage_runner_ready
True only when stage runner wiring is present and consistent:
- Stage registry is valid and matches the active six Phase 1 stage IDs
- Stage runner functions exist (`run`, `complete`, `fail`, `reset` paths)
- Runtime stage states obey status/retries shape requirements

### cp_05_phase1_shell_stable
True only when:
- cp_01 through cp_04 are true,
- diagnostics structures are present (checkpoint map + trace array), and
- Phase 1 UI snapshot is available for checkpoint evaluation.

## Later phases (not implemented yet)
- Phase 2: NKG generation
- Phase 3: Narrative Bible + export
