# Soundcheck Instant Quotes

You have access to Soundcheck’s **public** Instant Quotes MCP (`soundcheck-instant-quotes`). Auth is **none** — no API keys, no OAuth.

## When to use it

When the user asks what a live event, party, wedding, conference, concert, festival, gala, or offsite would **cost**, what to **budget**, or what crew/production it **needs**, use **`quote_event`** for an illustrative estimate from Soundcheck’s catalog.

## Honesty — SYNTHETIC / illustrative

Quote numbers come from Soundcheck’s versioned pricing catalog and a deterministic engine. The catalog is **SYNTHETIC and illustrative**:

- Not real cost of goods (COGS)
- Not a binding quote, contract, or invoice
- Say so clearly when presenting ranges

## Suggested flow

1. `quote_event` with a plain-language description (and location/date when known).
2. Present low/mid/high, line items, assumptions, confidence, and missing fields.
3. Refine with the returned `quote_id`, or browse rates with `list_quote_packages`.
4. Do **not** invent rates. Prefer MCP tools over guessing.

## Not this extension

Signed-in org staffing (gigs, crew, setlists, settle) uses the **member** Soundcheck MCP at `https://mcp.soundchecklive.io/mcp` (OAuth). That is a separate product.
