# Forever In Our Hearts MCP Server

A public, read-only [MCP](https://modelcontextprotocol.io) server for online memorials and funeral notices from
[Forever In Our Hearts](https://foreverinourhearts.co). AI assistants can look up a memorial, the time and place of a
funeral, or a partner funeral home, and link to the page.

- Page: https://foreverinourhearts.co/mcp
- Server: `https://mcp.foreverinourhearts.co/mcp` (Streamable HTTP)
- Free, no account or API key, read-only. 60 requests a minute per IP address

## Tools

| Tool | What it does |
|---|---|
| `search_notices` | Death and funeral notices by name, service location or funeral home, newest first |
| `get_notice` | One notice by id or link: every service with place, local time, livestream link and notes |
| `search_memorials` | Online memorials for people and pets by name |
| `get_memorial` | One memorial by id or link: dates, life story, service details, tribute count and link |
| `search_funeral_directors` | Partner funeral homes by name, town, postcode or country, with address and contact details |

Every tool takes an optional `region`: `global` (foreverinourhearts.co: US, UK, Canada, Ireland, New Zealand and
elsewhere), `au` (foreverinourhearts.com.au, Australia), or leave it out for both. Search tools take `limit` (up to 25)
and `page`.

Only pages that are already public and allowed in search engines are returned. Details a family shows only to QR code
visitors, email addresses and private messages are never returned.

## Connect

Claude (web and desktop): Settings, Connectors, Add custom connector, then paste the server address.

Claude Code:

```
claude mcp add --transport http forever-in-our-hearts https://mcp.foreverinourhearts.co/mcp
```

Other clients (VS Code, Cursor and similar):

```json
{
  "mcpServers": {
    "forever-in-our-hearts": { "type": "http", "url": "https://mcp.foreverinourhearts.co/mcp" }
  }
}
```

Test it with the MCP Inspector: `npx @modelcontextprotocol/inspector`, transport Streamable HTTP, the URL above.

## About

Forever In Our Hearts makes online memorial websites families pay for once, and branded notice and memorial pages for
funeral homes. See [foreverinourhearts.co](https://foreverinourhearts.co) and the
[Funeral Director Network](https://foreverinourhearts.co/funeral-director-network).
