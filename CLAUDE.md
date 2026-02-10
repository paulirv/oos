# CLAUDE.md

## Project Overview

**OpenOrigin Specification (OOS)** — An open specification for declaring the origin and creation process of web content. "WCAG for content transparency."

- **Author:** Paul Irving, Insite Web Publishing, Inc.
- **Domain:** openorigin.dev (registered 2026-02-08)
- **Repo:** ~/projects/oos

## Project Structure

```
oos/
├── spec/                    # The specification itself
│   ├── principles/          # Foundational principles
│   ├── guidelines/          # Guidelines under each principle
│   ├── success-criteria/    # Conformance levels (L1, L2, L3)
│   └── techniques/          # Implementation techniques
├── research/                # Prior art analysis, competitive landscape
├── examples/                # Reference implementations
│   ├── html/                # Meta tags, JSON-LD, microdata
│   ├── http/                # HTTP header examples
│   └── frontmatter/         # Static content frontmatter
├── docs/                    # Project documentation
│   └── original-idea.md     # Founding concept document
└── .claude/                 # Claude Code tooling (BoB)
```

## Design Principles

1. **Modeled on WCAG** — Principles > Guidelines > Success Criteria > Techniques
2. **Three conformance levels** — L1 (Basic), L2 (Detailed), L3 (Full)
3. **Three layers (a la Creative Commons)** — Human-readable, machine-readable, legal
4. **Practical first** — L1 is literally one meta tag. Complexity is opt-in.
5. **Complementary to C2PA** — Content process declaration, not cryptographic provenance.

## Four Principles

- **Transparent** — Content origin is openly declared
- **Accurate** — Declarations truthfully represent the creation process
- **Machine-Readable** — Declarations use standardized, parseable formats
- **Practical** — Conformance is achievable for publishers of any size

## Key Decisions

- Spec is self-declared (like WCAG), not enforced
- Dogfood on peabod.com articles as reference implementation
- Target web developers as primary audience
- .dev domain chosen for developer credibility

## Workflow

- Research goes in `research/`
- Spec drafts go in `spec/`
- Working examples go in `examples/`
- Use `/requirement` for tracking spec development milestones
- Use `/journal decision` for spec design choices
