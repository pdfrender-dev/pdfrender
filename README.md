# pdfrender

[![smithery badge](https://smithery.ai/badge/podshalocef/pdfrender)](https://smithery.ai/servers/podshalocef/pdfrender)

**HTML and CSS to PDF API and MCP server. WeasyPrint with page headers, footers and page numbers, no headless browser. Hosted in Germany.**

pdfrender turns HTML and CSS into PDF over a REST API and an MCP server. WeasyPrint 70 lays out the pages, with paper size, margins, headers, footers and page numbers set in CSS. It runs no JavaScript and fetches no URLs, so images and fonts go in as data: URIs. Limits are 2 MB of HTML and 50 pages per render. The servers are in Germany. The free plan has 100 credits a month and needs no card.

## Quickstart

Render HTML to a PDF in one call. The anonymous tier needs no key; add
`-H "X-API-Key: $PDFRENDER_API_KEY"` for your plan's limits.

```sh
curl -X POST https://api.pdfrender.dev/v1/render \
  -H 'content-type: application/json' \
  -d '{"html":"<h1>Hello</h1>"}' -o hello.pdf
```

The response is the PDF itself (`content-type: application/pdf`), saved as
`hello.pdf`. Page size, margins, headers, footers and page numbers are set in
the HTML's print CSS.

## Use it from

### MCP server

Streamable-HTTP endpoint: `https://api.pdfrender.dev/mcp/` — the anonymous
tier works without a key; an API key raises the limits.

Claude Code:

```sh
claude mcp add --transport http pdfrender https://api.pdfrender.dev/mcp/
```

Claude Code: `/plugin marketplace add pdfrender-dev/pdfrender` then `/plugin install pdfrender@pdfrender` (set `PDFRENDER_API_KEY` for your key).

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

**Integrations** (n8n, Zapier, Make, Dify, SDKs and templates): https://github.com/pdfrender-dev/pdfrender-integrations

## Templates

Ready-made workflows: https://pdfrender.dev/templates

## Links

- **Website:** https://pdfrender.dev/go/github
- **API docs:** https://api.pdfrender.dev/docs · [OpenAPI](https://api.pdfrender.dev/openapi.json)
- **Pricing:** https://pdfrender.dev/pricing
- **Render HTML free:** https://pdfrender.dev/tools/html-to-pdf
- **llms.txt:** https://pdfrender.dev/llms.txt
- **Privacy policy:** https://pdfrender.dev/privacy
- **Support:** https://pdfrender.dev/support

## API

Base URL `https://api.pdfrender.dev/` — authenticate with an `X-API-Key` header;
anonymous calls work at a lower rate limit.

## About the files here

- `.claude-plugin/` — Claude Code plugin, with this repo as its own marketplace.
- `.mcp.json` — the MCP server the Claude Code plugin connects to.
- `gemini-extension.json` — Gemini CLI extension manifest.
- `glama.json` — Glama server claim (names the maintainer).
- `mcp.json` — Agent Plugins 1.0 MCP server config.
- `plugin.json` — Agent Plugins 1.0 plugin manifest.
- `server.json` — the entry in the official MCP Registry.
- `skills/` — an Agent Skill (agentskills.io SKILL.md) for skill galleries.
