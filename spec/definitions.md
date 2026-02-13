# Terminology and Definitions

## Normative Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this specification are to be interpreted as described in BCP 14 [RFC 2119] [RFC 8174] when, and only when, they appear in all capitals, as shown here.

## Definitions

**AI tool**
A software system that uses machine learning, large language models, or other artificial intelligence techniques to generate, modify, or analyze content. Includes but is not limited to: text generators, image generators, code assistants, translation engines, and summarization tools. Does not include conventional software tools such as spell-checkers, grammar checkers, or search engines that operate on deterministic rules.

**conformance level**
One of three defined tiers of OpenOrigin implementation: L1 (Basic), L2 (Detailed), or L3 (Full). Each level is a strict superset of the level below it.

**content**
Any discrete unit of information published on the web. Includes but is not limited to: web pages, articles, blog posts, API responses, documents, images, and multimedia. Each unit of content is independently addressable (has its own URL or is a distinct section within a page).

**creation process**
The sequence of activities, tools, and human decisions that produced a piece of content. Includes research, drafting, editing, review, and any AI tool usage.

**declaration**
A machine-readable statement of content origin conforming to one of the recognized OpenOrigin formats. A declaration is embedded in or associated with the content it describes.

**meaningful human input**
Human involvement that shapes the substance, direction, or quality of the content beyond trivial actions. Approving, selecting, or publishing AI output without substantive modification does not constitute meaningful human input. Editing, rewriting, directing the creative process, or providing original source material does.

**origin**
The combination of who created the content and how it was created, expressed as one of the L1 origin categories: `human`, `ai-assisted`, `ai-created`, or `ai-generated`.

**origin category**
One of the four defined values in the L1 vocabulary: `human`, `ai-assisted`, `ai-created`, `ai-generated`. See [Level 1](success-criteria/level-1.md) for definitions of each value.

**publisher**
The person, organization, or entity responsible for making content publicly available on the web and for the accuracy of its OpenOrigin declaration.

**recognized format**
An implementation format defined by this specification for expressing OpenOrigin declarations. See [Recognized Formats](#recognized-formats).

**substantially revised**
A change to content that alters its meaning, conclusions, or the nature of AI involvement. Fixing typos, formatting changes, and minor copy edits are not substantial revisions. Rewriting sections, adding AI-generated content to previously human-written content, or changing the factual claims constitutes substantial revision.

## Recognized Formats

The following are the normatively defined formats for OpenOrigin declarations:

| Format | Identifier | Specification |
|--------|-----------|---------------|
| HTML meta tag | `html-meta` | [T-HTML-META](techniques/html-meta-tag.md) |
| JSON-LD structured data | `json-ld` | [T-JSON-LD](techniques/json-ld.md) |
| HTTP response header | `http-header` | [T-HTTP-HEADER](techniques/http-header.md) |
| Content frontmatter | `frontmatter` | [T-FRONTMATTER](techniques/frontmatter.md) |

A declaration MUST use one or more of these formats. Implementations MAY use multiple formats simultaneously; when they do, the declarations MUST be consistent (see [3.3 Interoperability](guidelines/3.3-interoperability.md)).

## Author Role Vocabulary

When identifying human contributors at L2 or L3, authors MUST be described using one of the following roles:

| Value | Meaning |
|-------|---------|
| `author` | Primary content creator |
| `editor` | Revised or shaped the content |
| `reviewer` | Reviewed content for accuracy or quality |
| `translator` | Translated content between languages |
| `curator` | Selected, organized, or compiled content |
| `approver` | Authorized publication without substantive content changes |

This vocabulary is extensible: implementations MAY include additional role values prefixed with `x-` (e.g., `x-illustrator`). When multiple roles apply, an author entry MAY list more than one role.
