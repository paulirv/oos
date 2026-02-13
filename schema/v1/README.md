# OpenOrigin Schema v1

Machine-readable schema for OpenOrigin content origin declarations.

## Files

| File | Purpose |
|------|---------|
| `context.jsonld` | JSON-LD context document — maps property names to IRIs |
| `openorigin.schema.json` | JSON Schema (Draft 2020-12) — validates declarations |

## Types

### ContentOrigin

The root type for all OpenOrigin declarations.

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin"
}
```

### Author

A human contributor to the content.

| Property | Type | L2 | L3 | Description |
|----------|------|----|----|-------------|
| `name` | string | Required* | Required* | Name of the contributor |
| `role` | string (enum) | Required* | Required* | Role from the author vocabulary |
| `contributions` | string[] | -- | Required | Specific contributions made |

*At least one of `name` or `role` is required.

### Tool

An AI tool used in the creation process.

| Property | Type | L2 | L3 | Description |
|----------|------|----|----|-------------|
| `name` | string | Required | Required | Name of the tool |
| `provider` | string | Optional | Optional | Organization providing the tool |
| `role` | string (enum) | Required | Required | Role from the AI role vocabulary |
| `version` | string | -- | Required | Version of the tool |
| `usage` | string | -- | Required | How the tool was used |

### ProcessStage

A stage in the content creation process (L3 only).

| Property | Type | Description |
|----------|------|-------------|
| `stage` | string | Name of the process stage |
| `actor` | `"human"` \| `"ai"` | Who performed this stage |
| `description` | string | What happened in this stage |

### HistoryEntry

A record of a significant change to the declaration (L3 only).

| Property | Type | Description |
|----------|------|-------------|
| `date` | ISO 8601 date | When the change occurred |
| `origin` | origin category | The origin category at that point |
| `note` | string | What changed |

## Properties by Level

### L1 (Basic)

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `@context` | string \| array | Yes | `"https://openorigin.dev/schema/v1"` |
| `@type` | string | Yes | `"ContentOrigin"` |
| `origin` | string (enum) | Yes | Origin category |

### L2 (Detailed) — includes all L1 properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `conformance` | string | Yes | `"L2"` |
| `authors` | Author[] | Yes | Human contributors |
| `tools` | Tool[] | No* | AI tools used |
| `datePublished` | ISO 8601 date | Yes | Publication date |
| `dateModified` | ISO 8601 date | No | Last modification date |

*Required when origin is not `human`.

### L3 (Full) — includes all L1 and L2 properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `conformance` | string | Yes | `"L3"` |
| `dateModified` | ISO 8601 date | Yes | Last modification date |
| `process` | object | Yes | Creation process description |
| `process.description` | string | Yes | Narrative of the creation process |
| `process.stages` | ProcessStage[] | Yes | Ordered list of creation stages |
| `history` | HistoryEntry[] | Yes | Record of declaration changes |

## Enumerations

### Origin Categories (L1 Vocabulary)

| Value | Meaning |
|-------|---------|
| `human` | Created entirely by humans, no AI tools used |
| `ai-assisted` | Human-created with AI assistance |
| `ai-created` | AI-generated with human oversight |
| `ai-generated` | AI-generated with no meaningful human input |

### AI Roles (L2 Vocabulary)

| Value | Meaning |
|-------|---------|
| `none` | No AI involvement |
| `research` | Research, fact-finding, or information gathering |
| `ideation` | Brainstorming, outlining, or concept development |
| `drafting` | Generated prose or content drafts |
| `editing` | Edited, revised, or improved human-written content |
| `translation` | Language translation |
| `coding` | Code generation or assistance |
| `review` | Fact-checking, proofreading, or quality review |

Extensions: use `x-` prefix (e.g., `x-image-generation`).

### Author Roles

| Value | Meaning |
|-------|---------|
| `author` | Primary content creator |
| `editor` | Revised or shaped the content |
| `reviewer` | Reviewed content for accuracy or quality |
| `translator` | Translated content between languages |
| `curator` | Selected, organized, or compiled content |
| `approver` | Authorized publication |

Extensions: use `x-` prefix (e.g., `x-illustrator`).

### Process Stage Actors

| Value | Meaning |
|-------|---------|
| `human` | A human performed this stage |
| `ai` | An AI tool performed this stage |

## Usage

### Standalone Mode

Use the OpenOrigin context as the sole context:

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin",
  "origin": "ai-assisted"
}
```

### Schema.org Integration

Combine with schema.org using a context array. Prefix OpenOrigin properties with `oo:` to avoid collisions:

```json
{
  "@context": [
    "https://schema.org",
    "https://openorigin.dev/schema/v1"
  ],
  "@type": "Article",
  "headline": "Example Article",
  "author": {
    "@type": "Person",
    "name": "Jane Smith"
  },
  "oo:origin": {
    "@type": "oo:ContentOrigin",
    "oo:origin": "ai-assisted",
    "oo:conformance": "L2",
    "oo:authors": [
      { "name": "Jane Smith", "role": "author" }
    ],
    "oo:tools": [
      { "name": "Claude", "provider": "Anthropic", "role": "editing" }
    ],
    "oo:datePublished": "2026-02-10"
  }
}
```

### Validation

Validate declarations against `openorigin.schema.json` using any JSON Schema Draft 2020-12 validator:

```bash
# Using ajv-cli
ajv validate -s openorigin.schema.json -d declaration.json

# Using Python jsonschema
python -m jsonschema -i declaration.json openorigin.schema.json
```
