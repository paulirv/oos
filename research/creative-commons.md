# Creative Commons Layered Model Analysis

How CC's three-layer approach informs OpenOrigin.

## Status: Draft

## The Three Layers

Creative Commons licenses exist in three parallel forms:

1. **Human-readable** ("deed") — Plain language summary anyone can understand
2. **Machine-readable** ("code") — RDF/HTML metadata machines can parse
3. **Legal code** — Full legal text with precise definitions

Each layer says the same thing in a different format for a different audience.

## Application to OpenOrigin

OOS should adopt a similar three-layer approach:

### Layer 1: Human-Readable Summary
A plain-language description of content origin:
> "This article was written by Jane Smith with AI assistance from Claude for research and initial drafting. Jane wrote the final version."

### Layer 2: Machine-Readable Declaration
Structured metadata in HTML, HTTP headers, or JSON-LD:
```html
<meta name="openorigin" content="ai-assisted">
```

### Layer 3: Detailed Specification
The formal OOS spec document defining terms, conformance levels, and validation rules.

## What OOS Borrows

| CC Concept | OOS Equivalent |
|------------|----------------|
| License deed | Origin summary badge/statement |
| Machine-readable code | Meta tags, JSON-LD, HTTP headers |
| Legal code | OOS specification document |
| License chooser tool | Origin declaration generator tool |
| License badges | OOS conformance badges (L1, L2, L3) |

## Key Insights

1. **The chooser tool drove adoption** — CC's web tool that helps you pick a license was crucial. OOS needs an equivalent "declaration builder."
2. **Badges signal conformance** — The CC badge is universally recognized. OOS badges could serve the same function.
3. **Simplicity wins** — Most people interact with CC through the deed, not the legal code. Most publishers will interact with OOS through L1 meta tags, not the full spec.
4. **Layer separation** — Each layer can evolve independently. The spec can add criteria without changing the meta tag format.

## Research Questions

- [ ] How does CC implement machine-readable metadata technically? (RDFa, microdata, link rel?)
- [ ] What's the CC chooser tool's architecture?
- [ ] How did CC achieve badge adoption?
