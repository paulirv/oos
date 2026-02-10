# C2PA / Content Credentials Analysis

How C2PA relates to OpenOrigin and where they diverge.

## Status: Draft

## What C2PA Does

The Coalition for Content Provenance and Authenticity (C2PA) defines a technical standard for:
- Cryptographic signing of media assets (photos, videos, audio)
- Chain of provenance from capture device through editing to publication
- Tamper-evident manifests embedded in files

## C2PA vs. OpenOrigin

| Dimension | C2PA | OpenOrigin |
|-----------|------|------------|
| **Focus** | Media file provenance | Content creation process |
| **Method** | Cryptographic signatures | Self-declared metadata |
| **Trust model** | Hardware/software attestation | Publisher reputation + community norms |
| **Scope** | Binary media files | Any web content (articles, pages, API responses) |
| **Granularity** | Edit-by-edit chain | Process-level declaration |
| **AI story** | "AI was used to modify this image" | "Here's the full human-AI collaboration process" |
| **Adoption** | Camera manufacturers, Adobe, platforms | Web developers, CMS platforms, publishers |

## Complementary, Not Competing

C2PA answers: "Is this photo authentic? What edits were made?"
OpenOrigin answers: "How was this article created? What roles did humans and AI play?"

A publisher could use both:
- C2PA on images (proving they're real photos, not AI-generated)
- OpenOrigin on the article (declaring the writing process)

## What OOS Can Learn from C2PA

1. **Vocabulary matters** — C2PA spent significant effort on terminology
2. **Format flexibility** — C2PA supports multiple manifest formats
3. **Industry backing** — C2PA got Adobe, Microsoft, camera manufacturers involved early
4. **The "just metadata" problem** — C2PA faced skepticism about self-declared data too; their answer was cryptographic proof. OOS takes the WCAG approach instead (self-declaration + norms)

## Research Questions

- [ ] Can OOS reference C2PA manifests as supporting evidence for L3 claims?
- [ ] Is there a schema.org mapping for C2PA concepts?
- [ ] What's C2PA's adoption status as of 2026?
