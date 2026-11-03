# Price sources for slab valuation

**Date:** 2026-11-02. **Question from grill session 1:** which ~4 price sources can the prototype use legally to produce an Estimated value for a slab? This extends §5 of `2026-11-02-card-shield-market-research.md`.

Confidence tags: **[P]** primary source, **[S]** secondary, **[U]** unverified.

## Status of sources already covered

- **eBay Marketplace Insights:** still "Limited Release," and approval is needed [P, [eBay](https://developer.ebay.com/api-docs/buy/marketplace-insights/overview.html)].
- **TCGplayer:** "We are no longer granting new API access at this time" [P, [TCGplayer docs](https://docs.tcgplayer.com/docs/getting-started)].
- **PSA Public API, Card Ladder, 130point, Beckett:** unchanged from the earlier research.

## New candidates

| Source | Data | Access today | Cost | Key terms | Conf. |
|---|---|---|---|---|---|
| **PriceCharting / SportsCardsPro** (same operator) | Current price by grader and grade (PSA 1–10, BGS 10, CGC, SGC, TAG, ACE). No historic sales through the API. Unclear whether prices are sold-based or estimated | Self-serve token API plus a daily CSV | Legendary tier, $49/month | **Internal use only.** Showing values to Users needs a commercial license and written permission. Cache must be purged when the subscription ends. 1 call/sec | [P, [API docs](https://www.pricecharting.com/api-documentation), [Pro](https://www.pricecharting.com/pricecharting-pro)]. SportsCardsPro terms are assumed to match [S] |
| **CardHedger** | Sports and Pokémon. Graded prices for PSA, BGS, SGC, CGC and HGA. Price lookup by cert number, comps with anomaly filtering, and an FMV estimate for each grade | Self-serve API, MCP server, enterprise tier | From $49/month | Terms couldn't be read (bot-check page) | [S, [docs](https://api.cardhedger.com/docs), [business](https://www.cardhedger.com/price_api_business)] |
| **CardSight AI** | Card ID and slab ID (PSA, BGS, SGC, CGC, TAG) plus market pricing, which was in beta in April 2026. Per-grade pricing not confirmed | Self-serve REST, SDKs | Free (750 calls/month), then $14.95, $74.95, $199.95, or Enterprise | Allows use inside your own end-user app. Bans resale, competing products and building a database. Short-term cache only | [P, [pricing](https://cardsight.ai/pricing), [terms](https://cardsight.ai/terms)] |
| **Scrydex** | TCG only. Raw and graded prices (PSA, BGS, CGC, TAG, ACE) | Self-serve | $29, $99 or $399 per month, or custom | Terms not published | [P] pricing; terms [U] |
| **PokemonPriceTracker** | Pokémon only. PSA graded sales from eBay and Fanatics Collect | Self-serve | Free, $9.99, $99 or $300 per month | Commercial license only on $99+ plans. Upstream eBay rights unclear | [P, [pricing](https://www.pokemonpricetracker.com/pricing)] |
| **Alt (Alt Value)** | Model estimate from auction comps. None for SGC/CGC cards under $500 | No API found | — | — | [P] method; API [U] |
| **Market Movers** | Sold comps from eBay, Goldin, Heritage and Fanatics Collect | Consumer app only | $9.99–49.99/month | Non-commercial use only | [S] |
| **Goldin, Fanatics Collect, Heritage, PSA APR** | Auction results | No official API. Heritage has sued over scraping | — | Avoid scraping | [S]/[U] |
| **Collectr, CollX, Ludex** | Consumer estimates | No public API found | — | — | [U] |

## Recommended prototype set

1. **PriceCharting / SportsCardsPro:** terms verified, widest grader and grade coverage, $49/month. Use it internally first, and negotiate the commercial license before Users see any values.
2. **CardSight AI:** free tier, and its terms explicitly allow use inside your own app. Pricing is in beta, so check per-grade depth.
3. **CardHedger:** closest to graded sold comps, with lookup by cert number, and independent of Collectors and eBay. Read its terms before building.
4. **Scrydex** for TCG slabs, **plus an eBay Marketplace Insights application filed now**. eBay is the only first-party source of sold data.

## Caveats

- The self-serve aggregators most likely get their data from eBay, Goldin or Fanatics Collect. Get written confirmation from each vendor that it has the upstream rights.
- No source examined mentions **insurance or valuation use**. Ask every vendor explicitly before using its data in an Agreed value proposal.
