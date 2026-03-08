# 02 — Checkpoints

## Phase 1 checkpoints (legacy visibility)
These remain visible for regression tracking from the closed foundation shell:
- `cp_01_scope_clean`
- `cp_02_ui_phase1_only`
- `cp_03_appstate_ready`
- `cp_04_stage_runner_ready`
- `cp_05_phase1_shell_stable`

## Phase 2 first-slice checkpoints (planned sequence)
Use this sequence for the first real `nkgStyleTheme` slice:

### cp_11_nkg_input_ready
True only when all required first-slice inputs are non-empty:
- one reference author name
- one non-empty style sample text
- one non-empty setting/location seed

### cp_12_style_profile_generated
True only when Pass 1 succeeds and generates:
- complete `styleProfile` with all required fields
- non-empty `targetNovelMode.label`
- non-empty `targetNovelMode.explanation`

### cp_13_setting_profile_generated
True only when Pass 2 succeeds and generates:
- complete `settingProfile` with all required fields

### cp_14_theme_candidates_generated
True only when Pass 3 succeeds and generates:
- at least 5 candidate themes
- scored candidates with `originalityScore`, `compatibilityScore`, and `repetitionRisk`

### cp_15_central_theme_selected_and_nkg_written
True only when Pass 4 succeeds and sets:
- non-empty `selectedThemeTitle`
- non-empty `selectedThemeRationale`
- successful official write to `AppState.outputs.nkg` passing output validation

## Failure visibility requirements
Failures must identify where they occurred:
- style analysis pass
- setting expansion pass
- theme ideation pass
- theme selection/normalization pass
- final official NKG write
