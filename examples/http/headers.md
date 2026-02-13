# HTTP Header Examples

## L1: Single Header

```http
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
OpenOrigin: ai-assisted
```

## L2: Structured Header

Using the Structured Fields syntax (RFC 8941):

```http
HTTP/1.1 200 OK
Content-Type: application/json
OpenOrigin: ai-assisted
OpenOrigin-Detail: origin="ai-assisted"; author="Jane Smith"; tool="Claude"; tool-role="research"; date="2026-02-10"
```

## API Response Example

For JSON API responses, include origin in the response body or headers:

```http
HTTP/1.1 200 OK
Content-Type: application/json
OpenOrigin: ai-created

{
  "title": "Generated Report",
  "content": "...",
  "_openorigin": {
    "origin": "ai-created",
    "tools": [{"name": "Claude", "role": "drafting"}],
    "authors": [{"name": "API Consumer", "role": "reviewer"}]
  }
}
```

## Notes

- HTTP headers are ideal for API responses where HTML meta tags don't apply
- The `OpenOrigin` header provides L1 conformance
- The `OpenOrigin-Detail` header provides L2 structured data
- For L3, use a `Link` header pointing to a full declaration document
