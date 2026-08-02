# Botrista

Botrista, Inc. is a San Francisco based beverage-automation company founded in 2017. It builds the
DrinkBot robotic beverage dispenser — which mixes infused teas, flavored lemonades, iced coffees and
mocktails in roughly twenty seconds from a touchscreen order — and the CloudBar cloud platform that
operators use to manage recipes, inventory and sales analytics across a fleet of connected machines.

Botrista sells beverage automation as a service, not as a developer platform. As of the 2026-08-02
enrichment pass it publishes **no developer portal, no API reference and no machine-readable API
contract**. POS integrations are handled case-by-case by its commercial team.

## What contract discovery found

| Surface | Result |
|---|---|
| OpenAPI / Swagger | none — every candidate path 404s on both live application backends |
| GraphQL | none |
| AsyncAPI / webhooks | none |
| A2A agent card | none on any host |
| `/.well-known/*` | nothing served anywhere (see `well-known/`) |
| MCP | **found** — the Wix platform site MCP at `https://www.botrista.info/_api/mcp` (9 tools, anonymous) |
| `llms.txt` | **found** — Wix-generated, at `https://www.botrista.info/llms.txt` |

The two live backends discovered (`us-orderbws.botrista.io` for CloudBar and
`portal-api.botrista.com` for the Botrista Data Portal) are private first-party backends for
Botrista's own single-page applications. They are recorded in `security/` and `well-known/` as
observed infrastructure; they are **not** listed as public APIs.

- https://botrista.com/
- https://www.botrista.info/
- https://forgeglobal.com/botrista_stock/
