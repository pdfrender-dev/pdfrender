# pdfrender

**HTML and CSS to PDF, without a headless browser**

pdfrender turns HTML and CSS into PDF over a REST API and an MCP server. WeasyPrint 70 lays out the pages, with paper size, margins, headers, footers and page numbers set in CSS. It runs no JavaScript and fetches no URLs, so images and fonts go in as data: URIs. Limits are 2 MB of HTML and 50 pages per render. The servers are in Germany. The free plan has 100 credits a month and needs no card.

## Links

- **Website:** https://pdfrender.dev/go/github
- **API docs:** https://api.pdfrender.dev/docs · [OpenAPI](https://api.pdfrender.dev/openapi.json)
- **Pricing:** https://pdfrender.dev/pricing
- **Render HTML free:** https://pdfrender.dev/tools/html-to-pdf
- **llms.txt:** https://pdfrender.dev/llms.txt

## MCP server

Streamable-HTTP endpoint: `https://api.pdfrender.dev/mcp/` — the anonymous
tier works without a key; an API key raises the limits.

Claude Code:

```sh
claude mcp add --transport http pdfrender https://api.pdfrender.dev/mcp/
```

Cursor / Windsurf / Cline / Claude Desktop:

```json
{
  "mcpServers": {
    "pdfrender": {
      "url": "https://api.pdfrender.dev/mcp/"
    }
  }
}
```

One-click installs for every client: https://pdfrender.dev/connect

## API

Base URL `https://api.pdfrender.dev/` — authenticate with an `X-API-Key` header;
anonymous calls work at a lower rate limit.
