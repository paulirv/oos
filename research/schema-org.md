# Schema.org Metadata Analysis

Existing schema.org types relevant to content origin and how OOS relates.

## Status: Draft

## Relevant Schema.org Types

### CreativeWork
The base type for content. Already supports:
- `author` — Who created it
- `editor` — Who edited it
- `dateCreated` / `dateModified`
- `isBasedOn` — Derivative work reference

### Missing from Schema.org
- AI tool involvement in creation
- Human-AI collaboration roles
- Creation process description
- Origin category (the spectrum from human to AI-generated)

## OOS Relationship to Schema.org

Two possible approaches:

### Option A: Extend Schema.org
Define new properties within the schema.org ecosystem:
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "author": {"@type": "Person", "name": "Jane Smith"},
  "openOrigin": {
    "@type": "ContentOrigin",
    "category": "human-ai-assisted",
    "tools": [...]
  }
}
```

### Option B: Separate Schema (Preferred)
Define an OOS JSON-LD context that can coexist with schema.org:
```json
{
  "@context": [
    "https://schema.org",
    "https://openorigin.dev/schema/v1"
  ],
  "@type": "Article",
  "author": {"@type": "Person", "name": "Jane Smith"},
  "oo:origin": "human-ai-assisted"
}
```

**Option B is preferred** because:
1. OOS can iterate independently of schema.org's governance
2. No waiting for schema.org approval
3. Can later propose schema.org integration once OOS is stable
4. Precedent: many vocabularies use their own context alongside schema.org

## Key Considerations

1. **Don't fight schema.org** — Use it where it applies (author, date), extend where it doesn't (origin, tools, process)
2. **JSON-LD is the bridge** — Both schema.org and OOS speak JSON-LD
3. **Propose upstream later** — Once OOS is stable, propose a ContentOrigin type to schema.org

## Research Questions

- [ ] Is there a pending schema.org proposal for AI-related properties?
- [ ] What's the process for proposing new schema.org types?
- [ ] How do other specs extend schema.org with custom contexts?
