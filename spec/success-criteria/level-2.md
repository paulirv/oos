# Level 2: Detailed Conformance

Structured breakdown of roles, tools, and process. Builds on all L1 criteria.

## Required (in addition to all L1 criteria)

| ID | Guideline | Criterion |
|----|-----------|-----------|
| 1.1.2 | Origin Declaration | Content includes a detailed origin breakdown |
| 1.2.1 | Authorship Attribution | Human author or editor is named or identified by role |
| 1.3.1 | Tool Disclosure | AI tools used are identified by name |
| 2.2.1 | Role Accuracy | AI role is described using defined role categories |
| 2.3.1 | Versioning | Declaration includes a date or version indicator |
| 3.1.2 | Structured Format | Declaration validates against the OpenOrigin schema |
| 3.2.2 | Discoverability | Declaration is accessible without JavaScript execution |
| 3.3.2 | Interoperability | Declarations are equivalent across formats used |
| 4.1.2 | Progressive Complexity | L2 declarations include all L1 required fields |

## AI Role Categories (L2 Vocabulary)

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

## What L2 Looks Like

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "OpenOrigin",
  "origin": "human-ai-assisted",
  "author": {
    "name": "Jane Smith",
    "role": "primary-author"
  },
  "tools": [
    {
      "name": "Claude",
      "provider": "Anthropic",
      "role": "editing"
    }
  ],
  "date": "2026-02-10"
}
```
