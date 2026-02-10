# Principle 3: Machine-Readable

Declarations use standardized, parseable formats.

## Intent

Origin declarations are not just for humans reading an "About" page. They are structured data that search engines, browser extensions, content aggregators, and AI systems can consume programmatically.

## Rationale

The web runs on structured data. For content origin declarations to have impact at scale, they must be machine-readable — discoverable by crawlers, indexable by search engines, and consumable by tools. A human-readable-only declaration is a PDF in a world of APIs.

## Guidelines

- [3.1 Structured Format](../guidelines/3.1-structured-format.md) — Declarations use defined schemas
- [3.2 Discoverability](../guidelines/3.2-discoverability.md) — Declarations are in standard locations
- [3.3 Interoperability](../guidelines/3.3-interoperability.md) — Multiple implementation formats are supported
