# Technique: HTML Meta Tag

**ID:** T-HTML-META
**Type:** Sufficient for L1, Supporting for L2+
**Applies to:** HTML web pages

## Description

The simplest implementation path. A single `<meta>` tag in the document `<head>` declares the content origin category.

## L1 Implementation

```html
<meta name="openorigin" content="ai-assisted">
```

### Valid Values

| Value | Meaning |
|-------|---------|
| `human` | Content created entirely by humans, no AI tools used in creation |
| `ai-assisted` | Human-created with AI assistance (research, editing, suggestions) |
| `ai-created` | AI-generated with human oversight (editing, review, approval) |
| `ai-generated` | AI-generated with no meaningful human input |

### Placement

The `<meta>` tag MUST be placed in the document `<head>` element, before the closing `</head>` tag.

## L2 Supplement

For L2 conformance, the meta tag is supplemented (not replaced) by JSON-LD:

```html
<head>
  <meta name="openorigin" content="ai-assisted">
  <script type="application/ld+json">
    { "@context": "https://openorigin.dev/schema/v1", ... }
  </script>
</head>
```

## Benefits

- Zero dependencies
- Works in any HTML page
- Discoverable by crawlers without JavaScript
- Trivial to implement in any CMS or template

## Limitations

- Cannot express L2/L3 detail alone
- Limited to one value (no structured data)
- Only works for HTML documents (not API responses)
