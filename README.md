# OpenOrigin Specification (OOS)

An open specification for declaring the origin and creation process of web content.

**Think WCAG for content transparency.** Machine-readable, implementable, auditable.

## What is OpenOrigin?

OpenOrigin defines a standardized way to declare how content was created — not just "was AI involved?" but the full story of authorship, tools, and editorial process.

## Why?

The AI content transparency conversation is stuck in binary mode. The reality is a spectrum from "human wrote everything" to "fully AI-generated." Current standards don't capture this nuance.

## Quick Start

L1 conformance is one meta tag:

```html
<meta name="openorigin" content="human-ai-assisted">
```

That's it. See [spec/success-criteria/level-1.md](spec/success-criteria/level-1.md) for the full L1 specification.

## Principles

1. **Transparent** — Content origin is openly declared
2. **Accurate** — Declarations truthfully represent the creation process
3. **Machine-Readable** — Declarations use standardized, parseable formats
4. **Practical** — Conformance is achievable for publishers of any size

## Conformance Levels

| Level | Name | What it takes |
|-------|------|---------------|
| **L1** | Basic | One declaration — origin category |
| **L2** | Detailed | Structured data — roles, tools, dates |
| **L3** | Full | Complete provenance chain |

## Project Structure

```
spec/                    # The specification
  principles/            # 4 foundational principles
  guidelines/            # 12 guidelines (3 per principle)
  success-criteria/      # L1, L2, L3 conformance levels
  techniques/            # Implementation techniques
  conformance.md         # How to claim conformance
  index.md               # Spec table of contents

research/                # Prior art analysis
  prior-art.md           # Overview and comparison matrix
  wcag-structure.md      # WCAG structural model analysis
  c2pa.md                # C2PA comparison
  creative-commons.md    # CC three-layer model
  schema-org.md          # Schema.org metadata analysis
  eu-ai-act.md           # Regulatory landscape

examples/                # Reference implementations
  html/                  # Meta tags, JSON-LD
  http/                  # HTTP header examples
  frontmatter/           # Static content frontmatter

docs/                    # Project documentation
  original-idea.md       # Founding concept document
```

## Status

Working draft. The spec framework is in place. Active work on:
- Finalizing L1 origin vocabulary
- Defining the JSON-LD schema
- Prior art deep research
- Dogfooding on peabod.com

## Links

- **Spec site:** openorigin.dev (coming soon)
- **Author:** Paul Irving, [Insite Web Publishing, Inc.](https://iwpi.com)

## License

TBD
