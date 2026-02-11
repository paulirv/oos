# Level 1: Basic Conformance

The minimum viable declaration. One element declaring content origin category.

## Required

| ID | Guideline | Criterion |
|----|-----------|-----------|
| 1.1.1 | Origin Declaration | Content includes a basic origin category declaration |
| 2.1.1 | Truthful Declaration | The declared origin category accurately reflects the creation process |
| 3.1.1 | Structured Format | Declaration uses a recognized OpenOrigin format |
| 3.2.1 | Discoverability | Declaration is in a standard location for its format |
| 3.3.1 | Interoperability | At least one recognized format is used |
| 4.1.1 | Progressive Complexity | L1 declarations are valid without L2/L3 data |
| 4.2.1 | Minimal Burden | Conformance is achievable with a single declaration element |
| 4.3.1 | Implementation Flexibility | Any recognized format achieves conformance |

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
