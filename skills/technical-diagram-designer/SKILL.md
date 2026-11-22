---
name: technical-diagram-designer
description: Design accurate, readable, brand-consistent technical diagrams for technology education. Choose semantic structure before visual layout, and return editable SVG/HTML or renderer-ready specifications.
license: MIT (Creator-OS skill)
---

# Technical Diagram Designer

## Purpose
Create original diagrams that improve understanding of a technical concept. The default brand adapter is applied by the caller; for TECHENIGMASTUDIOS use pure black #000000 and yellow #FFD400 only.

## Inputs
- Audience and learning objective.
- Verified concept description and source/claim references.
- Required entities, steps, relationships, boundaries and caveats.
- Brand adapter and target medium (9:16 short, 16:9 video, carousel, article).
- Required output form (SVG, HTML/SVG, Remotion component spec, or editable diagram source).

## Semantic selection
| Meaning | Diagram pattern |
|---|---|
| Components and connections | Architecture / system map |
| Ordered transformation | Process / pipeline |
| Request and response across actors | Sequence diagram |
| States and transitions | State machine |
| Data transformation and movement | Data-flow diagram |
| Two alternatives or trade-offs | Comparison / decision matrix |
| Time-dependent events | Timeline |
| Hierarchy and decomposition | Tree / layer stack |
| Feedback and repeated operation | Loop / cycle |
| Quantitative change | Chart appropriate to the measure |

Do not create a diagram when a sentence or small table communicates the point more clearly.

## Design rules
1. Every node represents a distinct concept; merge duplicate nodes.
2. Every connector represents a real relationship; remove redundant arrows.
3. Label every relationship that may be ambiguous.
4. Separate control flow, data flow, and feedback flow.
5. Use consistent direction, spacing, alignment and hierarchy.
6. Limit density. If the diagram needs too many nodes, split it into multiple frames/scenes.
7. Use motion only when order or change is part of the meaning.
8. Make diagrams readable at the final mobile viewport, not only at full desktop size.
9. Avoid unsupported technical labels, invented architecture or implied capabilities.
10. Use shape, labels and line patterns as well as colour; never make meaning depend on colour alone.

## TECHENIGMASTUDIOS visual profile
- Background: #000000.
- Primary highlight: #FFD400.
- Black text on yellow for high-emphasis labels.
- Yellow text/lines on black for the main drawing.
- No unapproved accent colours, gradients or decorative glow.
- Strong type hierarchy, generous negative space and restrained motion.
- Diagrams should be original and educational, not merely decorative.

## Output
Return diagram purpose and selected semantic pattern; entity/relationship inventory; layout specification; editable SVG/HTML or renderer-ready scene description; source/claim references; mobile readability notes; accuracy and accessibility checklist.

Never reuse a third-party skill's shipped diagram or copy its source code unless its licence and notices are followed. Use the framework's design principles, then create original artwork.