# Level 3: Full Conformance

Complete provenance chain with process narrative and audit trail. Builds on all L1 and L2 criteria.

## Required (in addition to all L1 and L2 criteria)

| ID | Guideline | Criterion |
|----|-----------|-----------|
| 1.1.3 | Origin Declaration | Content includes a complete creation process narrative |
| 1.2.2 | Authorship Attribution | Specific contributions of each human participant are described |
| 1.3.2 | Tool Disclosure | Tool versions, configurations, and specific usage are documented |
| 2.1.2 | Truthful Declaration | Publisher maintains records supporting the declared origin |
| 2.2.2 | Role Accuracy | Human and AI contributions are individually characterized |
| 2.3.2 | Versioning | Declaration history is preserved when content is substantially revised |
| 4.1.3 | Progressive Complexity | L3 declarations include all L1 and L2 required fields |

## What L3 Looks Like

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "OpenOrigin",
  "origin": "ai-assisted",
  "conformance": "L3",
  "author": {
    "name": "Jane Smith",
    "role": "primary-author",
    "contributions": ["outline", "research direction", "final editing", "fact verification"]
  },
  "tools": [
    {
      "name": "Claude",
      "provider": "Anthropic",
      "version": "Opus 4",
      "role": "drafting",
      "usage": "Generated initial draft from author's outline and notes",
      "configuration": {
        "temperature": "default",
        "systemPrompt": false
      }
    }
  ],
  "process": {
    "description": "Author created detailed outline and research notes. AI generated first draft from outline. Author rewrote introduction, verified all claims, added personal anecdotes, and edited for voice.",
    "stages": [
      {"stage": "research", "actor": "human", "description": "Author researched topic over 3 days"},
      {"stage": "outline", "actor": "human", "description": "Author wrote detailed section outline"},
      {"stage": "drafting", "actor": "ai", "description": "AI generated draft from outline"},
      {"stage": "editing", "actor": "human", "description": "Author substantially rewrote and edited"},
      {"stage": "review", "actor": "human", "description": "Author fact-checked all claims"}
    ]
  },
  "date": "2026-02-10",
  "history": [
    {"date": "2026-02-10", "origin": "ai-assisted", "note": "Initial publication"}
  ]
}
```

## Notes

L3 is aspirational for most publishers. It's designed for:
- Newsrooms with editorial transparency policies
- Academic publishers
- Government content with accountability requirements
- Publishers who want to lead on transparency

L3 is not expected to be widely adopted initially. Its existence defines the ceiling and gives early adopters something to aim for.
