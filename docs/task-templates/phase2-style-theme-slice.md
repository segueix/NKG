# Phase 2 Style/Theme Slice Template

## Context
NKG has a stable Phase 1 foundation. This task defines the first real Phase 2 NKG slice and stops after that slice is working.

## Mission
Implement one bounded Phase 2 pipeline that takes:
- one reference author name,
- three sample style paragraphs,
- one desired setting/location,
and produces an NKG result in `AppState.outputs.nkg` through three passes:
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
- Preserve Phase 1 behavior and existing checkpoints.
- Fail loudly with diagnostics; never fail silently.

## Implementation model
- **Pass 1 — Style analysis**
  - Inputs: author name + 3 style paragraphs + setting.
  - Output: abstract style profile (voice traits, rhythm, tone, motifs, constraints).
  - Guardrail: explicit anti-imitation rule in pass output.
- **Pass 2 — Theme ideation**
  - Input: abstract style profile + project context.
  - Output: ranked candidate theme list (minimum 5).
  - Guardrail: detect and penalize generic/repetitive themes.
- **Pass 3 — Theme selection + normalization**
  - Input: candidate themes + ranking signals.
  - Output: selected theme package normalized for downstream NKG usage.
  - Write result into `AppState.outputs.nkg`.

## Required NKG block
Require `AppState.outputs.nkg` to contain, at minimum:
- `inputs`: reference author, style samples, setting snapshot
- `styleProfile`: abstracted style analysis output
- `themeCandidates`: candidate themes with scores/notes (>=5)
- `selectedTheme`: winning normalized theme object
- `pipelineMeta`: pass statuses, timestamps, and diagnostic summary

## Theme quality rules
- Reject or down-rank themes that are vague, overused, or repetitive.
- Prefer themes with clear tension, narrative usefulness, and differentiation.
- Require a short rationale for each candidate score.
- Require explicit rationale for why the selected theme won.

## Temperature strategy
- Pass 1 (style analysis): `temperature = 0.2`
- Pass 2 (theme ideation): `temperature = 0.9`
- Pass 3 (theme selection/normalization): `temperature = 0.35`
- Treat temperatures as fixed defaults for this slice unless a task explicitly overrides them.

## State and stage requirements
- Keep Phase 1 state shape and behavior intact.
- Add clear StageRunner/state transitions for each of the three Phase 2 passes.
- Expose pass-level diagnostics in `diagnostics` with actionable failure reasons.
- Ensure `AppState.outputs.nkg` is written only after successful pass sequencing.

## Validation requirements
- Verify required inputs exist (author + 3 paragraphs + setting) before pass 1.
- Verify pass order is enforced: 1 → 2 → 3.
- Verify candidate theme count is at least 5 before selection.
- Verify selected theme is normalized and persisted to `AppState.outputs.nkg`.
- Verify generic/repetitive penalty logic is applied and traceable.

## Documentation updates required
- Document new Phase 2 slice inputs and pass flow.
- Document NKG output block contract for this slice.
- Document temperature defaults and quality/penalty rules.
- Document explicitly deferred work (later Phase 2 expansion, Bible, export).

## Suggested Phase 2 checkpoints
- `cp_06_phase2_inputs_ready`
- `cp_07_style_analysis_ready`
- `cp_08_theme_ideation_ready`
- `cp_09_theme_selection_normalized`
- `cp_10_nkg_output_written`

## Success criteria
- Operator can run the slice with author + 3 paragraphs + setting.
- Pipeline runs all 3 passes in order with diagnostics.
- At least 5 candidate themes are generated and scored.
- Generic/repetitive themes are explicitly penalized.
- Final normalized selection is written to `AppState.outputs.nkg`.
- Work stops after this first Phase 2 slice.

## Deliverables
- Phase 2 style/theme first-slice implementation only.
- Updated docs for flow, state contract, diagnostics, and checkpoints.
- Clear deferred-work list for subsequent Phase 2 expansion.

## Final warning
This template is only for the first working Phase 2 NKG slice. Do not add Bible generation, export logic, or manuscript-writing features in this task.
