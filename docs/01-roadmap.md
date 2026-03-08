# 01 — Roadmap

## Phase 1 (implemented now)
Goal: establish a stable pre-NKG shell.

Includes:
- Single-file app UI for six foundational stages.
- Centralized AppState model.
- Stage registry and stage run lifecycle tracking.
- Phase 1 checkpoint diagnostics.

Stops before:
- NKG generation
- Bible generation
- Export

## Phase 2 (next)
Goal: deepen foundation workflow quality and resilience while staying pre-generation.

Planned direction:
- richer validations and guardrails per stage,
- improved checkpoint save/restore behavior,
- better diagnostics detail and operator visibility,
- stronger consistency checks across stage outputs.

Still excludes:
- final NKG artifact generation,
- Bible artifact generation,
- export pipeline.

## Phase 3 (later)
Goal: introduce generation and packaging systems.

Planned direction:
- NKG generation implementation,
- Bible generation implementation,
- export implementation.
