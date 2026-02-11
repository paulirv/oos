---
title: "Example Blog Post"
date: 2026-02-10
author: Jane Smith
openorigin: ai-assisted
openorigin_detail:
  conformance: L2
  author:
    name: Jane Smith
    role: primary-author
  tools:
    - name: Claude
      provider: Anthropic
      role: editing
---

# Example Blog Post

This is an example of a static site blog post with OpenOrigin frontmatter.

The `openorigin` field alone achieves L1 conformance.

The `openorigin_detail` block adds L2 structured data for static site generators
that can render it as JSON-LD or meta tags at build time.

## For Static Site Generators

Hugo, Eleventy, Astro, Next.js, and other SSGs can read frontmatter and output
the appropriate HTML meta tags or JSON-LD in the page `<head>`.

A simple template partial:

```html
<!-- L1 -->
<meta name="openorigin" content="{{ openorigin }}">
```
