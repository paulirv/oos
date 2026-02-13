# Technique: Conformance Testing

**ID:** T-CONFORMANCE
**Type:** Advisory
**Applies to:** Publishers and tool developers validating conformance claims

## Description

This technique describes how to validate that content meets the requirements of a claimed conformance level. OpenOrigin success criteria fall into two categories: machine-testable (structure and format) and non-machine-testable (accuracy and truthfulness).

## Machine-Testable Criteria

These criteria can be checked by automated validators:

### L1 Checks

| SC | Test |
|----|------|
| 1.1.1 | Declaration contains a value from the L1 vocabulary (`human`, `ai-assisted`, `ai-created`, `ai-generated`) |
| 3.1.1 | Declaration uses a recognized format (html-meta, json-ld, http-header, frontmatter) |
| 3.2.1 | Declaration is in a standard location (meta in `<head>`, JSON-LD in `<script>`, header in HTTP response) |

### L2 Checks (in addition to L1)

| SC | Test |
|----|------|
| 1.1.2 | Declaration contains structured origin data with roles and tools |
| 1.2.1 | At least one entry in `authors` array with `name` or `role` |
| 1.3.1 | `tools` array present (may be empty for `human` origin) |
| 2.2.1 | Each tool's `role` value is from the L2 AI role vocabulary or uses `x-` prefix |
| 2.3.1 | `datePublished` or `dateModified` field is present and valid ISO 8601 |
| 3.1.2 | JSON-LD validates against the OpenOrigin schema |
| 3.2.2 | Declaration is present in initial HTML (not injected by JavaScript) |
| 3.3.1 | When multiple formats exist, origin category is the same across all |
| 4.1.1 | All L1 required fields are present |

### L3 Checks (in addition to L1 and L2)

| SC | Test |
|----|------|
| 1.1.3 | `process` object present with `description` and `stages` array |
| 1.2.2 | Each author entry has a `contributions` array |
| 1.3.2 | Each tool entry has a `version` and `usage` field |
| 2.3.2 | `history` array is present with at least one entry |
| 4.1.2 | All L1 and L2 required fields are present |

## Non-Machine-Testable Criteria

These criteria require human judgment:

| SC | What to assess |
|----|----------------|
| 2.1.1 (L1) | Does the declared origin category match how the content was actually created? |
| 2.1.2 (L3) | Can the publisher produce records supporting the declaration? |
| 2.2.2 (L3) | Are individual human and AI contributions accurately characterized? |

These are analogous to WCAG criteria that require human evaluation (e.g., "link purpose is clear"). Automated tools SHOULD flag these for manual review rather than auto-passing.

## Validation Pseudocode

```
function validateL1(content):
  declaration = findDeclaration(content)
  if not declaration: FAIL "No declaration found"
  if declaration.origin not in ["human", "ai-assisted", "ai-created", "ai-generated"]:
    FAIL "Invalid origin category"
  if not isStandardLocation(declaration): FAIL "Not in standard location"
  PASS

function validateL2(content):
  if not validateL1(content): FAIL
  if not declaration.authors or len(declaration.authors) == 0:
    if declaration.origin != "ai-generated": FAIL "Authors required"
  if declaration.origin != "human":
    if not declaration.tools or len(declaration.tools) == 0:
      FAIL "Tools required for non-human origin"
    for tool in declaration.tools:
      if not isValidAIRole(tool.role): FAIL "Invalid AI role"
  if not declaration.datePublished and not declaration.dateModified:
    FAIL "Date required"
  PASS
```

## Benefits

- Clear separation of automated vs. manual testing
- Enables consistent validator implementations
- Pseudocode provides unambiguous test logic

## Limitations

- Truthfulness cannot be verified by machines
- Schema validation requires the formal schema to be published
- Edge cases in format detection may vary between validators
