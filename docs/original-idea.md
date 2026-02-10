# OpenOrigin Specification

**Status:** Idea / Early Research
**Date captured:** 2026-02-08
**Author:** Paul Irving, Insite Web Publishing, Inc.

## The Idea

An open specification for declaring the origin and creation process of web content. Think WCAG for content transparency. Machine-readable, implementable, auditable.

Not just "was AI involved?" but the full story of how content came to be.

## Why This Matters

The AI content transparency conversation is stuck in binary mode: "AI-generated" or "human-created." The reality is a spectrum:

- Human wrote it, AI suggested edits
- Human outlined it, AI drafted sections, human rewrote
- AI generated first draft, human substantially edited
- Human and AI co-created through iterative conversation
- AI generated, human reviewed and approved with no changes
- Fully AI-generated, no human review

Current standards don't capture this nuance. They were designed for a world of "real vs. fake photos," not a world where every knowledge worker uses AI daily.

## What Exists (and What Doesn't)

| Standard | Scope | Gap |
|----------|-------|-----|
| C2PA / Content Credentials | Cryptographic media provenance | Binary media only. Not web content. Not the creation process. |
| EU AI Act Code of Practice | Regulatory AI labeling | Compliance-focused. Binary classification. |
| Platform labels (YouTube, Meta) | Platform-specific AI flags | Proprietary, inconsistent, not machine-readable. |
| OpenAI Model Spec | Model behavior specification | Provider-side. Not publisher-side. |

**The gap:** No open, web-developer-focused specification for declaring content creation processes in a standardized, machine-readable way.

## What OpenOrigin Could Be

A specification that defines:

### 1. Content Origin Declaration
- Who initiated the content (person, organization)
- What role did AI play (none, assistant, co-creator, primary author)
- What tools were involved (specific models, versions, tools)
- What was the human editorial process

### 2. Granularity Levels
Like WCAG's A/AA/AAA conformance levels:
- **Level 1 (Basic):** Binary declaration — human-created, AI-assisted, AI-generated
- **Level 2 (Detailed):** Role breakdown — human contribution %, AI tools used, editorial process
- **Level 3 (Full):** Complete provenance chain — prompts, iterations, sources consulted, review process

### 3. Machine-Readable Format
- HTML meta tags / microdata / JSON-LD (like schema.org)
- HTTP headers for API responses
- Frontmatter for static content
- Embeddable in any content format

### 4. Verification & Auditing
- Self-declared (like WCAG — you claim conformance)
- Optional third-party verification
- Audit trail recommendations

## Why Paul Irving Should Write This

- **30+ years** building for the web through every standards evolution
- **Daily AI user** shipping production code — not theoretical, practical
- **Content creator** actively grappling with this exact transparency question (peabod.com, Substack)
- **Accessibility expertise** — understands how specs become usable (WCAG veteran)
- **Solo practitioner + enterprise experience** — can bridge indie and corporate needs
- **Has the tooling** to dogfood it immediately (BoB framework, peabod articles)

## Spec Structure (Modeled on WCAG)

WCAG is a good structural model:

1. **Principles** (like WCAG's Perceivable, Operable, Understandable, Robust)
   - Transparent, Accurate, Machine-Readable, Practical
2. **Guidelines** under each principle
3. **Success Criteria** at conformance levels
4. **Techniques** (sufficient and advisory)
5. **Understanding documents** (rationale and examples)

## Prior Art to Study

| Specification | What to Learn |
|---------------|---------------|
| WCAG 2.1 | Structure, conformance levels, consensus process |
| Schema.org | Machine-readable metadata, adoption strategy |
| C2PA Technical Spec | Provenance chain concepts, terminology |
| XML Specification | Formal spec writing style |
| OpenAPI Specification | Community-driven spec governance |
| Creative Commons | Simple, layered declarations (human-readable + machine-readable + legal) |

Creative Commons is an especially interesting model: three layers (human-readable summary, machine-readable code, legal text) that work together.

## Potential Objections

| Objection | Response |
|-----------|----------|
| "C2PA already does this" | C2PA is cryptographic media provenance. OpenOrigin is content creation process declaration. Complementary, not competing. |
| "Nobody will self-declare honestly" | Same argument was made against WCAG. Self-declaration + community norms + optional auditing creates accountability. |
| "Too complex for small publishers" | Level 1 conformance is literally one meta tag. Complexity is opt-in. |
| "The EU will mandate something" | Regulatory mandates are minimums. OpenOrigin would be the best-practice standard that exceeds compliance (like WCAG AAA vs. legal minimum). |

## Next Steps

1. Study the specs listed above — especially WCAG process docs and Creative Commons layered approach
2. Draft OpenOrigin Principles — the 3-4 foundational principles
3. Write Level 1 Success Criteria — the simplest, most adoptable version
4. Create reference implementation — HTML meta tags, JSON-LD, frontmatter format
5. Dogfood on peabod.com — Use it on every article
6. Publish as article series — Build audience and invite feedback
7. Stand up a specification website — openorigin.org? (check availability)

## Connection to peabod.com

peabod.com is the perfect launch platform:
- Every article Paul writes uses AI tools to some degree
- The Substack audience is AI-aware developers who care about transparency
- Can demonstrate OpenOrigin conformance on real content
- Article series documenting the spec development process = content + spec in parallel

## Domain

**openorigin.dev** — Registered 2026-02-08.

| Domain | Status |
|--------|--------|
| openorigin.dev | Ours |
| openorigin.com | For sale on Afternic (GoDaddy marketplace) |
| openorigin.org | Parked, expires April 2026 |
| openorigin.io | Parked, expires April 2026 |

## Research Questions

- [x] ~~Is openorigin.org available?~~ No, but .dev is ours. .org/.io expire April 2026.
- [ ] Is there a W3C Community Group process for new specs?
- [ ] What's the WCAG Working Group's governance model?
- [ ] Are there existing schema.org types for content creation metadata?
- [ ] What would a Level 1 meta tag look like in practice?
- [ ] How does Creative Commons handle the three-layer approach technically?
