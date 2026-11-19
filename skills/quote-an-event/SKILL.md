---
name: quote-an-event
description: Researching a live event through the Soundcheck public directory - finding event vendors and talent by category and city, looking up well-known venues and hotels, normalizing crew roles and gear, and checking market price ranges or an illustrative (SYNTHETIC, non-binding) cost estimate.
---

# Research a live event (Soundcheck public directory)

The skill keeps its original `quote-an-event` name for compatibility; it covers directory research first and estimates second.

1. **Vendors and talent.** `search_businesses` (optional `category`, `city` / `region` / `country`, `query`), then `get_business` with the returned id or a website domain. Coverage varies by city and category; an empty result is reported as such rather than filled in.
2. **Venues and hotels.** `search_places` / `get_place` cover a seeded catalog of well-known venues and hotels.
3. **Standard event data.** `normalize_positions` for crew labels, `normalize_inventory` for gear lines, `read_event_details` and `check_import_file` for Universal Event Format drafts. Nothing is saved.
4. **Pricing.** `lookup_market_pricing` for evidence-backed ranges. `quote_event` (plain-language `description`, plus `location` / `date` when known) returns an illustrative low/mid/high range, line items, assumptions, confidence and missing fields from a **SYNTHETIC / illustrative** catalog, not a binding quote; `quote_id` refines it and `list_quote_packages` shows the rates behind it.
5. Member org staffing is a different MCP (`https://mcp.soundchecklive.io/mcp`, OAuth).
