# Conformance

## Conformance Levels

OpenOrigin defines three conformance levels. Each level is a superset of the one below it.

| Level | Name | Description | Target Audience |
|-------|------|-------------|-----------------|
| **L1** | Basic | Origin category declaration | Any publisher (bloggers, small sites) |
| **L2** | Detailed | Roles, tools, dates, structured data | Professional publishers, newsrooms |
| **L3** | Full | Complete provenance chain with process narrative | Enterprise, academic, government |

## Claiming Conformance

Conformance is self-declared, following the WCAG model. A conformance claim states:

> This [content/page/site] conforms to OpenOrigin Specification v[version] Level [L1/L2/L3].

### Conformance Claim Requirements

1. The conformance level claimed (L1, L2, or L3)
2. The specification version (e.g., "OpenOrigin 1.0")
3. The scope of the claim (specific page, section, or entire site)

### Scope

| Scope | Meaning |
|-------|---------|
| **Page** | This specific page conforms |
| **Section** | This section of content conforms |
| **Site** | All content on this site conforms |

Site-level claims are the strongest but require consistent implementation.

## Partial Conformance

There is no partial conformance. Content either meets all criteria for a level or it doesn't. However:

- A site can have some pages at L2 and others at L1
- Conformance is per-content-item, not all-or-nothing for a domain

## Relationship Between Levels

```
L3 ⊃ L2 ⊃ L1
```

- L1 conformance: meets all L1 success criteria
- L2 conformance: meets all L1 AND L2 success criteria
- L3 conformance: meets all L1, L2, AND L3 success criteria

## Validation

### Automated Validation
Format and structure can be validated automatically:
- Is the meta tag present?
- Does the JSON-LD validate against the schema?
- Are required fields present for the claimed level?

### Truth Validation
Accuracy of declarations cannot be validated automatically. Like WCAG, OpenOrigin relies on:
- Publisher integrity
- Community norms and expectations
- Optional third-party review
- Reputational accountability
