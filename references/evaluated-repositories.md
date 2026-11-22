# Evaluated External Repositories — Creator Workflow

**Purpose:** record architecture patterns worth learning from the 22 repositories reviewed for TECHENIGMASTUDIOS and Creator-OS. This is an evaluation register, not an installation list.

**Review rule:** do not copy code, prompts, assets, models, or distinctive creative expression merely because a repository is public. Check its current licence, third-party assets, usage terms, security posture, maintenance, required credentials, hardware, and platform rules before adopting anything. The decisions below distinguish reusable design ideas from dependencies we should actually install.

## Executive decision

### Adopt as design references for our own implementation

- [Bang Motion](https://github.com/bangtutorial/bang-motion): continuous motion-design rules, scene structure, style brief before code, deterministic browser-frame export.
- [diagram-design](https://github.com/cathrynlavery/diagram-design): semantic-pattern-first diagram selection, brand profiles, accessible HTML/SVG outputs.
- [anything2explainer](https://github.com/Vincentwei1021/anything2explainer): source-backed research → narration → storyboard → scene components → frame-level QC. **Do not reuse its code/template for commercial work without the author's prior permission:** its toolkit uses PolyForm Noncommercial.
- [Vox Director](https://github.com/Alisa0808/vox-director): staged asset production, beat maps, review checkpoints, FFmpeg assembly. Its Atlas Cloud dependency is not part of Google AI Pro.
- [OpenCreator](https://github.com/krillinai/OpenCreator): Codex-native runtime, shared run state, approvals, skills/MCP, local workspace. Revisit as a possible interface after the manual Creator-OS workflow is proven.
- [VoiceStudio](https://github.com/debpalash/VoiceStudio): local-first speech engine adapters, job queues, model management, API/MCP pattern. Treat as a voice-lab candidate only after checking each model's licence and hardware requirements.

### Use selectively / revisit later

- [OpenSEO](https://github.com/every-app/open-seo): MCP + skill interface for keyword research, competitor insights and AI visibility; requires a separate paid DataForSEO account or reseller balance.
- [Tencent WeKnora](https://github.com/Tencent/WeKnora): source-grounded RAG, hybrid retrieval, citations, knowledge curation/versioning and audit patterns; its full deployment is excessive for our current needs.
- [Podcastfy](https://github.com/souzatharsis/podcastfy): potential later conversion of long-form lessons into multi-speaker audio conversations.
- [LangChain Social Media Agent](https://github.com/langchain-ai/social-media-agent): human-in-the-loop draft approval and inbox patterns; full setup requires several third-party services.
- [paint-mv-skills](https://github.com/lintsinghua/paint-mv-skills): useful chapter decomposition, shared character/asset continuity, contact sheets and resumable renders, but the actual music-video workflow is not our format. The upstream PDoomVideo engine it downloads has no declared licence and must not be treated as reusable code.
- [ghost-editor](https://github.com/kurbaitaev/ghost-editor): editing QA and style-system ideas only; it is built for talking-head footage and its documented workflow is Mac-focused.

### Do not adopt for this creator operation

- [InstaPy](https://github.com/InstaPy/InstaPy): automates likes, comments and follows; its README says its creator was banned by Meta for creating and teaching social automation. Not appropriate for account health.
- [GramAddict](https://github.com/GramAddict/bot): Android automation for likes, follows, comments and DMs. Avoid engagement automation and account-risk patterns.
- [drawrowfly/instagram-scraper (InstaTouch)](https://github.com/drawrowfly/instagram-scraper): unofficial scraping of posts, comments, likers, followers and media; some operations require active sessions and it documents rate-limit/proxy handling. No use in our research pipeline.
- [instagrapi](https://github.com/subzeroid/instagrapi): unofficial private Instagram API, session handling and interaction/upload primitives. Its own README warns private-API automation is fragile and recommends official APIs for account-owned workflows.
- [InstaLooter](https://github.com/althonos/InstaLooter): legacy API-less downloader, GPLv3+, with old Python compatibility targets. Not useful for our content workflow.
- [Claudegram](https://github.com/karthiktadepalli1/claudegram): Claude-powered AI-text detector, not a creator workflow; requires a Claude Code login we do not have. AI-detection verdicts should not be treated as proof of authorship or quality.
- [MotionClone](https://github.com/LPengYang/MotionClone): research implementation for motion transfer using Stable Diffusion 1.5/AnimateDiff and downloaded model weights; specialised hardware/model setup and no top-level licence located in this review. Not required while Flow and deterministic motion graphics cover our use cases.
- [FluxCD](https://github.com/fluxcd/flux2): Kubernetes GitOps delivery. No current need to deploy Creator-OS as a Kubernetes service.
- [OpenProject](https://github.com/opf/openproject): large GPLv3 project/portfolio management product. Our existing Creator-OS content lifecycle is sufficient; adopting a second project-management platform adds operational overhead.
- [OpenHiggsfield](https://github.com/wide-trace/open-higgsfield): multi-provider image/video studio with model catalog, server-side credential handling and asset history. Useful catalog/provider-adapter ideas, but it requires a separate generation-platform key and its repository licence was not located in this review. It does not replace Google Flow or grant Flow credits.

## Repository-by-repository review

| Repository | Main architecture / useful idea | Licence / dependency notes | Decision |
|---|---|---|---|
| open-higgsfield | Single generation request object `{model,prompt,media,settings}`; model catalog owns per-model settings; server-only API calls; persisted run history; asset library and retry lifecycle. | No top-level LICENSE located in inspected files. Requires a separate generation API key, Vercel Blob for uploads, and its own provider backend. | **Reference only.** Borrow the provider-catalog abstraction if we later support multiple generation providers. Do not copy code or substitute it for Flow. |
| VoiceStudio | Local-first speech workspace; engine adapters; model manager; batch jobs; transcription, voice design/cloning, dubbing, API and MCP. | Application is AGPL-3.0. The README identifies the default OmniVoice weights as non-commercial; every model has its own terms. Local model downloads and hardware are required for some engines. | **Optional voice lab.** Do not include default weights in commercial production. Test a commercially cleared model separately before adopting. |
| open-seo | Agent-facing SEO system through MCP and reusable skills; keyword research, competitor insights, rank tracking, backlinks, audits and AI visibility. | MIT. DataForSEO is a separate pay-as-you-go service; repo docs state a $1 trial credit and $50 minimum top-up for its account path; a third-party reseller is also described. | **Revisit after launch.** Use only when SEO research at scale justifies data costs. Google Trends and manual platform research remain the initial low-cost sources. |
| WeKnora | Shared knowledge bases for RAG, agent tasks and wikis; hybrid retrieval, citations to source passages, multimodal parsing, knowledge curation/versioning, MCP, RBAC and tracing. | MIT for WeKnora with separately listed third-party components. Full Docker/Kubernetes setup has multiple services; Lite mode exists but still needs evaluation. | **Architecture reference.** Borrow source traceability, citations and knowledge versioning. Do not deploy it yet; NotebookLM + Drive + GitHub are enough. |
| OpenProject | Enterprise project/portfolio management, tasks, roadmaps, Gantt, agile boards, time and budget tracking. | GPLv3; large self-hosted application. | **Do not adopt.** Creator-OS already has states, IDs and review gates; another platform duplicates the control plane. |
| InstaPy | Selenium-driven Instagram interaction automation: likes, comments and follows. | GPLv3. README explicitly notes the creator was banned by Meta for creating/teaching social automation. | **Reject.** No automated engagement or growth bots. |
| GramAddict | Android/ADB automation for liking, following, commenting and sending DMs; includes scraping modes. | MIT. README itself describes action-blocking risks and attempts to imitate human activity. | **Reject.** MIT licence does not make platform automation safe or permitted. |
| Claudegram | Browser extension that submits selected text/pages/documents to Claude for AI-writing classification. | MIT, but requires Claude Code and a Claude subscription. Its verdict is a heuristic classification, not proof. | **Not relevant.** We need editorial quality and source checks, not AI-detector scores. |
| Instagram-scraper / InstaTouch | Unofficial Instagram Graph scraping for posts, comments, likers, followers and media; supports CSV/JSON and downloads. | Package metadata says MIT, but no top-level LICENSE was found. Some operations require an active session; README documents rate limits and proxy/timeout options. | **Reject for our research system.** Do not scrape followers, likers, private/session data or download creators' media. Use visible public research and official APIs where appropriate. |
| Vox Director | Agent pipeline from topic to beat map, visual keyframes, motion, voice/music, captions and FFmpeg output; approval before expensive generation. | MIT code, but generation uses Atlas Cloud API and paid model providers. Its named Vox-style collage is an external creative reference; do not copy a creator's distinctive expression. | **Borrow stage gates and production manifest.** No Atlas dependency for our pilot; retain our own black/yellow visual identity. |
| paint-mv-skills | Director/storyboard/animation/render skill separation; beat/lyric alignment; chapter-level parallel work; shared character sheets; contact sheets; resumable frame renders. | Repository MIT. It downloads PDoomVideo source at setup; that upstream repository has no declared licence and is explicitly not included. | **Borrow only generic orchestration/QC patterns.** Do not fetch, copy or patch the unlicensed upstream engine. Music-video format itself is out of scope. |
| anything2explainer | Remotion/React/TypeScript code-rendered explainer; source-backed research; narration and voice timing; storyboard per shot; parallel scene components; rendered-frame QC; multiple approval checkpoints. | PolyForm Noncommercial 1.0.0. Commercial use of the toolkit requires prior authorisation. Bundled fonts have separate OFL terms. | **Most relevant learning reference, but no code reuse for a monetisable brand without written permission.** Build our own independent Remotion pipeline using the general architecture. |
| Bang Motion | Agent Skill for cinematic HTML/CSS/GSAP motion; one continuous visual world rather than slide-like fades; style brief before coding; reusable starters; Puppeteer frame capture and FFmpeg MP4 export. | MIT. Browser deliverable can be viewed without Node; precise MP4 export needs Puppeteer + FFmpeg. | **Adopt as a design reference and optional skill.** Particularly useful for hooks, kinetic type, transitions and quick web-based animation prototypes. |
| ghost-editor | Selects usable takes from talking-head footage, builds a short reel in named styles, captions/B-roll and automated QA. | MIT. README says local Mac workflow, Whisper/OpenCV, FFmpeg and a Gemini API key for one B-roll check. | **Do not install for TECHENIGMASTUDIOS.** Our brand is faceless. Reuse only the idea of measurable audio/caption/export QA. |
| MotionClone | Training-free motion representation from temporal-attention maps, for reference-video-controlled generation with Stable Diffusion 1.5/AnimateDiff. | No top-level LICENSE located in this review. Requires specialised checkpoints and model setup. | **Research reference only.** Not required for our current Flow + code-animation stack. |
| OpenCreator | Codex CLI as execution runtime; local daemon/workspace; visual creative tools and reusable Skills; MCP; one shared state machine for visual and agent flows; runs, approvals and background work. | Apache-2.0. It is a substantial desktop/runtime application and uses Codex as its execution engine. | **Revisit later.** Study its runtime, capability/permission and approval design. Do not replace Creator-OS or duplicate its control plane now. |
| FluxCD | GitOps Toolkit for Kubernetes controllers and declarative cluster reconciliation. | Apache-2.0. | **Not relevant now.** No Kubernetes workload exists in this creator operation. |
| Podcastfy | Multimodal sources (text, PDFs, websites, images, YouTube) to multi-speaker AI audio conversations; Python package and configurable/local LLMs. | Apache-2.0. Voice and LLM providers still have their own costs and licences. | **Future repurposing option.** Test only after a long-form lesson library exists; not our Reel renderer. |
| LangChain Social Media Agent | LangGraph flow that takes a URL, drafts social posts, and uses an Agent Inbox for human edits/accept/reject; optional Slack intake and scheduled processing. | MIT. Full setup requires Anthropic, LangSmith, Firecrawl, Arcade, Supabase and platform credentials. | **Adopt HITL pattern only.** Creator-OS already has approvals; do not bring in its dependency stack or automated posting yet. |
| diagram-design | Agent Skill with semantic-pattern-first diagram selection, many diagram grammars, brand profiles, self-contained HTML/SVG, PNG/SVG export and import adapters. | MIT. Skill includes privacy notes and multiple host installers. | **Adopt as a primary diagram-design reference.** Create a TECHENIGMASTUDIOS black/yellow diagram skill; use SVG/HTML outputs and avoid copying its default visual palette. |
| instagrapi | Python wrapper for public web and private mobile Instagram flows; sessions, challenges, media, comments, insights, DMs and uploads. | MIT. README calls private API automation fragile and recommends official APIs for account-owned workflows. | **Reject for automation/scraping.** We will not store Instagram passwords, session IDs or use private endpoints. |
| InstaLooter | Legacy API-less Instagram picture/video downloader for profiles. | GPLv3+. Setup metadata targets old Python 2.7–3.6 versions. | **Reject.** Legacy downloader; no role in original educational content production. |

## Architectural patterns selected

1. **Typed content-to-production handoff:** keep the editorial brief separate from a validated scene/production plan. Every scene has duration, narration, screen text, visual direction, asset IDs and claim/source references.
2. **Deterministic rendering:** render scenes from code (Remotion or a browser/GSAP composition) at explicit timestamps; do not rely on screen recording for final frame accuracy.
3. **Human checkpoints:** approve research angle, script/narration, first visual pilot and final export before publishing or spending on optional generated footage.
4. **Visual QA:** render contact sheets and representative stills, check text safe areas, scene continuity, caption timing, audio, frame rate, aspect ratio and file integrity.
5. **Provider adapters:** keep voice, image, video and model providers behind replaceable adapters. A Google Flow clip is an optional asset, not a hard dependency of the renderer.
6. **Source-grounded knowledge:** retain source IDs, dates and claim mappings; citations must be inspectable in the final script/brief.
7. **Human-approved distribution:** prepare platform-specific packages, then publish with native platform tools or approved official APIs. Do not automate follows, likes, comments, DMs, scrape private data or use unofficial private endpoints.

## Selected implementation for our current stack

- **Creative/reasoning:** Gemini models for research synthesis, script/scene planning and critique; Codex for code, tests and deterministic render tooling.
- **Generated footage:** Google Flow only when a scene benefits from generated video. Keep provider credentials out of scripts and Git.
- **Primary code renderer:** Remotion with React/TypeScript for reusable, data-driven educational scenes.
- **Quick motion prototypes:** HTML/CSS/GSAP patterns inspired by Bang Motion, only where they are more efficient than a Remotion composition.
- **Technical diagrams:** original SVG/HTML diagrams using a TECHENIGMASTUDIOS palette profile.
- **Audio/media:** recorded or appropriately licensed TTS voiceover; FFmpeg/ffprobe for deterministic media processing and validation.
- **Final finishing:** DaVinci Resolve remains the finishing editor; raw and rendered media stay outside Git.
- **VoiceStudio, OpenCreator, WeKnora, OpenSEO and Podcastfy:** optional candidates, not current dependencies.

## Review limitations

The review used repository metadata, README files, selected workflow/skill files, and licence files where available. It is not a complete security audit, dependency audit, runtime test, or legal opinion. Re-check the upstream branch, licence and terms before installing or reusing anything. A public repository is not automatically a safe or licensed dependency.
