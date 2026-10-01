---
name: "pdfrender"
description: "HTML and CSS to PDF MCP server with page headers, footers and page numbers. No headless browser. Use it through the pdfrender MCP server at https://api.pdfrender.dev/mcp/ — the anonymous tier needs no key."
license: "MIT"
compatibility: "Needs network access to https://api.pdfrender.dev/mcp/; an API key is optional."
---

# pdfrender

pdfrender turns HTML and CSS into PDF over a REST API and an MCP server. WeasyPrint 70 lays out the pages, with paper size, margins, headers, footers and page numbers set in CSS. It runs no JavaScript and fetches no URLs, so images and fonts go in as data: URIs. Limits are 2 MB of HTML and 50 pages per render. The servers are in Germany. The free plan has 100 credits a month and needs no card.

## Connect

- MCP endpoint (streamable HTTP): https://api.pdfrender.dev/mcp/ — the anonymous tier works without a key.
- An API key raises the limits: send it in the `X-API-Key` header. The Claude Code plugin reads it from `PDFRENDER_API_KEY`.
- API reference: https://api.pdfrender.dev/docs

Maintained by the pdfrender team.
