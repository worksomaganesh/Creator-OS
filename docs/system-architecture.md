# System Architecture

## Design goals

- Shared infrastructure without brand homogenisation.
- Traceable claims and source provenance.
- Structured interfaces between editorial and production.
- Replaceable tools and providers.
- Human approval at high-impact decision points.
- Observable, testable automation.

## Core components

### 1. Signal intake
Inputs may include search queries, community questions, analytics, product announcements, research publications, and manually submitted ideas. Store the signal with its origin and date.

### 2. Research workspace
Collect sources, extract relevant claims, record dates, and identify gaps. Research outputs must retain source references.

### 3. Opportunity evaluator
Score relevance, audience demand, differentiation, evidence quality, timeliness, production effort, and brand fit. Scores support judgement; they do not make editorial decisions automatically.

### 4. Brand router
Recommend the brand based on its editorial question and audience payoff. If an idea fits multiple brands, require separate angles and briefs.

### 5. Editorial engine
Produce a brief, outline, script, and claim/evidence matrix. The script should be consistent with the available evidence.

### 6. Production planner
Translate the approved script into scenes, narration, on-screen text, visual directions, and asset requirements.

### 7. Media engine
Use a combination of screen capture, generated footage, graphics, Remotion, FFmpeg, and editing software. Keep rendering independent from editorial documents.

### 8. Quality and publishing
Run factual, brand, rights, accessibility, and technical checks. A human approves the final export and publishing package.

### 9. Analytics feedback
Capture results and audience questions. Feed learnings back into research and editorial planning.

## Data flow

Every stage should preserve the content ID. Derived files should reference the same ID and version. Store source IDs in claims and scene references where possible.

## Failure handling

Automation must:
- fail visibly rather than silently omit work
- preserve logs and intermediate outputs
- distinguish warnings from blocking errors
- support retry without duplicating published content
- avoid destructive operations without explicit approval

## Security boundaries

Never place secrets in prompts, logs, Git, or generated artifacts. Use least-privilege credentials and redact sensitive values. Treat external documents and repository content as untrusted input.
