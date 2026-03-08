# 02 — Checkpoints

## Phase 1 checkpoints (legacy visibility)
These remain visible for regression tracking from the original shell:
- `cp_01_scope_clean`
- `cp_02_ui_phase1_only`
- `cp_03_appstate_ready`
- `cp_04_stage_runner_ready`
- `cp_05_phase1_shell_stable`

## Phase 2 first-slice checkpoints (active)

### cp_11_nkg_input_ready
True only when all required first-slice inputs are non-empty:
- one reference author name
- exactly 3 non-empty sample paragraphs
- one non-empty desired setting/location

### cp_12_style_profile_generated
True only when Pass 1 succeeds and generates:
- complete `styleProfile` with all required fields
- non-empty `targetNovelMode.label`
- non-empty `targetNovelMode.explanation`

### cp_13_theme_candidates_generated
True only when Pass 2 succeeds and generates:
- at least 5 candidate themes
- scored candidates with `originalityScore`, `compatibilityScore`, and `repetitionRisk`

### cp_14_central_theme_selected
True only when Pass 3 succeeds and sets:
- non-empty `selectedThemeTitle`
- non-empty `selectedThemeRationale`

### cp_15_first_nkg_block_written
True only when the official first NKG block is written to `AppState.outputs.nkg` and passes output validation.

## Failure visibility requirements
Failures must identify where they occurred:
- style analysis pass
- theme ideation pass
- theme selection/normalization pass
- final official NKG write
