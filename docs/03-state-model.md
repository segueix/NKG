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
Pipeline input/work area:
- `config.temperatures`
  - `styleAnalysis` = `0.2`
  - `settingExpansion` = `0.55`
  - `themeIdeation` = `0.9`
  - `themeSelection` = `0.35`
- `authorReference`
- `styleSampleText`
- `settingSeed`
- `pass1`
  - `state`
  - `styleProfile`
  - `targetNovelMode`
- `pass2`
  - `state`
  - `settingProfile`
- `pass3`
  - `state`
  - `candidateThemes`
- `pass4`
  - `state`
  - `selectedThemeTitle`
  - `selectedThemeRationale`

## `outputs.nkg` (first official write target)

```json
{
  "authorReference": "string",
  "styleSource": {
    "authorName": "string",
    "sampleText": "string",
    "settingSeed": "string"
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
  "settingProfile": {
    "environmentType": "string",
    "geographicTone": "string",
    "climateMood": "string",
    "socialTexture": "string",
    "institutionalPresence": "string",
    "publicVsPrivateTension": "string",
    "recurringAtmosphericMotifs": ["string"],
    "fitRationale": "string"
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
Required visibility for the first Phase 2 slice:
- `checkpoints` (`cp_01..cp_05` + `cp_11..cp_15`)
- `trace`
- `lastError`
- `nkgStyleTheme`
  - `currentPhase`
  - `currentStage`
  - `pass1`, `pass2`, `pass3`, `pass4` status snapshots
  - `requestIds`
  - `warnings`
  - `lastError`
