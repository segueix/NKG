# NKG Judge Rubric

## Purpose
Use this rubric to evaluate a branch, phase closeout, or major slice with a stable and repeatable standard.

## Core rule of judgment
Judge each submission only against the intended target for that phase/slice.
- Do not penalize missing future-phase features.
- Do penalize scope creep, roadmap violations, and unstable foundations.

## Roadmap fit rule
- Phase 1 reviews focus on pre-NKG foundation quality.
- Phase 2 reviews focus on NKG generation slices.
- Phase 3 reviews focus on Bible + export work after NKG stabilization.

## Scoring scale and merge guidance
- **9.0–10.0 (Excellent):** merge when checks pass.
- **8.0–8.9 (Strong):** merge with minor follow-up notes.
- **7.0–7.9 (Borderline):** hold unless critical fixes are applied.
- **6.0–6.9 (Weak):** do not merge; requires meaningful rework.
- **< 6.0 (Fail):** reject for this phase target.

## Weighted criteria (100 points total)
1. **Scope fit (15)**
   - Matches requested phase/slice scope exactly.
   - No out-of-scope features introduced.
2. **Roadmap coherence (10)**
   - Aligns with fixed 3-phase roadmap sequencing.
3. **Architecture quality (15)**
   - Keeps clear logic/render separation and debuggable structure.
4. **State and checkpoints (15)**
   - State shape is coherent; checkpoint logic is real and reliable.
5. **Diagnostics and traceability (10)**
   - Failures are visible, localized, and actionable.
6. **Real functional quality (15)**
   - Claimed behavior actually works for valid inputs.
7. **Documentation quality (10)**
   - Docs reflect implementation, limits, and operator usage.
8. **Regression risk (5)**
   - Low risk of breaking prior stable flows.
9. **Readiness for next phase/slice (5)**
   - Current work leaves a clean handoff for next planned step.

## Serious failure conditions (heavy penalties)
Apply strong score reductions if any occur:
- Phase/roadmap violation (implementing later-phase features early).
- Silent failures or unclear error paths.
- Broken or incoherent `AppState` top-level contract.
- Checkpoint success hardcoded instead of state-derived.
- Claimed output not actually written to official state target.
- Documentation contradicts real behavior.

## Mandatory review output format
Every review must return:
1. **Review target** (branch/PR/phase/slice)
2. **Phase/slice expectation**
3. **Scores by criterion** (raw points + short rationale)
4. **Total score (0–100) and normalized score (0–10)**
5. **Merge recommendation** (`merge`, `merge-with-fixes`, `hold`, `reject`)
6. **Blocking issues** (must-fix before merge)
7. **Non-blocking improvements** (next pass)
8. **Regression risk callout** (low/medium/high + why)
9. **Next-phase readiness verdict** (ready/not-ready + why)
