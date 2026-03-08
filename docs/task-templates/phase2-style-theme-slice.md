# Phase 2 Style/Theme Slice Template

## Context
NKG has a stable Phase 1 foundation and is ready to start the first real Phase 2 NKG slice.

## Mission
Implement one bounded Phase 2 pipeline that takes:
- one reference author name,
- three sample style paragraphs,
- one desired setting/location,
and produces the first official non-empty NKG result in `AppState.outputs.nkg` through three passes:
1. style analysis
2. theme ideation
3. theme selection + normalization

## In scope
- Add/confirm inputs for reference author, three style samples, and desired setting.
- Build a 3-pass generation pipeline with explicit pass outputs.
- Write final normalized result to `AppState.outputs.nkg`.
- Add state/diagnostic visibility for each pass.
- Keep implementation constrained to this first Phase 2 slice only.

## Out of scope
- Any Bible generation work.
- Any export implementation.
- Any manuscript/chapter prose writing features.
- Full Phase 2 expansion beyond this initial style/theme slice.

## Hard constraints
- Do not imitate or mimic the named author literally.
- Convert author reference into an abstract style profile before theme work.
- Generate at least 5 candidate themes before selection.
- Penalize generic or repetitive theme candidates during ranking/selection.
- Fail loudly with diagnostics; never fail silently.

## Implementation model
- **Pass 1 — Style analysis**
  - Inputs: author name + 3 style paragraphs + setting.
  - Outputs: `styleProfile`, `targetNovelMode`.
  - Guardrail: explicit anti-imitation rule in pass output.
- **Pass 2 — Theme ideation**
  - Inputs: `styleProfile`, `targetNovelMode`, setting.
  - Output: ranked candidate themes (minimum 5).
  - Guardrail: detect and penalize generic/repetitive themes.
- **Pass 3 — Theme selection + normalization**
  - Inputs: candidate themes.
  - Outputs: `selectedThemeTitle`, `selectedThemeRationale`.
  - Final action: write official block into `AppState.outputs.nkg`.

## Required NKG block
Require `AppState.outputs.nkg` to match this structure:

```json
{
  "authorReference": "string",
  "styleSource": {
    "authorName": "string",
    "sampleParagraphs": ["string", "string", "string"],
    "settingIntent": "string"
  },
  "styleProfile": {
    "rhythm": "string",
    "sentenceLength": "string",
    "focalization": "string",
    "sensoryDensity": "string",
    "metaphorDensity": "string",
    "emotionalTemperature": "string",
    "actionVsReflection": "string",
    "narrativePressure": "string",
    "proseMode": "string"
  },
  "targetNovelMode": {
    "label": "string",
    "explanation": "string"
  },
  "themeExploration": {
    "candidates": [
      {
        "title": "string",
        "rationale": "string",
        "originalityScore": 0,
        "compatibilityScore": 0,
        "repetitionRisk": 0
      }
    ],
    "selectedThemeTitle": "string",
    "selectedThemeRationale": "string"
  }
}
```

## Theme quality rules
- Reject or down-rank themes that are vague, overused, or repetitive.
- Penalize candidates that are too similar to one another.
- Prefer themes with clear tension, specificity, and narrative usefulness.
- Require explicit rationale for why the selected theme won.

## Temperature strategy
- Pass 1 (style analysis): `temperature = 0.2`
- Pass 2 (theme ideation): `temperature = 0.9`
- Pass 3 (theme selection/normalization): `temperature = 0.35`
- Treat temperatures as fixed defaults for this slice unless a task explicitly overrides them.

## State and stage requirements
- Keep AppState top-level shape intact: `meta`, `stages`, `project`, `outputs`, `diagnostics`.
- Add clear stage/state transitions for all three passes.
- Expose pass-level diagnostics with actionable failure reasons.
- Ensure `AppState.outputs.nkg` is written only after successful pass sequencing and output validation.

## Validation requirements
- Verify required inputs exist (author + 3 paragraphs + setting) before pass 1.
- Verify pass order is enforced: 1 → 2 → 3.
- Verify candidate theme count is at least 5 before selection.
- Verify selected theme fields are non-empty.
- Verify the official `AppState.outputs.nkg` block is non-null and schema-conformant.

## Documentation updates required
- Document first-slice Phase 2 inputs and pass flow.
- Document NKG output block contract for this slice.
- Document temperature defaults and theme-quality rules.
- Document explicitly deferred work (later Phase 2 expansion, Bible, export).

## Suggested Phase 2 checkpoints
- `cp_11_nkg_input_ready`
- `cp_12_style_profile_generated`
- `cp_13_theme_candidates_generated`
- `cp_14_central_theme_selected`
- `cp_15_first_nkg_block_written`

## Success criteria
- Operator can run the slice with author + 3 paragraphs + setting.
- Pipeline runs all 3 passes in order with diagnostics.
- At least 5 candidate themes are generated and scored.
- Generic/repetitive and near-duplicate themes are penalized.
- Final selected theme is written in the richer official `AppState.outputs.nkg` structure.
- Work stops after this first Phase 2 slice.

## Deliverables
- Phase 2 style/theme first-slice implementation only.
- Updated docs for flow, state contract, diagnostics, and checkpoints.
- Clear deferred-work list for subsequent Phase 2 expansion.

## Final warning
This template is only for the first working Phase 2 NKG slice. Do not add Bible generation, export logic, or manuscript-writing features in this task.
