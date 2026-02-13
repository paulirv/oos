# Technique: Role Vocabulary

**ID:** T-ROLE-VOCAB
**Type:** Sufficient for L2-L3
**Applies to:** Any declaration that includes role information

## Description

OpenOrigin defines two controlled vocabularies for roles: one for AI tools and one for human contributors. Using these vocabularies satisfies the role accuracy requirements of Guideline 2.2.

## AI Role Vocabulary

Used in the `tools[].role` field. Declarations MUST use one or more values from this list.

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

### Extensibility

The AI role vocabulary is extensible. Implementations MAY include additional values prefixed with `x-` (e.g., `x-image-generation`, `x-data-analysis`, `x-summarization`). Future specification versions MAY promote `x-` values to standard values.

## Author Role Vocabulary

Used in the `authors[].role` field. See [Definitions: Author Role Vocabulary](../definitions.md#author-role-vocabulary) for the normative list.

| Value | Meaning |
|-------|---------|
| `author` | Primary content creator |
| `editor` | Revised or shaped the content |
| `reviewer` | Reviewed content for accuracy or quality |
| `translator` | Translated content between languages |
| `curator` | Selected, organized, or compiled content |
| `approver` | Authorized publication without substantive content changes |

Author roles follow the same `x-` extensibility convention as AI roles.

## Usage Examples

### L2 — Single AI tool, single author

```json
{
  "authors": [{ "name": "Jane Smith", "role": "author" }],
  "tools": [{ "name": "Claude", "provider": "Anthropic", "role": "editing" }]
}
```

### L2 — Multiple tools with different roles

```json
{
  "tools": [
    { "name": "Claude", "provider": "Anthropic", "role": "drafting" },
    { "name": "DeepL", "provider": "DeepL SE", "role": "translation" }
  ]
}
```

### L3 — Multiple contributors with specific contributions

```json
{
  "authors": [
    {
      "name": "Jane Smith",
      "role": "author",
      "contributions": ["research", "outline", "final editing"]
    },
    {
      "name": "Bob Lee",
      "role": "editor",
      "contributions": ["structural editing", "fact verification"]
    }
  ]
}
```

## Choosing the Right AI Role

| If the AI... | Use role |
|--------------|----------|
| Found sources or data for you | `research` |
| Helped brainstorm or outline | `ideation` |
| Wrote prose that you then edited | `drafting` |
| Edited or improved your writing | `editing` |
| Translated content between languages | `translation` |
| Wrote or helped write code | `coding` |
| Reviewed your work for errors | `review` |

When an AI tool performed multiple roles, list the tool multiple times with different roles, or use the most significant role.

## Benefits

- Consistent vocabulary enables cross-site comparison
- Extensibility prevents the vocabulary from blocking adoption
- Clear decision guide reduces publisher confusion

## Limitations

- Role boundaries are sometimes subjective (e.g., ideation vs. drafting)
- The vocabulary cannot capture every nuance of AI involvement
- Publishers must exercise judgment in role selection
