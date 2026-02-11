---
date: 2026-02-10
topic: Project Setup
duration: ~1 hour
commits:
  - 7f2be61
  - ac6f88f
requirements: []
tags: [setup, spec-framework, research, examples]
---

# Session: Project Setup

## Objective

Set up the OpenOrigin Specification project from initial scaffolding to a working spec framework with research, examples, and project management.

## Accomplished

Built out the complete WCAG-modeled spec structure, prior art research, reference implementations, and project management foundation.

### Changes Made

- Created 4 principle documents (Transparent, Accurate, Machine-Readable, Practical)
- Created 12 guideline documents (3 per principle, numbered 1.1–4.3)
- Created 3 conformance level documents (L1: 8 criteria, L2: +9, L3: +7 = 24 total)
- Created 4 technique documents (HTML meta tag, JSON-LD, HTTP headers, frontmatter)
- Created spec index and conformance model
- Created 6 research files (prior art overview, WCAG, C2PA, Creative Commons, Schema.org, EU AI Act)
- Created 4 example files (L1 HTML, L2 JSON-LD, HTTP headers, frontmatter blog post)
- Created PM foundation files (backlog, definition of done, traceability matrix)
- Updated README with quick start, principles, conformance levels, and project structure
- Removed .gitkeep placeholders from directories that now have content

### Commits

- `7f2be61`: chore: initialize OpenOrigin Specification project
- `ac6f88f`: feat: add spec framework, research, examples, and project management

## Requirements Progress

No formal requirements established yet — project is in pre-requirements phase.

## Remaining Work

### Next Steps

- [ ] Finalize L1 origin vocabulary (the 5 category values)
- [ ] Define the JSON-LD schema/context document
- [ ] Deep research: WCAG structure and governance process
- [ ] Deep research: C2PA technical specification
- [ ] Deep research: Schema.org content metadata types
- [ ] Dogfood L1 on a peabod.com article
- [ ] Define L2 role vocabulary (final values)
- [ ] Design conformance badge system
- [ ] Build declaration generator tool

## Blockers/Issues

None. Clean start.

## Decisions Made

Key design decisions captured in spec documents:
- WCAG-modeled structure (Principles > Guidelines > Success Criteria > Techniques)
- Three conformance levels: L1 (Basic), L2 (Detailed), L3 (Full)
- Three layers following Creative Commons model (human-readable, machine-readable, spec)
- Separate JSON-LD context (not extending schema.org directly) — can propose upstream later
- Five L1 origin categories: human, human-ai-assisted, ai-human-edited, ai-human-reviewed, ai-generated
- Self-declaration model (like WCAG, not cryptographic like C2PA)

## Lessons Learned

None yet — first session.

## Notes

The spec framework is intentionally front-loaded. Having the full Principles > Guidelines > Success Criteria > Techniques structure in place before deep research means the research can be directed at refining specific criteria rather than figuring out structure. The backlog is prioritized with vocabulary finalization and dogfooding at the top.
