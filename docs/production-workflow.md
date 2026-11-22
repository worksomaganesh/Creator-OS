# Production Workflow

## Creative-to-production handoff

The approved script becomes a structured production plan. Do not ask a renderer to infer editorial meaning from a loose paragraph.

A scene should specify:
- scene ID and order
- approximate duration and timing basis
- narration and caption/on-screen text
- visual concept, composition and continuity
- asset references and rights status
- animation, camera and transition direction
- source/claim references where applicable
- expected render method (code animation, generated footage, screen recording, or live-action asset)

The production plan is the contract between creative agents and deterministic rendering tools. If the script changes, re-check timing, captions and every dependent scene.

## Selected architecture

```text
Research brief + claim/source map
             |
             v
Approved narration/script
             |
             v
Storyboard + scene plan (JSON)
             |
             +-------------------------+
             |                         |
             v                         v
Voice recording / licensed TTS     Visual assets
             |                     /    |     \
             v                    /     |      \
Speech alignment + captions   SVG/Remotion  Google Flow  Screen capture
             |                    \     |      /
             +---------------------\----|-----/
                                    v
                         Deterministic renderer
                      (Remotion / HTML+GSAP as fit)
                                    |
                                    v
                             FFmpeg / ffprobe
                                    |
                                    v
                         Contact sheets + frame QA
                                    |
                                    v
                       DaVinci Resolve finishing
                                    |
                                    v
                        Export validation + approval
                                    |
                                    v
                         Platform publishing pack
```

## Tool roles

### Remotion — primary programmatic renderer

Use React/TypeScript compositions for repeatable educational scenes: typography, token flows, timelines, process diagrams, neural-network illustrations, charts, UI-like demonstrations, comparisons and chapter markers. Scene inputs must be data-driven and validated. Do not copy proprietary or non-commercial third-party templates.

### HTML/CSS/GSAP — quick motion prototype

Use one self-contained HTML composition when a scene is simpler to express in browser motion graphics. The Bang Motion reference demonstrates useful principles: one continuous visual world, purposeful camera movement, style brief before coding, explicit timeline control, frame-by-frame capture and no slide-deck fade pattern. Use our own visual language and assets.

### SVG / technical diagram layer

Choose a semantic pattern first (sequence, state machine, architecture, process, comparison, data flow, timeline, etc.), then choose its visual grammar. Each shape and connector must communicate something; remove decorative nodes and unnecessary connectors. Keep diagrams readable at mobile size and use brand-specific colour profiles.

### Google Flow — optional generated footage

Use only for a shot that benefits from generated motion or imagery. Flow is not required for every scene and must not replace explanatory diagrams. Check artefacts, continuity, factual depiction, prompt/reference rights, credit cost and generated-media disclosure requirements before use.

### Voice / narration

Keep narration as a separate, versioned asset. Use a consistent presenter voice (creator-recorded or a properly licensed TTS model). Record provider, model, voice ID, language, generation date and commercial-use permission in the asset manifest. Voice cloning requires explicit consent from the voice owner. Never assume a model's weights inherit the app's software licence.

### FFmpeg / ffprobe

Use for deterministic media operations: probing, transcoding, audio extraction, loudness/peak checks, resizing, audio mixing, concatenation, subtitle burn-in and automated validation. Validate commands on copies; never overwrite source media by default.

### DaVinci Resolve

Primary finishing editor for editorial assembly, pacing, audio mix, finishing and final export. The code renderer creates approved scenes and an intermediate master; Resolve remains the place for human editorial polish.

## Production stages and approval gates

1. **Research gate:** audience question, demand evidence, source map, claim list and uncertainties are explicit.
2. **Script gate:** one learning outcome, accurate explanation, source-backed claims, clear caveats, approved narration.
3. **Storyboard gate:** every scene has a visual purpose, duration, narration, screen text, transition and asset references.
4. **Voice gate:** pronunciation, pacing, pauses, consent and model licence checked; narration timing aligned.
5. **Visual pilot gate:** render the opening 5–10 seconds or first scene group; review typography, continuity, motion, contrast and pacing before rendering the full video.
6. **Render gate:** execute deterministic frame rendering; retain logs and render metadata.
7. **Frame/audio QA gate:** inspect overview and detailed contact sheets; listen to the full track; check text, caption timing, factual labels, scene transitions, audio clipping and output duration.
8. **Human approval gate:** final editor approves the exported master and platform package. AI-generated checks are advisory only.
9. **Publishing gate:** prepare native title/description/caption/cover/subtitles; publish manually or through explicitly approved official APIs.
10. **Learning gate:** record platform metrics and qualitative audience feedback; feed findings into the next research cycle.

## Automated quality checks

- Schema validation for the production plan.
- Scene durations are positive and the sum matches target runtime within tolerance.
- Each factual scene links to claim/source IDs.
- All required media files exist and pass ffprobe.
- Captions have valid time ranges, no unintended overlap and safe margins.
- Frame extraction covers the complete timeline without gaps.
- Contact sheets are generated for representative frames and every scene boundary.
- Verify output aspect ratio, dimensions, frame rate, codec and audio stream.
- No secret, private account data or unlicensed source media is included.
- Require human approval before publication.

## Media lifecycle

`brief → script → storyboard → voice/assets → create/capture → review → manifest → render → edit → export → QA → approve → archive`

Keep raw footage, generated clips, audio masters, proxies, caches and large exports in managed media storage, not regular Git history. Git stores schemas, code, small reference images where licensed, source metadata, scripts and documentation.

## Tool adoption notes

- `anything2explainer` is a strong architecture reference for research, narration timing, storyboard, code-rendered scenes and frame-level QC. Its toolkit is PolyForm Noncommercial: do not reuse its code or template for monetisable work without the author's prior written authorisation.
- `Bang Motion` (MIT) informs browser-motion rules and deterministic frame capture; use our own palette and design.
- `diagram-design` (MIT) informs semantic-pattern-first diagram selection; use a custom TECHENIGMASTUDIOS profile.
- `Vox Director` (MIT) informs staged asset production and review, but requires a separate Atlas Cloud API key; do not make it a dependency.
- `VoiceStudio` is AGPL-3.0 and individual model weights have separate licences. Its default OmniVoice weights are described by the project as non-commercial; verify each model before any monetised use.
- `OpenCreator` (Apache-2.0) is a possible future Codex-native workspace, but would duplicate much of Creator-OS until a specific runtime gap is demonstrated.

## Export checks

Confirm correct resolution, frame rate, aspect ratio, codec, audio peak/loudness targets, caption synchronisation, safe margins, file integrity and platform-specific constraints before delivery.
