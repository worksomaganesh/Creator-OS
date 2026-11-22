---
name: visual-explainer-producer
description: Turn an approved, source-backed educational script into a structured scene plan for a faceless visual explainer, then coordinate a deterministic renderer and frame-level quality review. Use for educational Shorts, Reels, and long-form explainers. Do not publish automatically.
---

# Visual Explainer Producer

## Purpose
Convert an approved educational brief into a renderer-ready production plan. The skill coordinates research, narration, scene design, visual assets, motion, rendering and QA. It is provider-agnostic: use available approved models/tools, and never assume a specific subscription or API.

## Inputs
- Approved content brief and stable content ID.
- Source register and claim-to-source map.
- Approved narration/script and target duration.
- Brand adapter, visual identity and platform target.
- Available asset providers, renderer, voice and editing tools.
- Production-plan schema.

## Non-negotiable rules
1. Research facts before scripting; every material claim must map to a source/claim ID.
2. Never let the renderer invent educational content or technical labels.
3. One scene should communicate one visual beat, not become a static slide.
4. Visuals must clarify the concept: show entities, relationships, transformations, sequence, scale, evidence or contrast.
5. Preserve one coherent visual world and brand system, but vary composition and camera language when the story changes.
6. Do not use generic stock/AI footage when a diagram, screen recording or original animation teaches the idea better.
7. AI-generated footage is optional. A valid production plan must still be renderable when generated footage is omitted.
8. Keep assets and narration rights documented. Voice cloning requires explicit consent.
9. Respect provider quotas and costs; show estimated usage before generation when available.
10. Do not publish, schedule, or interact with social accounts. Human approval is mandatory.

## Workflow
### 1. Validate the creative brief
Confirm content ID, brand, audience, audience question, learning outcome, target duration, platform, source set, format and editorial status. Stop if the content is not approved or claims are unsupported.

### 2. Define the narrative spine
Write an opening tension/question, minimum context, causal/mechanistic explanation, concrete example or demonstration, important limitation/caveat, and final takeaway. Do not force a hook that exaggerates the evidence. Short-form content may be split into a sequence when compression would become inaccurate.

### 3. Draft narration
Write natural spoken language. Estimate duration from actual voice pace, not a generic word-count assumption. Include pronunciations for uncommon technical terms and mark pauses/emphasis where useful.

### 4. Storyboard the visual argument
For each scene define scene ID/order/start/end time; narration and caption text; learning beat and visual purpose; primary subject and action; spatial composition and camera movement; transitions and continuity; brand palette, type roles and safe areas; required assets, source/claim IDs and asset rights; accessibility notes.
Prefer continuous transformations, camera movement, labelled diagrams, real interface recordings and kinetic typography. Avoid repeated title-card layouts and slide-like fade sequences.

### 5. Create a structured production plan
Output valid JSON matching the configured production-plan schema. Include an explicit renderer mode for each scene: remotion, html-gsap, screen-recording, generated-footage, or editorial-footage. Include fallbacks for provider-specific assets and do not invent URLs or asset IDs.

### 6. Generate a pilot
Render the first 5–10 seconds or first representative scene group. Produce a contact sheet and a short preview. Ask for human approval of brand identity, typography/mobile readability, motion language/pacing, narration/audio and diagram correctness. Do not render the full episode until the pilot is accepted.

### 7. Render deterministically
Render exact timeline timestamps/frame numbers. Prefer deterministic code scenes for diagrams, typography and repeatable motion. Use frame-accurate capture rather than real-time screen recording when exporting code-driven animation. Keep logs, render configuration and asset manifests.

### 8. Quality assurance
Check scene coverage and timeline continuity; source/claim references; technical accuracy of text, labels, diagrams and examples; caption alignment and mobile safe areas; contrast, typography and accessibility; animation continuity, dropped frames and broken assets; audio clipping/loudness/pauses/pronunciation; duration/dimensions/frame rate/aspect ratio/codec/output integrity; rights and privacy.
Generate representative stills/contact sheets, not just an overall MP4 preview. Any blocker must be fixed before approval.

### 9. Human handoff
Deliver research/claim map, final narration, storyboard, production JSON, asset manifest, render log, QA report, preview and final master path. Mark the item review until a person approves it. Never claim a file was rendered unless the render process actually completed and its output was checked.

## Output status
Use Creator-OS lifecycle states. A generated script or plan is not a completed video. A rendered video is not approved until human review and QA pass.