# WCAG Structure Analysis

How WCAG is structured and what OOS can learn from it.

## Status: Draft

## WCAG Architecture

```
Principles (4)
  └── Guidelines (13)
        └── Success Criteria (~78)
              └── Techniques (hundreds)
                    ├── Sufficient (meet the criterion)
                    └── Advisory (exceed the criterion)
```

## What OOS Borrows

### Conformance Levels
- WCAG: A, AA, AAA
- OOS: L1 (Basic), L2 (Detailed), L3 (Full)

WCAG lesson: AA is the practical target. AAA is aspirational. OOS should make L1 the easy entry and L2 the practical target.

### Self-Declaration Model
WCAG conformance is self-declared. There's no enforcement body. Accountability comes from:
1. Community norms
2. Automated testing tools
3. Legal requirements in some jurisdictions (ADA, EU)
4. Reputational incentive

OOS follows the same model. Publishers self-declare. Tools can validate. Trust builds over time.

### Normative vs. Informative
- Normative: Must follow to conform (principles, guidelines, success criteria)
- Informative: Helpful but not required (techniques, understanding docs)

OOS should clearly separate normative spec from informative guidance.

## What OOS Does Differently

| Aspect | WCAG | OOS |
|--------|------|-----|
| Subject | Accessibility of web content | Origin/process of web content |
| Complexity | 78 success criteria | Target ~20 success criteria |
| Audience | Web developers (accessibility) | Web developers (content transparency) |
| Testing | Largely automatable | Declaration validation (format), not truth verification |
| Scope | Single page/application | Per-content-item |

## Key Takeaways

1. **Simple entry point matters** — WCAG Level A gets people started
2. **Techniques are separate from criteria** — Criteria say what, techniques say how
3. **Understanding documents are valuable** — Explain the why behind each criterion
4. **Conformance claims are specific** — "This page conforms to WCAG 2.1 Level AA"
5. **Backwards compatibility** — WCAG 2.0 conformance ⊂ WCAG 2.1 conformance
