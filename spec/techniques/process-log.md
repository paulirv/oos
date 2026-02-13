# Technique: Process Log

**ID:** T-PROCESS-LOG
**Type:** Advisory for L1-L2, Supporting for L3
**Applies to:** Any publisher maintaining editorial records

## Description

A process log is an internal record of how content was created. It supports the truthfulness requirements of Guideline 2.1 by providing evidence that declarations match reality. At L3, publishers MUST maintain records supporting their declared origin (SC 2.1.2).

Process logs are not published — they are internal documents that a publisher can produce if a declaration is questioned.

## What to Record

| Field | Description | Example |
|-------|-------------|---------|
| Content ID | URL or internal identifier | `https://example.com/article/123` |
| Origin category | L1 declaration value | `ai-assisted` |
| Human contributors | Names and roles | Jane Smith (author), Bob Lee (editor) |
| AI tools used | Tool names and roles | Claude (drafting), Grammarly (editing) |
| Key dates | Creation, revision, publication | Created 2026-02-01, published 2026-02-10 |
| Process notes | What happened in what order | Author outlined, AI drafted, author rewrote |

## Example: Spreadsheet Log

```
| URL                    | Origin       | Author      | AI Tool | AI Role  | Date       | Notes                          |
|------------------------|-------------|-------------|---------|----------|------------|--------------------------------|
| /blog/post-1           | human       | Jane Smith  | —       | —        | 2026-02-01 | Written entirely by author     |
| /blog/post-2           | ai-assisted | Jane Smith  | Claude  | drafting | 2026-02-05 | AI drafted from author outline |
| /api/report/quarterly  | ai-created  | Bob Lee     | Claude  | drafting | 2026-02-10 | AI generated, Bob reviewed     |
```

## Example: Per-Content Log

For L3 conformance, a more detailed per-content record:

```markdown
# Process Log: /blog/post-2

- **2026-02-03:** Author researched topic, collected 5 source articles
- **2026-02-04:** Author wrote detailed outline (12 sections)
- **2026-02-04:** Claude (Opus 4) generated first draft from outline
- **2026-02-05:** Author rewrote introduction and conclusion
- **2026-02-05:** Author fact-checked all claims against sources
- **2026-02-05:** Author edited for voice and tone
- **2026-02-05:** Published as ai-assisted, L2
```

## Benefits

- Provides evidence supporting declaration accuracy
- Useful for editorial accountability and internal audits
- Enables accurate L3 `process.stages` declarations
- Low-tech — a spreadsheet or text file is sufficient

## Limitations

- Not published or machine-readable (internal only)
- Requires editorial discipline to maintain
- No standardized format (this technique is advisory)
- Cannot be validated externally
