# Technique: Quick Start

**ID:** T-QUICK-START
**Type:** Advisory
**Applies to:** Any publisher implementing OpenOrigin for the first time

## Description

This guide gets a publisher to L1 conformance in under 5 minutes. It covers the four implementation paths and helps publishers choose the right one.

## Step 1: Determine Your Origin Category

Ask yourself: **Who drove the creative process?**

| Answer | Category | Value |
|--------|----------|-------|
| I wrote it. No AI involved. | Human | `human` |
| I wrote it, but used AI to help (research, editing, suggestions). | AI-Assisted | `ai-assisted` |
| AI created it, but I reviewed, edited, or directed it. | AI-Created | `ai-created` |
| AI created it. I didn't meaningfully change it. | AI-Generated | `ai-generated` |

If you're unsure between `ai-assisted` and `ai-created`, ask: **Did I drive, or did the AI drive?** If you drove the process and the AI helped, it's `ai-assisted`. If the AI produced the content and you shaped or approved it, it's `ai-created`.

## Step 2: Add the Declaration

Pick the method that fits your setup:

### HTML Page

Add to your `<head>`:

```html
<meta name="openorigin" content="ai-assisted">
```

### HTTP Header

Add to your server response:

```
OpenOrigin: ai-assisted
```

### Markdown / Static Site

Add to your frontmatter:

```yaml
---
openorigin: ai-assisted
---
```

### API Response

Add the header to your API responses:

```
OpenOrigin: ai-created
```

## Step 3: Done

That's L1 conformance. One declaration, one value, in a standard location.

## What's Next?

When you're ready for more detail:

- **L2** adds who (authors), what (tools), and when (dates). See [Level 2](../success-criteria/level-2.md).
- **L3** adds the full story (process narrative, contribution details, version history). See [Level 3](../success-criteria/level-3.md).

L2 requires JSON-LD or structured frontmatter. A minimal L2 declaration:

```json
{
  "@context": "https://openorigin.dev/schema/v1",
  "@type": "ContentOrigin",
  "conformance": "L2",
  "origin": "ai-assisted",
  "authors": [{ "name": "Your Name", "role": "author" }],
  "tools": [{ "name": "Claude", "provider": "Anthropic", "role": "editing" }],
  "datePublished": "2026-02-10"
}
```

## Common Questions

**Do I need to declare `human` origin?**
Yes, if you want to claim conformance. The declaration is the act of transparency. Saying "no AI was used" is valuable information.

**What if different sections used AI differently?**
At L1, declare the category that best describes the overall content. At L2+, you can provide more detail about specific roles.

**What if I used AI for research but wrote everything myself?**
That's `ai-assisted`. The AI was a tool in your process, even if it didn't write any final text.

**Does using spell-check or grammar tools count as AI?**
No. Conventional software tools (spell-checkers, grammar checkers, search engines) that operate on deterministic rules are not AI tools under this specification. See [Definitions](../definitions.md).
