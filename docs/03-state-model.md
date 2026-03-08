# 03 — State Model (Phase 2 first official NKG slice)

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
- `phase` (`phase2` for this slice)
- `version`
- `createdAt`
- `updatedAt`
- `currentStage`
- `lastSuccessfulStage`

## `stages`
Includes Phase 1 stages plus one formal Phase 2 stage:
- `idea`
- `premise`
- `structure`
- `characters`
- `world`
- `chapterOutline`
- `nkgStyleTheme`

Each stage uses the same structure:
- `status` (`idle | running | ok | error`)
- `startedAt`
- `finishedAt`
- `requestId`
- `errorCode`
- `errorMessage`
- `retries`

## `project.themePipeline`
First-slice pipeline input/work area:
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

## `outputs.nkg` (official write target)
On successful pass 3, the first official non-empty NKG block is written to `AppState.outputs.nkg` with this structure:

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
Contains checkpoint, trace, and pass-level visibility:
- `checkpoints` (`cp_01..cp_05` + `cp_11..cp_15`)
- `trace`
- `lastError`
- `nkgStyleTheme`
  - `currentPhase`
  - `currentStage`
  - `lastSuccessfulStage`
  - `pass1`, `pass2`, `pass3` status snapshots
  - `requestIds`
  - `warnings`
  - `lastError`
