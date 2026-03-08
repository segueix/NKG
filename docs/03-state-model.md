# 03 — State Model (target contract for first Phase 2 slice)

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
Operational metadata:
- `appName`
- `phase`
- `version`
- `createdAt`
- `updatedAt`
- `currentStage`
- `lastSuccessfulStage`

## `stages`
Baseline includes Phase 1 stages and may add a formal Phase 2 stage (`nkgStyleTheme`) for the first real slice:
- `idea`
- `premise`
- `structure`
- `characters`
- `world`
- `chapterOutline`
- `nkgStyleTheme` (first-slice target stage)

Each stage uses the same structure:
- `status` (`idle | running | ok | error`)
- `startedAt`
- `finishedAt`
- `requestId`
- `errorCode`
- `errorMessage`
- `retries`

## `project.themePipeline` (first-slice target shape)
Planned pipeline input/work area:
- `config.temperatures`
  - `styleAnalysis` = `0.2`
  - `themeIdeation` = `0.9`
  - `themeSelection` = `0.35`
- `authorReference`
- `sampleParagraphs` (exactly 3)
- `desiredSetting`
- `selectedThemeIndex`
- `pass1`
  - `state`
  - `styleProfile`
  - `targetNovelMode`
- `pass2`
  - `state`
  - `candidateThemes`
- `pass3`
  - `state`
  - `selectedThemeTitle`
  - `selectedThemeRationale`

## `outputs.nkg` (first official write target)
For the first real Phase 2 slice, successful pass 3 should write this richer structure to `AppState.outputs.nkg`:

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

## `diagnostics`
Recommended visibility for the first Phase 2 slice:
- `checkpoints` (`cp_01..cp_05` + `cp_11..cp_15`)
- `trace`
- `lastError`
- optional stage-specific diagnostics for `nkgStyleTheme`
