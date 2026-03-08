# 03 — State Model (Phase 1)

## AppState top-level shape
```json
{
  "meta": {},
  "stages": {},
  "project": {},
  "outputs": {},
  "diagnostics": {}
}
```

## `meta`
Operational metadata for the running shell.
- `appName`
- `phase`
- `version`
- `createdAt`
- `updatedAt`
- `currentStage` (`stageId|null`)
- `lastSuccessfulStage` (`stageId|null`)

## `stages`
Dictionary keyed by stage id:
- `idea`
- `premise`
- `structure`
- `characters`
- `world`
- `chapterOutline`

Each stage object tracks:
- `status` (`idle | running | ok | error`)
- `startedAt` (`string|null`)
- `finishedAt` (`string|null`)
- `requestId` (`string|null`)
- `errorCode` (`string|null`)
- `errorMessage` (`string|null`)
- `retries` (`number`)

## `project`
Phase 1 narrative foundation payload.
- `idea`
- `premise`
- `structure`
- `characters`
- `world`
- `chapterOutline`
- `themePipeline` (explicit 3-pass foundation helper)

### `project.themePipeline`
A structurally visible and diagnosable pre-NKG helper pipeline:

- `authorReference`
- `sampleParagraphs` (exactly 3 inputs)
- `desiredSetting`
- `selectedThemeIndex`
- `pass1`
  - `state` (`status`, `lastRunAt`, `requestId`, `errorCode`, `errorMessage`)
  - `styleProfile`
  - `targetNovelMode`
- `pass2`
  - `state`
  - `candidateThemes` (at least 5 candidates on success)
- `pass3`
  - `state`
  - `selectedThemeTitle`
  - `selectedThemeRationale`
  - `finalNkgWrite` (Phase 1 placeholder write-up, not full NKG generation)

Pass dependencies are enforced in order:
1. Pass 1 — style analysis
2. Pass 2 — theme ideation
3. Pass 3 — theme selection and normalization

## `outputs`
Placeholders only in Phase 1:
- `nkg` (placeholder)
- `bible` (placeholder)

## `diagnostics`
Checkpoint and trace information.
- `checkpoints`: status map for cp_01..cp_05
- `trace`: recent events
- `lastError`: latest error snapshot if any
