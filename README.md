# Pdfrender

**Turn HTML into pixel-faithful PDFs.**

pdfrender turns HTML into pixel-faithful PDFs over a simple REST API and an MCP server. Anonymous calls work with no signup; an optional API key raises limits. Usage is metered in credits — one render costs one credit. The free tier is 100 credits/month (no card); Essential is €20/mo for 10,000 credits and Scale is €80/mo for 100,000 — cancel anytime, no other SKUs. Alternatives to Gotenberg, DocRaptor, PDFShift, api2pdf, CraftMyPDF and SelectPdf.

## Links

- **Website:** https://pdfrender.dev/go/github
- **API docs:** https://api.pdfrender.dev/docs · [OpenAPI](https://api.pdfrender.dev/openapi.json)
- **Pricing:** https://pdfrender.dev/pricing
- **Try it free — paste HTML, get a PDF:** https://pdfrender.dev/tools/html-to-pdf
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
