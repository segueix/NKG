# Phase 2 First Slice Smoke Checklist (Manual)

## Setup
- Open `index.html` in a browser.
- Confirm `nkgStyleTheme` stage is present.

## Input validation
- [ ] Empty author fails pass 1 with explicit error.
- [ ] Empty style sample text fails pass 1 with explicit error.
- [ ] Empty setting seed fails pass 1 with explicit error.

## 4-pass pipeline
- [ ] Pass 1 writes a complete non-empty `styleProfile` and `targetNovelMode`.
- [ ] Pass 2 runs only after pass 1 and yields a complete `settingProfile`.
- [ ] Pass 3 runs only after pass 2 and yields at least 5 scored candidate themes.
- [ ] Pass 4 selects one best candidate and writes `selectedThemeTitle` + `selectedThemeRationale`.
- [ ] Stage runner button executes pass1 → pass2 → pass3 → pass4 in order.

## Official NKG output write
- [ ] Successful pass 4 writes a non-null `AppState.outputs.nkg`.
- [ ] `outputs.nkg` includes `authorReference`, `styleSource`, `styleProfile`, `settingProfile`, `targetNovelMode`, and `themeExploration`.
- [ ] `styleSource` includes `authorName`, `sampleText`, and `settingSeed`.
- [ ] Candidate entries include `title`, `rationale`, `originalityScore`, `compatibilityScore`, `repetitionRisk`.

## Main document rendering
- [ ] After generation, `NKG projecte 1` auto-renders without extra user action.
- [ ] Document includes author reference, style sample summary, setting seed, expanded setting profile, style profile, target novel mode, candidate themes, selected theme, and rationale.

## Diagnostics and failure visibility
- [ ] Diagnostics panel shows current phase, current stage, and last successful stage.
- [ ] Diagnostics panel shows pass1/pass2/pass3/pass4 status + requestIds.
- [ ] Warnings appear for high candidate similarity and generic selected themes.
- [ ] Last error clearly identifies failed pass or final write failure.

## Temperature strategy
- [ ] `styleAnalysis` temperature is visible as `0.2`.
- [ ] `settingExpansion` temperature is visible as `0.55`.
- [ ] `themeIdeation` temperature is visible as `0.9`.
- [ ] `themeSelection` temperature is visible as `0.35`.

## Checkpoints
- [ ] `cp_11_nkg_input_ready` flips true only with valid inputs.
- [ ] `cp_12_style_profile_generated` flips true after successful pass 1.
- [ ] `cp_13_setting_profile_generated` flips true after successful pass 2.
- [ ] `cp_14_theme_candidates_generated` flips true after successful pass 3.
- [ ] `cp_15_central_theme_selected_and_nkg_written` flips true only when pass 4 succeeds and `outputs.nkg` is valid.
