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
- [ ] `outputs.nkg` and `outputs.bible` are placeholders only.
- [ ] Every stage has status lifecycle fields and error fields.

## Stage runner
- [ ] Starting a stage sets status to `running` with `startedAt` and `requestId`.
- [ ] Completing a stage sets status to `ok` and `finishedAt`.
- [ ] Failing a stage sets status to `error` with `errorCode` and `errorMessage`.
- [ ] Resetting a stage returns it to `idle` and clears runtime error fields.

## Diagnostics
- [ ] Trace log updates on each stage action.
- [ ] Checkpoints re-evaluate when state changes.
- [ ] `cp_05_phase1_shell_stable` is true only when cp_01..cp_04 are true.

## Basic checkpoint shell
- [ ] “Build checkpoint payload” produces a structured JSON payload.
- [ ] Payload includes `checkpointId`, `phase`, `createdAt`, `appVersion`, and `appState`.
