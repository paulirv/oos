# Technique: Version History

**ID:** T-VERSION-HISTORY
**Type:** Supporting for L2, Sufficient for L3
**Applies to:** Content that is updated after initial publication

## Description

Declarations should reflect the current state of content, not just its original creation. When content is substantially revised — especially when the nature of AI involvement changes — the declaration MUST be updated (SC 2.3.1, 2.3.2).

At L2, a date field tracks when the declaration was last updated. At L3, a full history array preserves the record of changes over time.

## L2 Implementation

Include `datePublished` and `dateModified` in the declaration:

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin",
  "conformance": "L2",
  "origin": "ai-assisted",
  "datePublished": "2026-02-01",
  "dateModified": "2026-03-15"
}
```

When `dateModified` differs from `datePublished`, consumers know the declaration has been updated since initial publication.

## L3 Implementation

Add a `history` array that records each significant change to the declaration:

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin",
  "conformance": "L3",
  "origin": "ai-assisted",
  "datePublished": "2026-02-01",
  "dateModified": "2026-03-15",
  "history": [
    {
      "date": "2026-02-01",
      "origin": "human",
      "note": "Initial publication, written entirely by author"
    },
    {
      "date": "2026-03-15",
      "origin": "ai-assisted",
      "note": "Substantial revision using AI to rewrite technical sections"
    }
  ]
}
```

### History Entry Fields

| Field | Required | Description |
|-------|----------|-------------|
| `date` | Yes | ISO 8601 date of the change |
| `origin` | Yes | The origin category at that point in time |
| `note` | Yes | Brief description of what changed and why the origin category changed (if it did) |

## When to Update

A declaration MUST be updated when content is **substantially revised** (see [Definitions](../definitions.md)). In practice:

| Change | Update required? |
|--------|-----------------|
| Fix typos | No |
| Formatting changes | No |
| Minor copy edits | No |
| Rewrite a section | Yes |
| Add AI-generated content to human-written article | Yes — origin category may change |
| Translate content using AI | Yes |
| Update factual claims | Yes |

## Benefits

- Consumers can see when a declaration was last reviewed
- History preserves transparency through content evolution
- Enables trust even for frequently updated content

## Limitations

- Requires publisher discipline to update declarations on revision
- History can grow long for frequently updated content
- No mechanism to verify history entries are complete
