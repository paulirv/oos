# Spec Writing Best Practices and Competitive Landscape

**Status:** Research Complete
**Date:** 2026-02-10
**Relevance:** Directly informs how to write the OOS and how to position it relative to existing AI content labeling efforts.

---

## 1. Normative Language: RFC 2119 / RFC 8174

The foundation of spec language:

| Keyword | Meaning |
|---------|---------|
| **MUST** / REQUIRED / SHALL | Absolute requirement |
| **MUST NOT** / SHALL NOT | Absolute prohibition |
| **SHOULD** / RECOMMENDED | Valid reasons to deviate may exist, but understand implications |
| **SHOULD NOT** / NOT RECOMMENDED | Acceptable in some circumstances, weigh carefully |
| **MAY** / OPTIONAL | Truly optional |

### Critical Rules

- Only UPPERCASE forms carry normative weight (RFC 8174 clarification)
- Use keywords only where required for interoperability or to prevent harm
- Include the standard boilerplate referencing BCP 14

### For OOS

- Use MUST sparingly. Every MUST is a barrier to conformance.
- Avoid SHALL/SHALL NOT in a developer-facing spec -- too legalistic.
- L1 should have very few MUSTs.

### Separating Normative from Informative

WCAG's strategy (apply to OOS):

| Document | Normative? | Purpose |
|----------|-----------|---------|
| The spec itself | Yes | Principles, guidelines, criteria, conformance |
| Understanding documents | No | Intent, benefits, examples |
| Techniques | No | Implementation patterns |

- Keep core spec lean and normative
- Label informative sections: "This section is non-normative."
- Use "Note:" prefix for informative asides within normative sections

---

## 2. Existing AI Content Labeling Efforts (2025-2026)

### A. IETF AI Content Disclosure Header (draft-abaris-aicdh)

Published April 2025. **Most directly relevant** to OOS.

**Header:** `AI-Disclosure`

| Key | Type | Example |
|-----|------|---------|
| `mode` | Token | `ai-originated` |
| `model` | String | `"gpt-4"` |
| `provider` | String | `"OpenAI"` |
| `reviewed-by` | String | `"editorial-team"` |
| `date` | Date | `@1745286896` |

**Mode values:** `none`, `ai-modified`, `ai-originated`, `machine-generated`

**Limitations:** Applies to entire HTTP response only. No element-level granularity. Expired November 2025 (renewal status unclear). RFC 9651 Structured Fields syntax.

**OOS implication:** This establishes a four-tier vocabulary gaining traction. OOS should align terminology rather than inventing new terms.

### B. HTML AI Content Disclosure (dweekly proposal)

David Weekly's proposal, filed as WICG Issue #261 and WHATWG HTML Issue #9479.

- Page-level: `<meta name="ai-disclosure" content="VALUE">`
- Element-level: `ai-disclosure="VALUE"` attribute on any HTML element
- Values: `none`, `ai-assisted`, `ai-generated`, `autonomous`
- Optional: `ai-model`, `ai-provider`, `ai-prompt-url` attributes
- Inheritance model: children inherit parent values unless overridden

**OOS implication:** Closest existing proposal to what OOS describes. However, it covers only "what role did AI play." OOS's vision is broader -- encompassing full creation process, editorial workflow, and provenance chain. The dweekly proposal could serve as a foundation for OOS's L1 level, while L2/L3 add the depth it lacks.

### C. IPTC Photo Metadata Standard 2025.1

New AI-specific properties:

| Property | Description |
|----------|-------------|
| AI System Used | Name of the AI system |
| AI System Version Used | Version identifier |
| AI Prompt Information | The prompt(s) used |
| AI Prompt Writer Name | Who wrote the prompt |

IPTC Digital Source Type vocabulary (adopted by Google, Meta):
- `trainedAlgorithmicMedia` = "Created using Generative AI"
- `compositeWithTrainedAlgorithmicMedia` = "Edited using Generative AI"

**OOS implication:** Becoming de facto standard for image AI labeling. Align with IPTC terminology where possible, extending to text/web content.

### D. Google SynthID

Invisible watermarks in AI-generated content (text, images, audio, video). Over 10 billion pieces watermarked. Partnered with NVIDIA to extend beyond Google models.

**Limitation:** Detection-based, not declaration-based. Proprietary. Requires model-level integration.

**OOS implication:** Complementary. SynthID answers "was this made by AI?" through detection. OOS answers "what was the creation process?" through voluntary declaration.

### E. EU AI Act Article 50

**Full transparency obligations: August 2, 2026.** Requires:
- AI-generated text on matters of public interest labeled in machine-readable format
- Code of Practice expected June 2026
- Unresolved: short text marking, agentic AI, audio-only labeling, icon design

**OOS implication:** Creates market demand. OOS could position as the best-practice framework exceeding regulatory minimums (like WCAG AAA vs. legal requirements). **The timing is favorable.**

