# Soundcheck public MCP: live event directory

This extension connects Soundcheck's **public** MCP (`soundcheck-instant-quotes`). Auth is **none**: no API keys, no OAuth. Soundcheck is live event digital infrastructure: the primitives agents need to manage any type of event.

## What it covers

- **Directory.** `search_businesses` finds event businesses (AV and production, sound, lighting, staging, backline, video, DJs, live bands, entertainment agencies, planners, caterers, photographers, videographers, rentals, decor, staffing, security, transportation) by `category`, `city` / `region` / `country` and free-text `query`. `get_business` returns one listing by id or website domain, with website, services, published contact details and source URLs. Listings are researched from public websites and cached, so coverage varies by city and category; an empty result means no listings yet for that search.
- **Venues and hotels.** `search_places` / `get_place` cover a seeded catalog of well-known venues and hotels. Unknown names return empty results; addresses are never invented.
- **Organizations on Soundcheck.** `get_public_org` returns a public profile by slug or id.
- **Standard event data.** `list_positions` / `normalize_positions` (crew roles such as FOH, A2, LD), `search_inventory` / `normalize_inventory` (gear), and `read_event_details` / `get_import_format` / `check_import_file` (Universal Event Format drafts and checks; nothing is saved).
- **Pricing.** `lookup_market_pricing` returns evidence-backed ranges with citations, or no number when evidence is missing. `quote_event` / `list_quote_packages` return illustrative estimates.

## Estimates are SYNTHETIC / illustrative

`quote_event` numbers come from Soundcheck's versioned pricing catalog and a deterministic engine. The catalog is **SYNTHETIC and illustrative**: not real cost of goods (COGS), and not a binding quote, contract, or invoice. Estimates are presented with that label.

## Requests

`request_booking` and `request_sponsorship` reach an organization only after the requester confirms by email, and apply only when the person asks to contact an organization.

## Not this extension

Signed-in org staffing (gigs, crew, setlists, settle) uses the **member** Soundcheck MCP at `https://mcp.soundchecklive.io/mcp` (OAuth). That is a separate product.
