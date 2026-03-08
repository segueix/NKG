# Phase Review Template

## Review context
- Review target: [branch/PR/commit]
- Requested phase/slice: [Phase 1 / Phase 2 slice / Phase 3 slice]
- Reviewer: [name]
- Date: [YYYY-MM-DD]

## Rule of review
Evaluate only against what this phase/slice is supposed to deliver now.
Do not require future-phase functionality.
Do not ignore scope creep or roadmap violations.

## Material to review
- Diff/changed files:
- Relevant docs:
- Relevant checkpoints/state schema:
- Validation/test evidence provided:

## Key questions
1. Scope fit: Is work exactly within requested phase/slice?
2. Roadmap coherence: Does sequencing match the fixed roadmap?
3. Architecture quality: Is logic clear, stable, and debuggable?
4. State/checkpoints: Are state transitions and checkpoints real, not hardcoded?
5. Diagnostics: Are failures explicit and localized?
6. Functional quality: Does claimed behavior work on valid inputs?
7. Documentation quality: Do docs match implementation and boundaries?
8. Regression risk: What prior behavior might break?
9. Next-step readiness: Is this cleanly ready for the next planned slice?

## Mandatory response format
### 1) Review target
[fill]

### 2) Phase/slice expectation
[fill]

### 3) Criterion scores (use rubric weights)
- Scope fit (15): [score] — [rationale]
- Roadmap coherence (10): [score] — [rationale]
- Architecture quality (15): [score] — [rationale]
- State and checkpoints (15): [score] — [rationale]
- Diagnostics and traceability (10): [score] — [rationale]
- Real functional quality (15): [score] — [rationale]
- Documentation quality (10): [score] — [rationale]
- Regression risk (5): [score] — [rationale]
- Readiness for next phase/slice (5): [score] — [rationale]

### 4) Total
- Raw total: [0-100]
- Normalized: [0.0-10.0]

### 5) Merge recommendation
[merge | merge-with-fixes | hold | reject]

### 6) Blocking issues
- [issue]

### 7) Non-blocking improvements
- [improvement]

### 8) Regression risk callout
- Risk level: [low | medium | high]
- Reason: [fill]

### 9) Next-phase readiness verdict
- Verdict: [ready | not-ready]
- Reason: [fill]