### F. IETF AI Preferences (AI Pref) Working Group

`draft-ietf-aipref-attach` addresses the inverse: how publishers declare preferences about AI training/inference use of their content. Uses robots.txt and HTTP headers.

**OOS implication:** Addresses different direction (consumption vs. creation). Could reference as companion standard.

### Competitive Landscape Summary

| Standard | Scope | Format | Status |
|----------|-------|--------|--------|
| IETF AI-Disclosure | HTTP headers, whole-response | Structured Fields | Expired draft |
| dweekly HTML | Meta tags, element-level | HTML attributes | Proposal |
| IPTC Photo Metadata | Image files | XMP/EXIF | Published standard |
| C2PA | Media files | Cryptographic signatures | Active standard |
| SynthID | Model output | Invisible watermarks | Proprietary |
| EU AI Act | Legal requirement | TBD | August 2026 |
| **OpenOrigin** | **Web content, full process** | **Meta/JSON-LD/HTTP/Frontmatter** | **In development** |

**OOS differentiator:** None of the existing proposals cover the full editorial process spectrum. They handle binary/four-tier AI labeling. OOS adds depth (L2/L3) that no other proposal addresses.

---

## 3. Schema.org Content Metadata

### Existing Relevant Properties (CreativeWork type)

| Property | Type | Purpose |
|----------|------|---------|
| `author` | Person/Organization | Who wrote/created it |
| `creator` | Person/Organization | Who created it (broader) |
| `editor` | Person | Who edited it |
| `contributor` | Person/Organization | Who contributed |
| `dateCreated` | Date | When created |
| `dateModified` | Date | When last modified |
| `datePublished` | Date | When published |
| `isBasedOn` | CreativeWork/URL | Source material |

### What Is Missing

No schema.org property exists for:
- Declaring AI tool involvement in creation
- Specifying the degree of AI contribution
- Documenting the editorial/review process
- Linking to prompt or methodology documentation

### Opportunity for OOS

Define a JSON-LD extension that:
- Reuses `author`, `editor`, `contributor` for human participants
- Defines new terms: `oo:aiRole`, `oo:aiTool`, `oo:editorialProcess`
- Publishes as a schema.org extension namespace (as C2PA and IPTC do)
- Maximizes interoperability with existing tooling (Google structured data parsing, SEO tools)

---

## 4. Successful Small Specs

### Markdown (2004)

- **Creator:** John Gruber (with Aaron Swartz)
- **What worked:** Extreme simplicity, solved immediate pain, one person's opinionated design
- **What went wrong:** No formal spec led to divergent implementations (CommonMark fork)
- **Lesson:** Start simple, but write a real specification from day one. Ambiguity is tech debt.

### JSON Feed (2017)

- **Creators:** Brent Simmons and Manton Reece
- **What worked:** Simple spec readable in one sitting, reference implementations shipped alongside, adopted within weeks
- **Lesson:** Ship the spec with working code. If L1 takes more than 15 minutes to implement, it's too complex.

### Microformats (2004-present)

- **Creator:** Tantek Celik (with Kevin Marks, Eric Meyer, Matt Mullenweg)
- **What worked:** Used existing HTML (CSS classes), "minutes to add," tens of millions adopted
- **Lesson:** Work with existing HTML mechanisms. Drop-in meta tags and JSON-LD blocks are far more adoptable than requiring new infrastructure.

### Open Graph Protocol (2010)

- **Creator:** Facebook
- **What worked:** Four required properties, immediate visible benefit (rich link previews), based on RDFa
- **Lesson:** The **visible benefit loop**. Publishers added OG tags because they could immediately see results. OOS needs a similar feedback loop.

### robots.txt (1994)

- **Creator:** Martijn Koster, a single webmaster
- **What worked:** Solved immediate pain, trivially simple, no protocol changes, adopted through social convention
- **Lesson:** Took 28 years to become RFC 9309. De facto standards can formalize later.

### Pattern Summary

| Spec | v1 Size | What It Grew Into |
|------|---------|-------------------|
| robots.txt | ~1 page | RFC 9309 (28 years later) |
| Markdown | ~1 page | CommonMark (~600 tests), GFM, dozens of extensions |
| JSON Feed | ~2 pages | v1.1 with extensions |
| Open Graph | 4 required properties | Dozens of optional properties, all social platforms |
| Microformats | hCard, hCalendar | Microformats2, dozens of types, IndieWeb ecosystem |

**Consistent pattern:** Start with the smallest useful thing, prove adoption, extend based on real-world needs.

---

## 5. Common Pitfalls

### A. Over-Complexity (The XHTML2 Problem)

XHTML2 died because it broke backward compatibility and added complexity without clear benefit. HTML5 succeeded by being pragmatic.

**For OOS:** L1 must be dead simple. One meta tag. Complexity is opt-in at L2/L3.

### B. Lack of Tooling

Specs without reference implementations, validators, or developer tools languish.

