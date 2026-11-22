---
name: render-qa
description: Validate rendered educational video assets, frame sequences, captions, audio and export metadata before human approval. Use after code rendering or editing.
---

# Render QA

## Purpose
Provide deterministic checks and a reviewable visual/audio QA report. This skill does not replace human editorial review.

## Required inputs
- Content ID and approved storyboard/production plan.
- Rendered video file or frame sequence.
- Narration/audio master and caption/subtitle file.
- Expected aspect ratio, resolution, frame rate and duration.
- Asset manifest and claim/source map.

## Checks
### Structural
- All planned scenes exist and are in order.
- No missing frame/time ranges or unexpected black gaps.
- Scene durations sum to the expected runtime within configured tolerance.
- Scene boundaries and transitions match the approved plan.
- The export is decodable and contains the expected video/audio streams.

### Visual
- Brand palette and approved typography are respected.
- Captions and key text fit inside safe margins.
- No clipped labels, incorrect arrows, overlapping nodes or broken assets.
- Technical diagrams match the validated claim map.
- No unintended slide-like repetition or unexplained visual changes.
- Motion is purposeful; no accidental static/frozen sections or jarring discontinuities.
- Inspect opening, every scene boundary, representative mid-scene frames and end card using contact sheets.

### Audio and captions
- Voiceover is audible and intelligible.
- No clipping, abrupt cuts, accidental silence or excessive background music.
- Pronunciation of technical terms is checked.
- Captions align with spoken words and do not overlap or exceed safe areas.
- Narration and visuals do not contradict each other.

### Technical export
Use ffprobe/appropriate media inspection to record container and codec; width/height and aspect ratio; frame rate and frame count; duration; audio codec/sample rate/channel count; file size and decode errors. Compare the result with the export profile; do not assume an extension proves the codec.

### Rights and privacy
- Every third-party/generated asset has provenance and usage status.
- No unapproved creator footage, logos, copyrighted course slides or private account data.
- No API keys, tokens or secrets embedded in files or rendered frames.
- Required AI-generated-media disclosure has been considered.

## Output report
Create a QA report with content ID, export path, export hash if available; expected versus actual metadata; passed checks; blocker/major/minor findings tied to timestamp/frame; screenshots/contact-sheet paths; unresolved uncertainty; human reviewer and approval status.

## Rules
- Never mark QA passed if the file could not be inspected.
- Never infer technical correctness from visual polish.
- Never auto-publish.
- A QA pass is not editorial approval; final approval remains human.