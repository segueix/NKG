# Phase 1 Smoke Checklist (Manual)

## Setup
- Open `index.html` directly in a browser.
- Confirm app title indicates Phase 1 shell only.

## Scope and UI
- [ ] UI lists exactly six stages: idea, premise, structure, characters, world, chapterOutline.
- [ ] No controls claim manuscript writing, NKG generation, Bible generation, or export.
- [ ] Checkpoint panel includes cp_01 through cp_05.

## State model
- [ ] State panel (or console dump) shows top-level keys only:
  - `meta`, `stages`, `project`, `outputs`, `diagnostics`
- [ ] `meta.currentStage` and `meta.lastSuccessfulStage` exist and are null or a valid stage id.
- [ ] `outputs.nkg` and `outputs.bible` are placeholders only.
- [ ] Every stage has status lifecycle fields and error fields.

## Stage runner
- [ ] Starting a stage sets status to `running` with `startedAt` and `requestId`, and updates `meta.currentStage`.
- [ ] Completing a stage sets status to `ok`, sets `finishedAt`, clears `meta.currentStage`, and sets `meta.lastSuccessfulStage`.
- [ ] Failing a stage sets status to `error` with `errorCode` and `errorMessage`, clears `meta.currentStage`, and updates `diagnostics.lastError`.
- [ ] Resetting a stage returns it to `idle` and clears runtime error fields.

## Diagnostics
- [ ] Diagnostic panel clearly shows current phase, current stage, last successful stage, checkpoint status, trace, and last error.
- [ ] Trace log updates on each stage action.
- [ ] Checkpoints re-evaluate when state changes.
- [ ] `cp_01_scope_clean` is computed, not hardcoded.
- [ ] `cp_05_phase1_shell_stable` is true only when cp_01..cp_04 are true and diagnostics shell data is present.

## Basic checkpoint shell
- [ ] “Build checkpoint payload” produces a structured JSON payload.
- [ ] Payload includes `checkpointId`, `phase`, `createdAt`, `appVersion`, and `appState`.