**Ship alongside the spec:**
- A validator (online tool + CLI)
- CMS plugins (WordPress, at minimum)
- SSG plugins (Astro, Hugo, Next.js)
- Browser extension displaying OpenOrigin metadata
- Copy-paste code snippets for every conformance level

### C. No Visible Benefit

Open Graph succeeded because of rich previews. WCAG adoption driven by legal requirements.

**Create visible rewards:**
- Badge/icon system (like CC)
- Search engine recognition (pitch to Google)
- Browser extension showing "content origin" indicator
- Integration with AI answer engines that cite sources

### D. Committee Paralysis vs. Lone Wolf Fragmentation

Committees produce bloated specs slowly. Lone wolves produce simple specs that fragment.

**OOS is in the sweet spot:** One author with clear vision, but writing a formal spec from the start. Invite community feedback early (GitHub issues), maintain editorial control over v1.0.

### E. Competing Without Differentiating

If your spec does exactly what an existing standard does, adoption is near-impossible.

**OOS differentiation is clear:** The dweekly/IETF proposals handle binary/four-tier AI labeling. OOS handles the full creation process spectrum. Not competing -- building the deeper layer they don't address.

---

## 6. Actionable Recommendations for OOS

1. **Align vocabulary with existing efforts.** Use the `none` / `ai-assisted` / `ai-generated` vocabulary from IETF/dweekly proposals where possible. Don't invent new terms. OOS adds depth (L2/L3), not different labels.

2. **Write L1 as one meta tag.** If you can't explain L1 in a tweet, simplify further.

3. **Separate normative from informative from day one.** The spec is lean and normative. Understanding documents, techniques, and examples are informative companions.

4. **Ship tooling with the spec.** A validator, a WordPress plugin, and a browser extension are as important as the spec document.

5. **Create a visible benefit loop.** Publishers need to see something happen when they add OpenOrigin metadata.

6. **Position as complementary, not competitive.** OOS complements C2PA (cryptographic), SynthID (detection), IETF AI-Disclosure (HTTP signals), IPTC (photo metadata). It adds the editorial process dimension that none of them cover.

7. **Dogfood immediately.** Implement on peabod.com before publishing v1.0.

8. **Maintain editorial control for v1.0.** Accept community feedback via GitHub issues, but one author with a clear vision ships faster than a committee.

9. **Target the EU AI Act timeline.** Article 50 obligations arrive August 2026. If OOS v1.0 is published and implementable by mid-2026, it becomes a practical compliance tool.

10. **Plan for three CC-style layers from the start** but only ship the machine-readable layer in v1.0. Human-readable summary and badge system can follow.

---

## 7. Vocabulary Alignment Question

**Decision resolved:** OOS L1 now uses a 4-value vocabulary aligned with emerging industry standards:
- `human` — Content created entirely by humans
- `ai-assisted` — Human-created with AI assistance
- `ai-created` — AI-generated with human oversight
- `ai-generated` — AI-generated with no meaningful human input

The emerging industry vocabulary:
- IETF: `none`, `ai-modified`, `ai-originated`, `machine-generated`
- dweekly: `none`, `ai-assisted`, `ai-generated`, `autonomous`
- IPTC: `trainedAlgorithmicMedia`, `compositeWithTrainedAlgorithmicMedia`

The richer distinctions (edited vs. reviewed) are available at L2 through the AI role categories vocabulary.

---

## Sources

- [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119)
- [RFC 8174](https://www.rfc-editor.org/rfc/rfc8174.html)
- [IETF AI Content Disclosure Header (draft-abaris-aicdh-00)](https://www.ietf.org/id/draft-abaris-aicdh-00.html)
- [AI Content Disclosure for HTML (dweekly)](https://github.com/dweekly/ai-content-disclosure)
- [WICG Proposal #261](https://github.com/WICG/proposals/issues/261)
- [WHATWG HTML Issue #9479](https://github.com/whatwg/html/issues/9479)
- [IPTC Photo Metadata Standard 2025.1](https://www.iptc.org/std/photometadata/specification/IPTC-PhotoMetadata-2025.1.html)
- [IPTC Digital Source Type Vocabulary](https://cv.iptc.org/newscodes/digitalsourcetype/)
- [Google SynthID](https://deepmind.google/models/synthid/)
- [EU AI Act Code of Practice](https://digital-strategy.ec.europa.eu/en/policies/code-practice-ai-generated-content)
- [IETF AI Preferences (draft-ietf-aipref-attach)](https://datatracker.ietf.org/doc/draft-ietf-aipref-attach/)
- [Schema.org CreativeWork](https://schema.org/CreativeWork)
- [JSON Feed Specification](https://www.jsonfeed.org/)
- [Open Graph Protocol](https://ogp.me/)
- [Microformats History](https://microformats.org/wiki/history-of-microformats)
- [CommonMark](https://commonmark.org/)
