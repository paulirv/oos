# OpenOrigin Specification

**Version:** 0.1.0-draft
**Status:** Working Draft
**Editor:** Paul Irving, Insite Web Publishing, Inc.

## Abstract

OpenOrigin defines a standardized way to declare the origin and creation process of web content. It provides machine-readable, implementable, and auditable declarations that describe how content was created — including the roles of human authors and AI tools.

## Terminology

See [Terminology and Definitions](definitions.md) for formal definitions of key terms and normative language conventions used in this specification.

## Conformance Levels

- **[Level 1 (Basic)](success-criteria/level-1.md)** — One declaration. Origin category.
- **[Level 2 (Detailed)](success-criteria/level-2.md)** — Structured data. Roles, tools, dates.
- **[Level 3 (Full)](success-criteria/level-3.md)** — Complete provenance chain.

See [Conformance](conformance.md) for details on claiming conformance.

## Principles

1. **[Transparent](principles/transparent.md)** — Content origin is openly declared
2. **[Accurate](principles/accurate.md)** — Declarations truthfully represent the creation process
3. **[Machine-Readable](principles/machine-readable.md)** — Declarations use standardized, parseable formats
4. **[Practical](principles/practical.md)** — Conformance is achievable for publishers of any size

## Guidelines

### Principle 1: Transparent
- [1.1 Origin Declaration](guidelines/1.1-origin-declaration.md)
- [1.2 Authorship Attribution](guidelines/1.2-authorship-attribution.md)
- [1.3 Tool Disclosure](guidelines/1.3-tool-disclosure.md)

### Principle 2: Accurate
- [2.1 Truthful Declaration](guidelines/2.1-truthful-declaration.md)
- [2.2 Role Accuracy](guidelines/2.2-role-accuracy.md)
- [2.3 Versioning](guidelines/2.3-versioning.md)

### Principle 3: Machine-Readable
- [3.1 Structured Format](guidelines/3.1-structured-format.md)
- [3.2 Discoverability](guidelines/3.2-discoverability.md)
- [3.3 Interoperability](guidelines/3.3-interoperability.md)

### Principle 4: Practical
- [4.1 Progressive Complexity](guidelines/4.1-progressive-complexity.md)
- [4.2 Minimal Burden](guidelines/4.2-minimal-burden.md)
- [4.3 Implementation Flexibility](guidelines/4.3-implementation-flexibility.md)

## Techniques

### Implementation Formats
- [HTML Meta Tag](techniques/html-meta-tag.md)
- [JSON-LD Structured Data](techniques/json-ld.md)
- [HTTP Headers](techniques/http-header.md)
- [Frontmatter](techniques/frontmatter.md)

### Supporting Techniques
- [Role Vocabulary](techniques/role-vocabulary.md)
- [Version History](techniques/version-history.md)
- [Process Log](techniques/process-log.md)
- [Conformance Testing](techniques/conformance-testing.md)
- [Quick Start](techniques/quick-start.md)

## Three Layers

Following the Creative Commons model, OpenOrigin operates in three layers:

1. **Human-readable** — Plain language summaries and badges
2. **Machine-readable** — Meta tags, JSON-LD, HTTP headers
3. **Specification** — This document, defining terms, levels, and validation
