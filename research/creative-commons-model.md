# Creative Commons: Three-Layer System, Adoption Strategy, and Technical Implementation

**Status:** Research Complete
**Date:** 2026-02-10
**Relevance:** CC's three-layer model is the primary inspiration for OOS's human-readable / machine-readable / specification architecture.

---

## 1. The Three-Layer Model in Practice

Creative Commons licenses operate through three distinct but interconnected layers, a design philosophy established by Lawrence Lessig and the founding team in 2001-2002.

### Legal Code (the "lawyer-readable" layer)

The legal code is the actual license text -- a full legal instrument with traditional legal language. Each license (e.g., CC BY 4.0) has a complete legal document that would hold up in court.

- Written by lawyers, for lawyers and courts
- Jurisdiction-specific in early versions (1.0-3.0), then "international" in 4.0
- Defines terms precisely: "Licensed Material," "Adapted Material," "Share," "Reproduce"
- CC BY 4.0 legal code is approximately 2,000 words
- Hosted at URLs like `creativecommons.org/licenses/by/4.0/legalcode`

### Human-Readable Deed (the "Commons Deed")

The deed is a plain-language summary -- what you can and cannot do. It is explicitly "not a license" and has no legal force:

- Typically one page with icons and short bullet points
- Structured as: "You are free to..." / "Under the following terms..."
- Uses the CC badge icons as visual shorthand
- Available in dozens of languages (community-translated)
- Hosted at URLs like `creativecommons.org/licenses/by/4.0/` (no "legalcode" suffix)

### Machine-Readable Code (the "digital code" layer)

The technical metadata layer uses several formats:

**CC REL (Creative Commons Rights Expression Language):**
- Built on RDF (Resource Description Framework)
- Defines properties like `cc:license`, `cc:attributionName`, `cc:attributionURL`
- Namespace: `http://creativecommons.org/ns#`

**RDFa (the primary HTML embedding method):**

```html
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">
  <img alt="Creative Commons License" src="https://i.creativecommons.org/l/by/4.0/88x31.png" />
</a>
<br />
This work by <a xmlns:cc="http://creativecommons.org/ns#"
  href="https://example.com" property="cc:attributionName"
  rel="cc:attributionURL">Author Name</a>
is licensed under a <a rel="license"
  href="http://creativecommons.org/licenses/by/4.0/">
  Creative Commons Attribution 4.0 International License</a>.
```

**JSON-LD (newer adoption):**

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "name": "Example Article",
  "author": "Author Name",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

**XMP:** Used for embedding license info directly in image, PDF, and media files.

**Key design insight:** The machine-readable layer doesn't reinvent metadata standards -- it rides on top of existing ones (RDF, Dublin Core, Schema.org). The CC namespace adds only what's license-specific.

---

## 2. The CC Chooser Tool

### UX Flow

1. **Start with questions, not license names.** The chooser never asks "which license do you want?" -- it asks about intentions:
   - "Allow adaptations of your work?" (Yes / Yes, share alike / No)
   - "Allow commercial uses of your work?" (Yes / No)

2. **Two questions yield six licenses.** Simple combinatorial logic.

3. **Immediate visual feedback.** Badge and name update in real time.

4. **Attribution metadata collection.** Optionally: title, name, URL, source, format.

5. **Copy-paste output.** Generates HTML with badge image, human-readable link, RDFa metadata, and `rel="license"` attributes.

### Why It Drove Adoption

- **Eliminated decision paralysis.** Two simple questions instead of reading six license texts.
- **Generated correct markup.** Users didn't need to understand RDFa.
- **Made the badge visible.** Output included the visual badge by default.
- **Lowered the barrier to zero technical knowledge.** Under 60 seconds to add a CC license.

**Key insight for OOS:** The chooser was arguably more important than the licenses themselves for adoption.

---

## 3. Adoption Strategy: From Unknown to Ubiquitous

### Phase 1: Academic and Legal Credibility (2001-2003)

- Founded by Lawrence Lessig (Stanford Law), Hal Abelson (MIT), Eric Eldred
- Positioned as "doing for content what FSF/GPL did for code"
- Launch: December 16, 2002 -- first licenses released
- Key early adopters: MIT OpenCourseWare, Public Library of Science (PLoS)

### Phase 2: Platform Integration (2004-2006)

- **Flickr (2004):** Single biggest inflection point. CC license selection in upload flow. Millions of photos CC-licensed within a year.
- **Google Image Search (2005):** Filter by CC license. CC-licensed content discoverable at scale.
- **Wikipedia/Wikimedia (2005-2009):** Migration from GFDL to CC BY-SA 3.0 made CC BY-SA the de facto standard for collaborative knowledge.

### Phase 3: Institutional Adoption (2007-2012)

- Government open data (White House, national governments)
- Education: UNESCO recommended CC for educational materials
- Science: Open Access journals standardized on CC BY
- CC0 (Public Domain Dedication) released 2009

### Phase 4: Default Standard (2013-Present)

- YouTube (2011): CC BY as a license option
- Over 2 billion CC-licensed works estimated by 2021

### Key Inflection Points

1. **Flickr integration (2004)** -- Platform integration beats individual adoption
2. **Google search filter (2005)** -- Created demand-side pull
3. **Wikipedia migration (2009)** -- CC BY-SA became the collaborative content standard
4. **Government adoption** -- Legitimized for institutional use
5. **The Chooser tool** -- Made adoption trivially easy

