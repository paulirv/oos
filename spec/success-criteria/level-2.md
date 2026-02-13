# Level 2: Detailed Conformance

Structured breakdown of roles, tools, and process. Builds on all L1 criteria.

## Required (in addition to all L1 criteria)

| ID | Guideline | Criterion |
|----|-----------|-----------|
| 1.1.2 | Origin Declaration | Content MUST include a structured origin breakdown with roles and tools |
| 1.2.1 | Authorship Attribution | Human author or editor MUST be named or identified by role |
| 1.3.1 | Tool Disclosure | AI tools used MUST be identified by name; if no AI tools were used, the tools array MUST be empty or omitted |
| 2.2.1 | Role Accuracy | AI role MUST be described using the defined L2 role vocabulary |
| 2.3.1 | Versioning | Declaration MUST include a date indicating when the declaration was created or last updated |
| 3.1.2 | Structured Format | Declaration MUST validate against the OpenOrigin schema |
| 3.2.2 | Discoverability | Declaration MUST be accessible without JavaScript execution |
| 3.3.1 | Interoperability | When multiple formats are used, declarations MUST convey the same origin information |
| 4.1.1 | Progressive Complexity | L2 declarations MUST include all L1 required fields |

## AI Role Categories (L2 Vocabulary)

Declarations MUST use one or more values from this vocabulary. This vocabulary is extensible: implementations MAY include additional role values prefixed with `x-` (e.g., `x-image-generation`). Future versions of this specification MAY add new standard values.

| Value | Meaning |
|-------|---------|
| `none` | No AI involvement |
| `research` | AI used for research, fact-finding, or information gathering |
| `ideation` | AI used for brainstorming, outlining, or concept development |
| `drafting` | AI generated prose or content drafts |
| `editing` | AI used to edit, revise, or improve human-written content |
| `translation` | AI used for language translation |
| `coding` | AI used for code generation or assistance |
| `review` | AI used for fact-checking, proofreading, or quality review |

### When Origin Is `human`

When the L1 origin category is `human`, L2 conformance still requires authorship attribution (1.2.1) and a declaration date (2.3.1). The `tools` array SHOULD be omitted or empty, and no AI role declaration is required. SC 1.3.1 and 2.2.1 are satisfied by the absence of AI tools.

## What L2 Looks Like

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin",
  "conformance": "L2",
  "origin": "ai-assisted",
  "authors": [
    {
      "name": "Jane Smith",
      "role": "author"
    }
  ],
  "tools": [
    {
      "name": "Claude",
      "provider": "Anthropic",
      "role": "editing"
    }
  ],
  "datePublished": "2026-02-10",
  "dateModified": "2026-02-10"
}
```
