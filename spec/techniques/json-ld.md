# Technique: JSON-LD Structured Data

**ID:** T-JSON-LD
**Type:** Sufficient for L1-L3
**Applies to:** HTML web pages, API responses

## Description

JSON-LD (JavaScript Object Notation for Linked Data) provides a rich, structured format for origin declarations. It's the primary format for L2 and L3 conformance.

## L1 Implementation

```html
<script type="application/ld+json">
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin",
  "origin": "ai-assisted"
}
</script>
```

## L2 Implementation

```html
<script type="application/ld+json">
{
  "@context": [
    "https://schema.org",
    "https://openorigin.dev/schema/v1"
  ],
  "@type": "Article",
  "headline": "Article Title",
  "author": {
    "@type": "Person",
    "name": "Jane Smith"
  },
  "oo:origin": {
    "@type": "oo:ContentOrigin",
    "oo:origin": "ai-assisted",
    "oo:conformance": "L2",
    "oo:authors": [
      {
        "name": "Jane Smith",
        "role": "author"
      }
    ],
    "oo:tools": [
      {
        "name": "Claude",
        "provider": "Anthropic",
        "role": "research"
      }
    ],
    "oo:datePublished": "2026-02-10",
    "oo:dateModified": "2026-02-10"
  }
}
</script>
```

## Schema

The OpenOrigin JSON-LD context defines:

| Property | Type | L1 | L2 | L3 |
|----------|------|----|----|-----|
| `origin` | string (enum) | Required | Required | Required |
| `conformance` | string (L1/L2/L3) | Optional | Required | Required |
| `authors` | array of objects | — | Required | Required |
| `tools` | array of objects | — | Required* | Required |
| `datePublished` | date (ISO 8601) | — | Required | Required |
| `dateModified` | date (ISO 8601) | — | Optional | Required |
| `process` | object | — | — | Required |
| `history` | array | — | — | Required |

*When origin is `human`, `tools` MAY be omitted or empty.

## Benefits

- Rich structured data
- Compatible with schema.org
- Understood by search engines
- Supports all conformance levels

## Limitations

- More complex than a meta tag
- Requires understanding of JSON-LD syntax
- Larger payload than meta tag alone