### Strategic Lessons

- **Don't ask people to adopt your standard; embed it in tools they already use.**
- **Make the simplest version genuinely simple.** CC BY is one condition: give credit.
- **Leverage existing communities.** CC didn't build a community; it gave tools to existing communities.
- **The deed (human-readable layer) was the marketing tool.** People shared badges, not legal text.

---

## 4. Version Evolution (1.0 through 4.0)

| Version | Date | Key Changes |
|---------|------|-------------|
| 1.0 | Dec 2002 | 11 licenses, jurisdiction-specific, US-centric |
| 2.0 | May 2004 | "Generic" (unported) version introduced |
| 2.5 | Jun 2005 | Attribution required for all licenses (non-attribution retired) |
| 3.0 | Feb 2007 | Unported as primary, compatibility framework, moral rights |
| 4.0 | Nov 2013 | Fully international (no more ports), database rights, 30-day auto-cure |

### 4.0 Was Designed to Be the Last Major Version

- No more jurisdiction-specific ports -- one legal text works globally
- Explicit database rights coverage
- 30-day automatic cure for violations
- Designed to not need future versions

### Versioning Strategy Lessons

1. **Never invalidate prior versions.** Every CC license ever applied still works.
2. **Make upgrade paths clear and one-directional.** 3.0 -> 4.0 allowed; reverse not.
3. **Design for "last version needed."**
4. **Version infrequently.** Four major versions in 20+ years.
5. **Maintain backward compatibility.**

---

## 5. Badge and Icon System

### Design

- Each condition has a distinct symbol: BY (person), SA (circular arrow), NC (dollar with strike-through), ND (equals sign)
- CC logo: Two C's in a circle (analogous to copyright (c) symbol)
- Standard web badge: 88x31 pixels (same size as old W3C badges, deliberately)
- Compact badge: 80x15 pixels for footers
- Black and white by default (works on any background)

### Design Principles

1. **Universal symbols** -- No text, works across languages
2. **Composable** -- Condition icons combine into license badges
3. **Self-explanatory** -- Person icon (attribution), dollar with line (non-commercial)
4. **Consistent sizing** -- All condition icons same size

---

## 6. Governance

- 501(c)(3) nonprofit, US-based
- Board of Directors oversees strategy and major license decisions
- CC Global Network (CCGN) replaced older "Affiliate" model (~2017-2018)
- Chapters in 80+ countries

### License Development Process

1. Public discussion period with discussion draft
2. Multiple rounds of public comment (2-4 rounds for major versions)
3. Expert consultation from multiple jurisdictions
4. Board approval of final text
5. 4.0 process took approximately 2 years (2011-2013)

### Key Governance Principle: Conservative Expansion

CC has been extremely conservative about new licenses:
- **Retired** options (Developing Nations license, non-attribution licenses)
- Guiding philosophy: **fewer licenses, not more**
- License proliferation is harmful (compatibility problems)
- Proposals for new licenses consistently resisted

---

## 7. Technical Implementation

### Simplest implementation:

```html
<link rel="license" href="https://creativecommons.org/licenses/by/4.0/">
```

### CC REL Properties

| Property | Purpose |
|----------|---------|
| `cc:license` | The license URL |
| `cc:attributionName` | Who to credit |
| `cc:attributionURL` | Link for credit |
| `cc:morePermissions` | URL for additional permissions |
| `cc:permits` | What the license permits |
| `cc:requires` | What the license requires |
| `cc:prohibits` | What the license prohibits |

### Search Engine Support

- Google reads `rel="license"` links and structured data for image search filters
- CC Search (now Openverse) crawls platforms for CC-licensed content
- Flickr API, YouTube API, WordPress all integrate CC through their APIs

---

## Implications for OpenOrigin

### Adapt the Three-Layer Model

For OOS (declarative, not legal), the layers serve different purposes:
- **Human-readable:** "This content was created by a human with AI assistance"
- **Machine-readable:** Structured metadata in JSON-LD/meta tags
- **Detailed specification:** The full OOS spec document (precision, not legal enforcement)

### The Chooser Tool Is Not Optional

Plan for an interactive tool from day one that:
- Asks simple questions about content creation process
- Generates copy-paste markup
- Produces the badge/visual indicator automatically

### Platform Integration Beats Individual Adoption

Target CMS platforms (WordPress, Ghost, Hugo, Astro) and publishing tools early, not individual publishers.

### Start With the Minimum

CC started with eleven licenses and had to retire some. OOS should launch with the smallest viable set of declaration options at L1.

### Badges Are the Viral Vector

OOS needs a visual indicator system that is instantly recognizable, works across languages, is composable, and embeddable with a single line of HTML.

### Ride Existing Metadata Standards

CC didn't invent RDF or Dublin Core -- it built a thin layer on top. OOS should use Schema.org, JSON-LD, and existing meta tag conventions.

---

## Sources

- [Creative Commons Licenses](https://creativecommons.org/share-your-work/cclicenses/)
- [CC REL Specification](https://wiki.creativecommons.org/wiki/CC_REL)
- [CC Chooser](https://chooser-beta.creativecommons.org/)
- [CC Global Network](https://network.creativecommons.org/)
- [State of the Commons Reports](https://creativecommons.org/about/program-areas/policy-advocacy-copyright-reform/state-of-the-commons/)
- [CC Version 4.0 Overview](https://wiki.creativecommons.org/wiki/4.0)
