# Level 1: Basic Conformance

The minimum viable declaration. One element declaring content origin category.

## Required

| ID | Guideline | Criterion |
|----|-----------|-----------|
| 1.1.1 | Origin Declaration | Content MUST include an origin category from the L1 vocabulary |
| 2.1.1 | Truthful Declaration | The declared origin category MUST accurately reflect the creation process |
| 3.1.1 | Structured Format | Declaration MUST use a recognized OpenOrigin format |
| 3.2.1 | Discoverability | Declaration MUST be in a standard location for its format |

## Origin Categories (L1 Vocabulary)

The L1 origin category is a single value from a controlled vocabulary:

| Value | Meaning |
|-------|---------|
| `human` | Content created entirely by humans, no AI tools used in creation |
| `ai-assisted` | Human-created with AI assistance (research, editing, suggestions) |
| `ai-created` | AI-generated with human oversight (editing, review, approval) |
| `ai-generated` | AI-generated with no meaningful human input |

The distinction between `ai-assisted` (human-led) and `ai-created` (AI-led) is the key boundary. In `ai-assisted`, a human drove the creative process and used AI as a tool. In `ai-created`, AI produced the primary content and a human shaped or approved it.

For more granular role descriptions (editor vs. reviewer vs. approver), see L2 conformance.

### Interoperability Mapping

| OpenOrigin | IETF AI-Disclosure | dweekly HTML |
|------------|-------------------|--------------|
| `human` | `none` | `none` |
| `ai-assisted` | `ai-modified` | `ai-assisted` |
| `ai-created` | `ai-originated` | `ai-generated` |
| `ai-generated` | `machine-generated` | `autonomous` |

## What L1 Looks Like

```html
<!-- HTML meta tag — the simplest implementation -->
<meta name="openorigin" content="ai-assisted">
```

```
# HTTP header
OpenOrigin: ai-assisted
```

```yaml
# Frontmatter
openorigin: ai-assisted
```

That's it. One declaration. L1 conformance achieved.
