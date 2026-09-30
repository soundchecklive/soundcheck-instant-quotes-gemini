# Soundcheck Instant Quotes (Gemini CLI Extension)

Gemini CLI **Extensions Gallery** package that wires [Google Gemini CLI](https://github.com/google-gemini/gemini-cli) to Soundcheck’s **public** [Instant Quotes](https://soundchecklive.io) MCP. No login, no API keys: anonymous illustrative cost estimates for live events (parties, weddings, conferences, concerts, festivals, galas, offsites).

## Honesty

Estimates come from Soundcheck’s **versioned pricing catalog** and a deterministic engine. Numbers are **SYNTHETIC and illustrative**:

- Not real cost of goods (COGS)
- Not a binding quote, contract, or invoice

Always say so when you share ranges with users.

## Install

```bash
gemini extensions install https://github.com/soundchecklive/soundcheck-instant-quotes-gemini
```

### Local development

From a clone of this repo:

```bash
gemini extensions link .
```

## Verify

In Gemini CLI:

- `/extensions list` — extension appears as `soundcheck-instant-quotes`
- `/mcp` — MCP server `soundcheck-instant-quotes` is connected

## MCP server

| Field | Value |
| --- | --- |
| Name | `soundcheck-instant-quotes` |
| Transport | Streamable HTTP |
| URL | `https://mcp.soundchecklive.io/public/mcp` |
| Auth | **none** (no OAuth, no API key) |

### Manual `settings.json` snippet

If you configure MCP by hand instead of installing the extension:

```json
{
  "mcpServers": {
    "soundcheck-instant-quotes": {
      "httpUrl": "https://mcp.soundchecklive.io/public/mcp"
    }
  }
}
```

## Gallery listing (maintainers)

For this repo to appear in the Gemini CLI Extensions Gallery crawl, a maintainer must add the GitHub repository topic **`gemini-cli-extension`** on the repository settings page. That step is human-only; this README does not imply the topic is already set.

## Repository layout

```
.
├── gemini-extension.json   # Extension manifest (MCP httpUrl + GEMINI.md)
├── GEMINI.md               # Default context for Gemini when extension is active
├── README.md
├── LICENSE
└── skills/
    └── quote-an-event/
        └── SKILL.md        # Skill: quote_event flow + SYNTHETIC disclaimer
```

## Not this extension

**Member** Soundcheck (signed-in org staffing: gigs, crew, setlists, settle, ledger) uses a **different** MCP:

- URL: `https://mcp.soundchecklive.io/mcp`
- Auth: OAuth

Instant Quotes here is public, anonymous, and estimate-only.

## Links

- Product: [soundchecklive.io](https://soundchecklive.io)
- This repo: [github.com/soundchecklive/soundcheck-instant-quotes-gemini](https://github.com/soundchecklive/soundcheck-instant-quotes-gemini)
- Public Instant Quotes MCP base: `https://mcp.soundchecklive.io/public/mcp`

## License

MIT © [Soundcheck Live, Inc.](https://soundchecklive.io) — see [LICENSE](./LICENSE).
