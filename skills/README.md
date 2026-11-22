# Agent Skills

Skills are focused instructions for repeatable tasks. Each defines purpose, inputs, outputs, process, constraints and quality checks. Skills can be invoked by compatible agent hosts; they must not assume a particular model or provider unless their metadata says so.

## Available skills

- `topic-researcher/` — turn an audience question into a traceable research brief.
- `brand-router/` — route an editorial question to the correct brand.
- `scriptwriter/` — produce a sourced script for a defined audience and outcome.
- `fact-checker/` — verify material claims and label uncertainty.
- `storyboard-planner/` — turn an approved script into scenes.
- `visual-explainer-producer/` — coordinate a code-rendered educational explainer from a validated brief and production plan.
- `technical-diagram-designer/` — select and specify a semantic diagram that fits the lesson and brand adapter.
- `publishing-auditor/` — validate the final publishing package and human approval state.

## Skill rules

- Use the brand adapter and its repository as the source of brand-specific identity.
- Never invent evidence, sources, performance metrics or tool execution.
- Keep claims traceable to source IDs.
- Do not copy third-party code, templates, visual expression, scripts or media without licence/permission review.
- Return reviewable files and state uncertainty.
- Never publish, schedule, follow, like, comment, DM or scrape accounts autonomously.
- Require human approval at the defined gates.
