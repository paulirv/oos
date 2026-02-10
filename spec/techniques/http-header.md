# Technique: HTTP Headers

**ID:** T-HTTP-HEADER
**Type:** Sufficient for L1, Supporting for L2
**Applies to:** Any HTTP response (pages, APIs, assets)

## Description

HTTP response headers provide origin declarations at the transport layer. Ideal for API responses and server-side declarations.

## L1 Implementation

```http
OpenOrigin: human-ai-assisted
```

### Valid Values

Same controlled vocabulary as the HTML meta tag.

## L2 Supplement

```http
OpenOrigin: human-ai-assisted
OpenOrigin-Detail: category="human-ai-assisted"; author="Jane Smith"; tool="Claude"; tool-role="research"
```

The `OpenOrigin-Detail` header uses Structured Fields syntax (RFC 8941).

## Use Cases

- **API responses** — Declare origin of API-generated content
- **CDN/proxy** — Add origin headers at the edge
- **Server-rendered pages** — Set alongside HTML meta tags

## Benefits

- Works for any content type (HTML, JSON, images, PDFs)
- Set at the server/CDN level without modifying content
- Discoverable by any HTTP client

## Limitations

- Not visible in saved/cached HTML
- Lost when content is copied or re-published
- Limited structured data capacity
