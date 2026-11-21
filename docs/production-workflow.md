# Production Workflow

## Creative-to-production handoff

The approved script becomes a structured production plan. Do not ask a renderer to infer editorial meaning from a loose paragraph.

A scene should specify:
- scene ID and order
- approximate duration
- narration
- on-screen text
- visual concept and composition
- asset references
- animation or transition direction
- source/claim references where applicable

## Tool roles

### DaVinci Resolve
Primary editor for timeline assembly, pacing, colour, audio mixing, finishing, and final export.

### Remotion
Candidate engine for reusable animated typography, diagrams, charts, UI-like sequences, maps, and programmatic scenes. Use when structured, repeatable motion is valuable.

### Google Flow
Candidate for generated supporting footage and visual scenes. Generated media must be checked for continuity, factual representation, artefacts, and rights/usage constraints.

### FFmpeg
Useful for deterministic media operations: probing, transcoding, audio extraction, resizing, normalisation, concatenation, and automated validation. Validate commands on copies before batch processing.

## Media lifecycle

`brief → asset request → create/capture → review → manifest → edit → export → QA → archive`

Keep raw footage, generated clips, audio masters, proxies, caches, and large exports in managed media storage, not regular Git history.

## Export checks

Confirm correct resolution, frame rate, aspect ratio, codec, audio peak/loudness targets, caption synchronisation, safe margins, and platform-specific file constraints before delivery.
