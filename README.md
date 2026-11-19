# Soundcheck Event Directory (Gemini CLI extension)

Gemini CLI **Extensions Gallery** package that wires [Google Gemini CLI](https://github.com/google-gemini/gemini-cli) to Soundcheck’s **public** MCP: a live event directory and the data standards behind it. Soundcheck is live event digital infrastructure: the primitives agents need to manage any type of event. No login, no API keys.

## What it covers

- **Directory:** event businesses (AV and production, sound, lighting, staging, backline, video, DJs, live bands, agencies, planners, caterers, photographers, rentals, decor, staffing, security, transportation) by category and city via `search_businesses` / `get_business`; a seeded catalog of well-known venues and hotels via `search_places` / `get_place`; public organization profiles via `get_public_org`. Listings are researched from public websites and cached, so coverage varies by city and category.
- **Standard event data:** crew roles (`list_positions`, `normalize_positions`), gear (`search_inventory`, `normalize_inventory`), and Universal Event Format files (`read_event_details`, `get_import_format`, `check_import_file`).
- **Pricing:** evidence-backed market ranges (`lookup_market_pricing`) and illustrative cost estimates (`quote_event`, `list_quote_packages`).

The extension keeps its original `soundcheck-instant-quotes` name so existing installs keep working.

## Honesty: estimates

`quote_event` estimates come from Soundcheck’s **versioned pricing catalog** and a deterministic engine. Numbers are **SYNTHETIC and illustrative**:

- Not real cost of goods (COGS)
- Not a binding quote, contract, or invoice

Ranges are shared with that label.

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

Auto-listing on [geminicli.com/extensions](https://geminicli.com/extensions/) requires:

1. Public GitHub repo with `gemini-extension.json` at the **absolute root** (this package)
2. GitHub topic **`gemini-cli-extension`** on the repo About section

Adding the topic (and owning the gallery crawl) is a **humans-only** maintainer step — typically Steven. This README does **not** claim the topic is already set. Official release docs: [Releasing extensions](https://geminicli.com/docs/extensions/releasing/).

## Repository layout

```
.
├── gemini-extension.json   # Extension manifest (MCP httpUrl + GEMINI.md)
├── GEMINI.md               # Default context for Gemini when extension is active
├── README.md
├── LICENSE
└── skills/
    └── quote-an-event/
        └── SKILL.md        # Skill: directory research, then estimates (SYNTHETIC disclaimer)
```

## Not this extension

**Member** Soundcheck (signed-in org staffing: gigs, crew, setlists, settle, ledger) uses a **different** MCP:

- URL: `https://mcp.soundchecklive.io/mcp`
- Auth: OAuth

This extension is public, anonymous and read-focused: directory, standard event data and pricing.

## Links

- Product: [soundchecklive.io](https://soundchecklive.io)
- MCP docs: [docs.soundchecklive.io/integrations/mcp-server](https://docs.soundchecklive.io/integrations/mcp-server)
- MCP discovery: [docs.soundchecklive.io/integrations/mcp-discovery](https://docs.soundchecklive.io/integrations/mcp-discovery)
- Privacy: [soundchecklive.io/privacy](https://soundchecklive.io/privacy)
- Sibling Claude plugin (public directory): [soundcheck-plugin/instant-quotes](https://github.com/soundchecklive/soundcheck-plugin/tree/main/instant-quotes)
- Writing Gemini extensions: [geminicli.com/docs/extensions](https://geminicli.com/docs/extensions/writing-extensions/)

## License

MIT © Soundcheck Live, Inc. — see [LICENSE](./LICENSE).
