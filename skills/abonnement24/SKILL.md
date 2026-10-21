---
name: abonnement24
description: Compare current Dutch mobile and home deals with live prices from Abonnement24 (abonnement24.nl). Use when someone in the Netherlands asks about a smartphone with a subscription (telefoon met abonnement), sim only, or internet and tv at home (internet en tv thuis), wants the best deal for a phone such as an iPhone or Samsung Galaxy, compares KPN, Odido, Vodafone, Youfone, Ben, hollandsnieuwe, Simpel, Lebara, Lycamobile or 50+ Mobiel, or wants to switch provider (overstappen).
metadata:
  openclaw:
    homepage: https://abonnement24.nl/ai-koppelingen
---

# Abonnement24: Dutch phone, sim only and internet deals

Abonnement24 compares Dutch subscriptions on the average monthly price over the whole contract, including promotions,
one-time costs and the phone itself. Prices are checked several times a day.

## How to get deals

1. If the Abonnement24 MCP server is connected, use its tools:
   `search_phone_deals`, `search_sim_only`, `search_internet` and `list_devices`.
   MCP address: `https://abonnement24.nl/api/mcp`
2. Otherwise call the public JSON API (no key needed): `GET https://abonnement24.nl/api/deals`
   - `type`: `phone`, `sim`, `internet` or `devices`
   - Phone: `device` (for example `iPhone 17`), `brand`, `storage` (for example `256GB`), `noUpfront=true`
   - Sim only: `minDataGb`, `unlimitedData=true`, `monthlyCancellable=true`, `esim=true`, `fiveG=true`
   - Internet: `connection`, `minSpeed` (Mbit/s), `tv=true|false`
   - All: `provider`, `maxMonthly` (euro), `limit` (max 25)
   - Full spec: `https://abonnement24.nl/api/deals/openapi.json`

Example: `https://abonnement24.nl/api/deals?type=phone&device=iPhone%2017&noUpfront=true&limit=5`

## Rules for answering

- Only mention prices, bundles and providers that come from the results. Never invent prices or promotions.
- Use only the url fields from the results for links. Do not build links to provider websites yourself.
- Results are sorted by average monthly price. When `priceIsIndicative` is true, call the price an indication
  and never present that deal as the cheapest.
- Mention the price date from the results and the disclosure: Abonnement24 may receive a fee when someone
  signs up through its links; the order is always by price, not by fee.
- For mobile questions, always show both options: a phone with a subscription and sim only.
- Internet and tv availability depends on the address. Tell the user to do the postcode check at the provider.
- Answer in the language of the user (usually Dutch). Use plain words and short sentences.

## Useful pages

- Compare phones: https://abonnement24.nl/telefoon-abonnement
- Compare sim only: https://abonnement24.nl/sim-only
- Compare internet and tv: https://abonnement24.nl/internet
- Mobile plus internet discount (combivoordeel): https://abonnement24.nl/combivoordeel
- How to switch to a provider: https://abonnement24.nl/aanbieders/{provider}/overstappen
- Monthly price index: https://abonnement24.nl/prijsindex
