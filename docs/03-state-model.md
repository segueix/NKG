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

## `outputs`
Placeholders only in Phase 1:
- `nkg` (placeholder)
- `bible` (placeholder)

## `diagnostics`
Checkpoint and trace information.
- `checkpoints`: status map for cp_01..cp_05
- `trace`: recent events
- `lastError`: latest error snapshot if any
