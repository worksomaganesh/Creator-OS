# Creator OS

> A shared, AI-assisted operating system for researching, planning, producing, publishing, and improving high-quality content across independent creator brands.

**Creator OS is the shared infrastructure. The brands remain independent.**

This repository is the central operating layer for the three content brands:

- [TECHENIGMASTUDIOS](https://github.com/worksomaganesh/techenigmastudios) — technology and AI education.
- [AI That Works](https://github.com/worksomaganesh/aithatworks) — practical AI implementations and useful workflows.
- [ContextAhead](https://github.com/worksomaganesh/contxtahead) — technology intelligence, context, and implications.

The purpose is not to generate the maximum number of posts. It is to build a repeatable system that helps produce distinctive, researched, accurate, visually strong content—with human editorial control.

---

## 1. Why Creator OS exists

Running three independent brands creates repeated operational work: research, ideation, scripting, source tracking, storyboarding, asset management, editing preparation, publishing, and analytics.

Building three separate automation systems would duplicate effort and create inconsistent processes. Creator OS centralises reusable capabilities while allowing each brand to retain its own:

- audience and positioning
- editorial questions and content pillars
- voice, visual identity, and storytelling
- research standards and approval rules
- content backlog and publishing decisions

A shared engine must never make the brands sound or look identical. Reuse the machinery, not the editorial identity.

## 2. Vision

Build an AI-assisted content production system with a clear handoff from research to finished media:

1. Discover audience questions, market signals, and content opportunities.
2. Research them using traceable sources and evidence.
3. Evaluate whether the idea belongs to a specific brand.
4. Create a brief, narrative, script, and storyboard.
5. Prepare visual, narration, and asset instructions.
6. Produce reusable motion graphics and media components.
7. Assemble and finish content using the selected editing tools.
8. Review factual accuracy, quality, rights, and brand fit.
9. Publish with platform-specific metadata.
10. Learn from performance and audience feedback.

The system should progressively move from documented manual workflows to reliable automation. Do not automate a process before its quality criteria are understood.

## 3. The three brand boundaries

| Brand | Core question | Output |
|---|---|---|
| TECHENIGMASTUDIOS | What is this technology, how does it work, and how can I learn it? | Education, explainers, tutorials, learning paths |
| AI That Works | What practical problem can AI solve, and how does the working implementation perform? | Demonstrations, builds, workflows, case studies |
| ContextAhead | Why does this development matter, what does it connect to, and what may change? | Context-rich analysis, timelines, industry explainers |

**Example: AI agents**
- TECHENIGMASTUDIOS explains agent concepts, architecture, tools, memory, and evaluation.
- AI That Works builds and tests an agent that handles a defined business workflow.
- ContextAhead examines how agents could affect software, business models, competition, and work.

Do not recycle one script into three superficial variations. Each brand needs a distinct research question, evidence, narrative, and audience payoff.

## 4. System architecture

```text
Audience signals / search / communities / primary sources / analytics
                              |
                              v
                    01. Research engine
                              |
                              v
                 02. Opportunity evaluation
                              |
                              v
                  03. Brand routing & brief
                              |
                              v
                    04. Editorial engine
                 outline -> script -> fact-check
                              |
                              v
                   05. Production planning
              scenes -> shots -> narration -> assets
                              |
                              v
                     06. Media engine
       graphics / Remotion / Flow / screen capture / FFmpeg
                              |
                              v
                   07. Human finishing
                    DaVinci Resolve
                              |
                              v
                   08. Quality & rights gate
                              |
                              v
                    09. Publishing pack
                              |
                              v
                    10. Analytics & learning
                              |
                              +------> Research engine
```

### Layer responsibilities

- **Research:** collect signals, source material, audience questions, and evidence.
- **Editorial:** choose the angle, structure the explanation, and write scripts.
- **Brand adapters:** apply the correct audience, voice, format, and visual rules.
- **Production:** translate approved scripts into scenes, graphics, media, and edits.
- **Quality:** verify claims, rights, accessibility, technical quality, and brand fit.
- **Publishing:** prepare platform-specific metadata and delivery files.
- **Analytics:** evaluate outcomes and feed lessons into future decisions.

## 5. Repository map

```text
Creator-OS/
├── README.md
├── CONTRIBUTING.md
├── .gitignore
├── docs/
│   ├── system-architecture.md
│   ├── operating-workflow.md
│   ├── brand-separation.md
│   ├── research-and-evidence.md
│   ├── production-workflow.md
│   ├── quality-gates.md
│   └── roadmap.md
├── brands/
│   ├── README.md
│   ├── techenigmastudios/
│   ├── ai-that-works/
│   └── contextahead/
├── research/
│   ├── opportunity-scoring.md
│   ├── source-register-template.csv
│   └── research-brief-template.md
├── editorial/
│   ├── content-brief-template.md
│   ├── script-template.md
│   ├── storyboard-template.md
│   └── repurposing-rules.md
├── production/
│   ├── production-brief-template.md
│   ├── asset-manifest-template.csv
│   ├── naming-conventions.md
│   ├── resolve/
│   ├── remotion/
│   ├── flow/
│   └── ffmpeg/
├── skills/
│   ├── README.md
│   ├── topic-researcher/
│   ├── brand-router/
│   ├── scriptwriter/
│   ├── fact-checker/
│   ├── storyboard-planner/
│   └── publishing-auditor/
├── schemas/
│   ├── content-item.schema.json
│   └── production-plan.schema.json
├── automation/
│   ├── README.md
│   └── scripts/
├── analytics/
│   ├── metrics-dictionary.md
│   ├── experiment-log-template.md
│   └── review-template.md
├── references/
│   └── evaluated-repositories.md
└── .github/
    └── ISSUE_TEMPLATE/
```

The directory structure will grow as working implementations are added. Empty folders are represented with README or placeholder files.

## 6. The standard content lifecycle

`signal → research → evaluate → brand-route → brief → outline → script → fact-check → storyboard → production-plan → create → edit → QA → publish → measure → learn`

Every item receives a stable ID:
- `TES-YYYY-NNN`
- `ATW-YYYY-NNN`
- `CA-YYYY-NNN`

A content item should have a single source of truth for its brief, sources, script, storyboard, assets, production notes, publishing package, and review.

See [Operating Workflow](docs/operating-workflow.md).

## 7. AI-assisted production stack

The stack is intentionally modular. A tool can be replaced without redesigning the whole operating system.

| Need | Candidate tool / environment | Responsibility |
|---|---|---|
| Research and planning | Gemini, ChatGPT, Codex, browser research | Research synthesis, briefs, planning, review |
| Agent-assisted coding | Codex, Google Antigravity | Scripts, tools, automation, integrations |
| Generated video | Google Flow | Supporting generated footage and visual scenes |
| Programmatic motion graphics | Remotion | Reusable animations, diagrams, typography, charts |
| Media processing | FFmpeg | Transcoding, audio/video processing, validation |
| Main editor | DaVinci Resolve | Editorial assembly, colour, audio, finishing, export |
| Storage and versioning | GitHub + local media storage | Documentation/code in Git; large media outside Git |

Tool availability, licensing, quotas, APIs, and capabilities can change. Verify them before depending on them in production. No workflow should assume a paid subscription that is not available.

### Production philosophy

- Use AI to accelerate research and production, not to remove responsibility.
- Prefer structured handoffs over long unstructured prompts.
- Keep deterministic tasks in code where practical.
- Use human judgement for editorial direction and final approval.
- Build reusable visual components instead of recreating every animation.
- Do not claim an automation works until it has been tested.

## 8. Structured content and production data

The system should treat each content item as structured data, not only as a document. The schemas in `schemas/` establish a starting contract.

A production plan may describe:
- content ID and brand
- target platform and aspect ratio
- scene order and approximate duration
- narration and on-screen text
- visual direction and asset references
- source/claim references
- motion-graphic components
- review status

This enables future renderers and automation without making the editorial process dependent on one video tool.

## 9. Quality gates

Content must pass these gates before publication:

1. **Audience gate:** a specific audience and viewer payoff are defined.
2. **Brand gate:** the idea belongs to this brand and does not duplicate another.
3. **Evidence gate:** important claims have traceable sources.
4. **Editorial gate:** the script is clear, coherent, and appropriately scoped.
5. **Production gate:** visuals support the story and assets are accounted for.
6. **Rights and privacy gate:** permissions, licences, consent, and sensitive data are checked.
7. **Technical gate:** audio, captions, framing, readability, and export are checked.
8. **Human approval gate:** a person approves the final deliverable.

See [Quality Gates](docs/quality-gates.md).

## 10. Research integrity and rights

- Prefer primary sources for direct factual claims.
- Record publisher, title, URL, date, access date, and the claim supported.
- Distinguish facts, attributed claims, analysis, and speculation.
- Never invent citations, metrics, quotations, test results, or ROI.
- Verify generated visuals and diagrams against source material.
- Record licences and permissions for music, footage, fonts, images, and templates.
- Do not commit API keys, credentials, private messages, customer data, or confidential files.
- Follow the licence of every external repository or asset before reuse.

## 11. What belongs in Git?

**Keep in Git:** source code, Markdown, JSON/YAML schemas, prompts, agent skills, lightweight templates, small approved graphics, source logs, test fixtures without sensitive data, and documentation.

**Keep outside ordinary Git:** raw footage, generated video masters, high-resolution audio, Resolve caches, proxies, large exports, private datasets, and credentials. Use local storage, external drives, or appropriate media/object storage. Git LFS may be considered for selected versioned media, but is not a substitute for a media archive strategy.

## 12. Metrics and learning

Measure both audience response and editorial quality. Useful metrics include reach, retention, average view duration, completion, rewatch, saves, shares, meaningful comments, follower conversion, click-through, and returning viewers.

Do not optimise only for views. Review whether the content delivered its promised value, whether the audience understood it, and what questions remained.

Experiments should record a hypothesis, variable, sample/time window, result, and decision. Avoid strong conclusions from tiny samples.

## 13. Roadmap

### Stage 1 — Foundation
- Establish brand adapters and editorial boundaries.
- Standardise IDs, briefs, source logs, scripts, storyboards, and asset manifests.
- Define quality gates and naming conventions.

### Stage 2 — Repeatable workflow
- Build research, brand-routing, scripting, fact-checking, and production-planning skills.
- Test the workflow manually on one content item per brand.
- Record failure points and revise templates.

### Stage 3 — Production engine
- Build reusable Remotion components and brand themes.
- Add media-processing and export-validation utilities.
- Define the handoff into DaVinci Resolve.

### Stage 4 — Automation
- Automate stable, repetitive tasks.
- Add validation, tests, logging, and error handling.
- Keep approvals and irreversible publishing actions human-controlled.

### Stage 5 — Measurement and optimisation
- Capture publishing outcomes.
- Compare experiments and brand performance.
- Improve the system from evidence, not assumptions.

This is a capability roadmap, not a date-based promise. A stage is complete only when its deliverables work and have been reviewed.

## 14. Guiding principles

1. One shared engine; three distinct brands.
2. Audience value before output volume.
3. Research before confident claims.
4. Evidence before automation.
5. Structure before scale.
6. Reusable systems before one-off hacks.
7. Human approval before publication.
8. Quality and trust before vanity metrics.
9. Keep tools replaceable.
10. Document decisions and learn from failures.

---

## Start here

1. Read [System Architecture](docs/system-architecture.md).
2. Follow [Operating Workflow](docs/operating-workflow.md).
3. Use the [Research Brief](research/research-brief-template.md).
4. Create a [Content Brief](editorial/content-brief-template.md).
5. Prepare a [Production Brief](production/production-brief-template.md).
6. Apply [Quality Gates](docs/quality-gates.md).
7. Review the [Roadmap](docs/roadmap.md).

**Creator OS exists to make excellent content production repeatable—not to make generic content faster.**
