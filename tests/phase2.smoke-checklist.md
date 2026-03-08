# Phase 2 First Slice Smoke Checklist (Manual)

## Setup
- Open `index.html` in a browser.
- Confirm `nkgStyleTheme` stage is present.

## Input validation
- [ ] Empty author fails pass 1 with explicit error.
- [ ] Any empty sample paragraph fails pass 1 with explicit error.
- [ ] Empty setting fails pass 1 with explicit error.

## 3-pass pipeline
- [ ] Pass 1 writes a complete non-empty `styleProfile` and `targetNovelMode`.
- [ ] Pass 2 runs only after pass 1 and yields at least 5 candidate themes.
- [ ] Pass 3 runs only after pass 2 and sets `selectedThemeTitle` + `selectedThemeRationale`.
- [ ] Stage runner button executes pass1 → pass2 → pass3 in order.

## Official NKG output write
- [ ] Successful pass 3 writes a non-null `AppState.outputs.nkg`.
- [ ] `outputs.nkg` includes `authorReference`, `styleSource`, `styleProfile`, `targetNovelMode`, and `themeExploration`.
- [ ] Candidate entries include `title`, `rationale`, `originalityScore`, `compatibilityScore`, `repetitionRisk`.

## Diagnostics and failure visibility
- [ ] Diagnostics panel shows current phase, current stage, last successful stage.
- [ ] Diagnostics panel shows pass1/pass2/pass3 status + requestIds.
- [ ] Warnings appear for high candidate similarity and generic selected themes.
- [ ] Last error clearly identifies failed pass or final write failure.

## Temperature strategy
- [ ] `styleAnalysis` temperature is visible as `0.2`.
- [ ] `themeIdeation` temperature is visible as `0.9`.
- [ ] `themeSelection` temperature is visible as `0.35`.

## Checkpoints
- [ ] `cp_11_nkg_input_ready` flips true only with valid inputs.
- [ ] `cp_12_style_profile_generated` flips true after successful pass 1.
- [ ] `cp_13_theme_candidates_generated` flips true after successful pass 2.
- [ ] `cp_14_central_theme_selected` flips true after successful pass 3 selection.
- [ ] `cp_15_first_nkg_block_written` flips true only when `outputs.nkg` is valid and non-null.
