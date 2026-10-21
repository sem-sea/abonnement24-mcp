# Abonnement24 deals: MCP server and skill

Live Dutch deals for **smartphones with a subscription**, **sim only** and **internet and tv at home**, compared on the
average monthly price over the whole contract. Data from [Abonnement24](https://abonnement24.nl), prices checked several times a day.

Providers: KPN, Odido, Vodafone, Youfone, Ben, hollandsnieuwe, Simpel, Lebara, Lycamobile and 50+ Mobiel.

## Connect the MCP server

Remote server (streamable HTTP, no key, read only):

```
https://abonnement24.nl/api/mcp
```

Claude Desktop or any MCP client:

```json
{
  "mcpServers": {
    "abonnement24": { "type": "http", "url": "https://abonnement24.nl/api/mcp" }
  }
}
```

Claude Code: `claude mcp add --transport http abonnement24 https://abonnement24.nl/api/mcp`

## Tools

| Tool | What it does |
|---|---|
| `search_phone_deals` | Smartphone with a subscription for a device, brand or budget, for example iPhone 17 or Galaxy S26 |
| `search_sim_only` | Sim only by data, provider, contract length, eSIM or 5G |
| `search_internet` | Internet and tv at home by connection type, speed and tv |
| `list_devices` | Devices with current deals |

## Skill for Claude and OpenClaw

The [`abonnement24` skill](skills/abonnement24/SKILL.md) teaches an agent when and how to use these deals.
Download: https://abonnement24.nl/skills/abonnement24.zip

## Public JSON API

`GET https://abonnement24.nl/api/deals?type=phone&device=iPhone%2017` (also `type=sim`, `internet`, `devices`).
OpenAPI: https://abonnement24.nl/api/deals/openapi.json

## Example questions

- What is the cheapest iPhone 17 with a subscription in the Netherlands without an upfront payment?
- Welke sim only met 20 GB is nu het voordeligst?
- Glasvezel met tv, minimaal 500 Mbit/s: wat zijn de opties?

## Disclosure

Abonnement24 may receive a fee when someone signs up through its links. The order is always by price, not by fee.
More: https://abonnement24.nl/disclaimer
