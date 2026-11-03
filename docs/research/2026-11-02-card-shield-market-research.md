# Card Shield: market and business research

**Date:** 2026-11-02. **Purpose:** raw research to feed later "grill" sessions that stress-test the Card Shield idea. It is meant to be evidence, not a plan.

**Confidence tags** (used on every claim):
- **[P]** verified against a primary source: company page, official release, regulator, statute or app-store listing.
- **[S]** secondary source only, such as trade press, blogs, aggregators or forum posts. Multiple agreeing secondaries are noted.
- **[U]** unverified, or my own assumption or estimate.

**Access caveat:** psacard.com, gosgc.com, beckett.com and cardladder.com returned HTTP 403 to automated fetches. PSA, SGC and BGS prices therefore come from trade press that cites those companies' announcements. Founders should screenshot the live pricing pages before using any number in a pitch.

---

## Executive summary

1. **The premise partly holds.** Graded-card volume is real and growing fast. GemRate counted about 26.8M cards graded in 2025, up 32% YoY, with PSA at about 19.26M [S, [cllct/GemRate](https://www.cllct.com/sports-collectibles/sports-cards/major-authenticators-graded-more-than-26-million-cards-in-2025)]. Theft against card shops is rising, and shops report trouble getting coverage [S, [CP24/CNN, 2026-04-04](https://www.cp24.com/news/world/2026/04/04/pokemon-cards-are-igniting-an-international-crime-spree/)].
2. **"Only WAX works with an insurer" is wrong.** WAX is a real collectibles-insurance MGA underwritten by Chubb that covers trading cards. However, at least eight other players already pair cards with insurance: Collectibles Insurance Services, American Collectors (also sold through USAA), the PSA + Cabrella partnership, insured vaults at eBay, Alt and Fanatics, CardCastle + Sure, and others. See §2.
3. **The biggest risk is that Collectors (PSA's parent) already owns the on-ramp.** In April 2026 PSA named Cabrella its *exclusive* insurance partner for inbound grading shipments and called it a "first step toward a wider range of collectibles services" [P, [PR Newswire via AAP, 2026-04-27](https://www.aap.com.au/aapreleases/cision20260427ae43393/)]. PSA's free app added portfolio-value tracking for PSA, SGC, BGS, CGC and raw cards in September 2026 [S, [Heavy](https://heavy.com/sports/cards/psa-app-update-raw-collection/)]. Collectors also owns SGC and Card Ladder, and agreed to buy Beckett [P, [Collectors, 2025-12-15](https://collectors.com/company-announcement)]. The "insure at the grading checkout" idea depends on a checkout that PSA controls and has already given to a partner.
4. **Second risk: most collections are small.** Collectr reports more than 4M users tracking about $1.5B in total, roughly $375 per user on average [S, [BetaKit, 2025-08-13](https://betakit.com/how-collectr-bootstrapped-a-trading-card-hobby-into-an-eight-figure-business/)]. A standalone policy at the reported $0.50–$1.00 per $100 of value [S] only gets meaningful premium above roughly $10–25k of value. Willingness to pay for insurance is likely concentrated in a small high-value segment.
5. **PSA pricing is rising, but the story is messier than "sharp increases."** The cheapest tier went from $19.99 (Value Bulk, before September 2025) to $21.99 (September 2025) to $24.99 (February 2026). All Value tiers were then paused on 2026-06-02 because of a backlog of about 10M cards. A new Standard tier opened at $59.99 on 2026-09-14, and Value reopened 2026-10-29 at $39.99 with a $500 maximum insured value [S, several outlets]. The entry price roughly doubled in about 13 months.
6. **The underwriting thesis is half right.** Slabs carry a cert number that can be checked against PSA's public API [P, [PSA Public API](https://www.psacard.com/publicapi)], plus tamper-evident cases and grade-specific comparable sales. That makes proof of existence, identity and condition easier than for most collectibles. But prices are volatile (Card Ladder reported values up more than 145% YoY [S, CP24]), theft is concentrated, and fake or swapped slabs are a fraud vector. Agreed value has to be re-marked often. WAX already sells "real-time premium updates" (WAX Flex) [P, [App Store](https://apps.apple.com/us/app/id1511201226)].
7. **Valuation data is a moat for incumbents and a cost for Card Shield.** Card Ladder (owned by Collectors) and eBay sold-price data (the Marketplace Insights API is "Limited Release") are gated [P, [eBay Buy APIs](https://developer.ebay.com/api-docs/buy/static/buy-overview.html)]. Beckett has sued scrapers [S, [Cardboard Connection](https://www.cardboardconnection.com/law-of-cards-beckett-sues-two-more-for-scraping-data/amp)]. "Real-time verifiable value" needs a licensed data source.
8. **Candidate wedges that the evidence supports (not recommendations):**
   - (a) Dealers and card shops at shows, who report they can't get coverage [S].
   - (b) A B2B2C "schedule and valuation feed" for existing valuable-articles policies sold by independent agents. The precedents are Appraisal Bureau → Addepar for art [P, [Addepar integrations](https://integrations.addepar.com/product/appraisal-bureau)] and Hodinkee Insurance (an in-house agency with Chubb) for watches [S, [Coverager](https://coverager.com/introducing-hodinkee-insurance/)].
   - (c) Estate and beneficiary records for high-value collections, a gap no card app addresses (§6).
9. **Insurance distribution fits the founder's background.** A licensed agency that appoints with a carrier or an existing MGA (WAX pays agents 8% [P, [First Connect, 2026-04](https://info.firstconnectinsurance.com/help/wax-launch-session)]) is a fast, low-capital first step. Becoming an MGA takes a carrier willing to delegate authority, and that needs loss data the company doesn't yet have. Broker-backed accelerators exist, for example BrokerTech Ventures, which gives $50k per company [S, [Holmes Murphy](https://www.holmesmurphy.com/news/brokertech-ventures-announces-2026-accelerator-cohort-sponsors-gis-and-more/)].
10. **Insurance commission alone probably can't fund a venture-scale business** (rough numbers in §4). A business case likely needs several revenue streams (§8), or a narrow, high-value focus that fits a lifestyle or angel-funded business rather than VC.

---

## 1. Grading companies: prices, coverage, volume

### PSA price history (cheapest tier and main tiers)

| Date | Change | Source |
|---|---|---|
| ~2020–21 boom | Economy was $50/card and lottery-gated, then discontinued. A March 2021 list showed Value $20, Regular $100, Express $150, Super Express $300 | [S, [Cardlines](https://cardlines.com/psa-grading-price-increases)] |
| 2025-09-25 | Value Bulk $19.99 → $21.99, with turnaround extended | [S, [cardgrade.io](https://cardgrade.io/blog/psa-grading-price-increase-2025), [Cardlines](https://cardlines.com/as-psa-raises-prices-again-when-should-you-grade-your-cards/)] |
| 2026-02-10 | Value Bulk $21.99 → $24.99 (TCG Bulk folded in), Value $27.99 → $32.99, Value Plus $44.99 → $49.99, Value Max $59.99 → $64.99, Regular $74.99 → $79.99. PSA cited labor costs, AI, and a $200M capacity investment | [S, [SI](https://www.si.com/collectibles/psa-increasing-card-grading-prices-and-turnaround-times), [cllct](https://www.cllct.com/sports-collectibles/sports-cards/psa-to-increase-grading-prices-turnaround-times)]. The prior Value Bulk price conflicts across sources ($19.99 vs $21.99) |
| 2026-06-02 | All four Value tiers paused because the backlog was near 10M (announced 2026-05-28). Regular at $79.99 became the floor | [S, [Sports Collectors Digest](https://sportscollectorsdigest.com/psa-halts-value-grading-services-amid-10-million-card-backlog)]; PSA has a [backlog tracker page](https://www.psacard.com/info/backlog-tracker) (403 to fetch) |
| 2026-09-14 | New Standard tier $59.99 (max insured value $1,000). Regular renamed Priority ($79–79.99, max $1,500). Express $149 → $199 (max $2,500). Super Express $349 (max $5,000). Walk-Through renamed Premier at $599 (max $10,000). Premium $999+ (max $25,000+). PSA Europe (Frankfurt) opened 2026-09-15 | [S, [Pregrade](https://pregradecards.com/blog/psa-lowers-grading-prices-new-standard-tier-september-2026)] |
| 2026-10-29 | Value reopened at $39.99 (90–100 business days, $500 max insured). Standard at 70–80 days, Priority at 50–60 days. The backlog peaked at about 14M in June | [S, [ICv2, 2026-10-29](https://icv2.com/articles/news/view/63751/)] |

**Takeaway [U]:** the founders' "rising sharply" claim is directionally right. The cheapest available PSA tier went from $19.99 to $39.99 between September 2025 and October 2026. But PSA has also added cheaper tiers at times, so this is repricing plus rationing, not a straight line up.

### Peer graders (all [S]; verify on each company's order form)

| Grader | Latest reported entry price | Notes |
|---|---|---|
| CGC | Bulk $15 → $17, Economy $18 → $20 (2026-03-24); Standard $55, Express $100, WalkThrough $300 | Jan 2026 schedule [P, [CGC news](https://cgccards.com/news/article/14659/cgc-price-updates-2026)]; March change [S, cardgrade.io](https://cardgrade.io/blog/card-grading-industry-2026) |
| SGC | Lowest tier raised to $50 on 2026-09-02, from $15 or $18 (sources disagree). SGC warned of more changes in "late 2026–early 2027" | [S, [SI](https://www.si.com/collectibles/sgc-latest-company-raise-grading-prices), [cardgrade.io](https://cardgrade.io/blog/sgc-standard-price-increase-50-september-2026)] |
| BGS (Beckett) | June 2026 snapshot: Base $14.95/$17.95 (with subgrades), Standard $34.95, Express $79.95, with Base/Standard paused at times | [S, [cardgrade.io](https://cardgrade.io/blog/card-grading-industry-2026)] |
| TAG | Basic $22 to Walkthrough $299, several tiers sold out (June 2026) | [S, same] |

### PSA's existing coverage, vault and insurance

- **Declared value and maximum insured value per tier:** while PSA holds a card, coverage is capped by tier, for example $500 for Value and $1,000 for Standard [S, above]. Users report PSA reimburses fair market value capped at declared value [S, forum, [Elite Fourum](https://www.elitefourum.com/t/what-does-psa-insurance-cover/22381)]. PSA's own coverage pages are at [psacard.com/info/coverage](https://www.psacard.com/info/coverage) (403 to fetch).
- **PSA + Cabrella (2026-04-27):** an exclusive, opt-in, paid add-on that covers inbound shipments to PSA, up to $150k per shipment. Ungraded cards are valued using Beckett, Card Ladder and similar sources. PSA calls it "a first step toward a wider range of collectibles services" [P, [PR Newswire/AAP](https://www.aap.com.au/aapreleases/cision20260427ae43393/)]. **This directly occupies the "insurance at grading checkout" slot.**
- **PSA Vault / eBay vault:** eligible cards are graded singles worth $250 or more, held by a US user. eBay "maintains insurance at its own expense" for stored items. Value is the purchase price, or the lesser of stated value and the insurer's market value [P, [eBay vault terms](https://www.ebay.com/vault/terms)]. Vault services bought on eBay are subject to PSA's terms [P, same]. Coverage stops when a card leaves the vault, which means it doesn't protect cards at home.
- **PSA app:** free. In September 2026 it added "Collection" with estimated portfolio value, history, folders and public collections, covering PSA, SGC, BGS, BVC, CSG, CGC and raw cards [S, [Heavy](https://heavy.com/sports/cards/psa-app-update-raw-collection/); [App Store](https://apps.apple.com/app/id996239729)]. It has no insurance or estate features [S].

### Collectors (PSA parent): structure and deals

- Brands include PSA, PSA Vault, PCGS, SGC and Card Ladder. Collectors agreed on 2025-12-15 to acquire Beckett, which will remain a separate brand with no pricing change [P, [Collectors](https://collectors.com/company-announcement)]. Closing status is unclear: one aggregator says it closed [S, [PrivSource](https://www.privsource.com/acquisitions/deal/deSq6n)].
- Collectors acquired Card Ladder in December 2021 [S, [SCD](https://sportscollectorsdigest.com/news/collectors-universe-acquires-card-ladder-card-grading-values)], and SGC in 2024 [S, [cllct](https://www.cllct.com/sports-collectibles/memorabilia/psa-parent-company-collectors-acquires-beckett)].
- It raised $100M at a $4.3B valuation in March 2022 [P, [BusinessWire](https://www.businesswire.com/news/home/20220329006052/en/Collectors-Announces-New-100-Million-Financing-Round); valuation S, [FOS](https://frontofficesports.com/collectors-raises-100m-valued-at-4-3b/)].
- PSA, SGC and Beckett together hold about 79% of grading [S, cllct]. A congressman asked the FTC to investigate [S, [Antiques & Auction News](https://antiquesandauctionnews.net/when-is-a-monopoly-not-a-monopoly)].

### Volume

- 2025: about 26.8M cards graded industry-wide (+32% YoY). PSA graded about 19.26M (+26%), CGC about 4.92M. Pokémon alone was about 16.1M, and TCG/non-sports cards outnumbered sports cards (16.8M vs 10M) for the first time [S, GemRate via [cllct](https://www.cllct.com/sports-collectibles/sports-cards/major-authenticators-graded-more-than-26-million-cards-in-2025) / [SI](https://www.si.com/collectibles/over-26-million-cards-graded-in-2025-how-the-market-exploded)].
- 2026: PSA passed 2M per month (March) and about 2.5M in June. The industry hit about 2.97M in March [S, [thecardshopfinder](https://thecardshopfinder.com/blog/gemrate-march-2026-record-2-97-million-cards-graded-20260501/)].
- **Cumulative PSA population [U]:** no primary figure found. GemRate or PSA's population report would be the source.

---

## 2. Competitors and adjacent players

### WAX (the "Wax collectibles app"): identified

- **What it is:** the iOS app is now named **"WAX Collectibles"** (formerly "WAX Insurance"). The developer is WAX Insurance and the seller is **Osiris Exchange Inc.** [P, [App Store id1511201226](https://apps.apple.com/us/app/id1511201226)]. The domain is wax.insure [S]. It was founded in 2018 and launched in September 2020 by David Nichols (former K-Swiss global president) and CEO Calvin Bradley [P, [PR Newswire 2020-09-09](https://prnewswire.com/news-releases/former-k-swiss-global-president-and-olympic-athlete-team-up-on-insurance-app-for-luxury-watches-and-collectibles-301127005.html)].
- **Category scope:** generalist. It covers 25–30+ categories (watches, jewelry, handbags, cars, sneakers, art, **trading cards**) [P, App Store; PR Newswire]. It is not card-specific.
- **Insurer:** **Chubb** in the US and **Sukoon** in the UAE [P, App Store]. A First Connect carrier-store page says WAX is an **MGA** whose Valuable Articles & Collections product is "underwritten by Chubb," with admitted and E&S options through other insurers. It launched in that agent marketplace on 2026-04-02 and pays **8% agent commission** on new and renewal business [P, [First Connect](https://info.firstconnectinsurance.com/help/wax-launch-session)]. An earlier report says "Markel and/or Chubb" [S, [Coverager](https://coverager.com/introducing-wax-credit/)]. The Sukoon contract is documented [P, [DFM filing 2024-01-17](https://feeds.dfm.ae/documents//2024/Jan/17/96f1ccff-372f-461c-9aff-224ff03fe98f/Press%20Release%20-%20WAX%20Sukoon%20Contract%20EN%202024-01-17.pdf)].
- **Product:** quote and bind in the app (US).
  - **WAX Flex:** "real-time premium updates" and a choice of 100/125/150% claims payout.
  - **WAX Classic:** 150% maximum agreed value and mysterious-disappearance coverage.
  - **WAX Credit:** collectible-backed loans (NY/CA/FL).
  - The app also has claims tracking.
  
  All [P, App Store]. Its 2020 launch had up to $1M limits, a $0 deductible option, and no appraisal at application, in 13 states [S, [Coverager](https://coverager.com/introducing-the-wax-insurance-app/)]. In 2026, agents said appraisals are typically needed within 3 years, and Pokémon eligibility came up as an underwriting question [P, First Connect].
- **Traction:** 62 App Store ratings [P], which suggests a small consumer footprint. Reported seed funding was $10M (Slow Ventures, AV8) [S, [StreetInsider/GlobeNewswire](https://www.streetinsider.com/Globe+Newswire/WAX+Insurance+Services+Launches+Collectibles+Insurance/20135506.html)].
- **Do not confuse with:** the WAX blockchain (Worldwide Asset eXchange), or **Wax Cache**, a card inventory app at $9.99/month with no insurance [S, [Hunted](https://www.hunted.space/product/wax-cache)].

**Founders' assumption check:** "WAX is the only one actively working with an insurance carrier" is **false**. WAX is the closest analog to Card Shield's app-plus-insurance model, but it is generalist and luxury-leaning. Others (all below) already pair cards with insurance.

### Insurance-first players

| Player | What | Price / terms | Carrier | Conf. |
|---|---|---|---|---|
| **Collectibles Insurance Services (CIS)** | Collector and dealer policies, sports-card page | Collector deductible from $0, dealer $500. Market-value basis. Items ≥$25k must be scheduled. Mail and transit covered; mysterious disappearance excluded. Optional 1%/month auto-increase. Online quote | "AM Best A-rated" carrier, not named | [P, [collectinsure.com](https://collectinsure.com/sports-card-insurance/)] |
| **American Collectors Insurance** | Sports cards and memorabilia | Agreed value, mysterious disappearance, shipping. Inflation guard of 2% per quarter. New items auto-covered for 30 days | Not named on page | [P, [americancollectors.com](https://americancollectors.com/insurance/collectibles/sports-cards/)]; sold to USAA members with a 10% discount [P, [USAA](https://usaa.com/insurance/property/collectibles)] |
| **Chubb valuable articles** | HNW rider or standalone | Agreed value. New acquisitions covered 90 days. Often requires a Chubb home policy | Chubb | Features [P, [Chubb](https://www.chubb.com/us-en/individuals-families/clients/valuable-articles-insurance-coverage.html)]; rates anecdotal at $0.33–$3.10 per $100 [S, forums] |
| **Hodinkee Insurance** (watches, analog) | Content and community brand with its own agency | n/a | Chubb | [S, [Coverager](https://coverager.com/introducing-hodinkee-insurance/)]; Watches of Switzerland bought Hodinkee in October 2024 [S] |
| **Cabrella** | Shipping insurance; PSA inbound partner | Up to $150k per shipment, opt-in fee | Not disclosed | [P, PR] |
| **CardCastle + Sure** | MTG tracker with embedded insurance | n/a | Sure (embedded platform) | [S, [CardCastle help](https://support.cardcastle.co/en/articles/3617150-can-use-cardcastle-to-insure-my-collection)] |
| **NFP (Canada)** | Card and memorabilia program | n/a | Berkley Asset Protection | [S, [NFP](https://www.nfp.ca/insights/why-todays-collectors-need-specialized-insurance/)] |

### Software and marketplaces (tracking, pricing, vaults)

| Player | What | Price | Insurance? | Funding | Conf. |
|---|---|---|---|---|---|
| **Collectr** | TCG-first portfolio tracker (raw, graded, sealed). Values come from eBay/TCGplayer affiliate data. Ad network | Pro $7.99/month (also $59.99/year reported) | None found | $500k friends and family, bootstrapped. "Eight-figure ARR," more than 4M users, team of 5 (August 2025) | [S, [BetaKit](https://betakit.com/how-collectr-bootstrapped-a-trading-card-hobby-into-an-eight-figure-business/)]; annual price [S] |
| **Card Ladder** (Collectors) | Sales data and indexes | Pro $20/month or $200/year (from 2025-02-01; previously $15/$150) | No | Acquired by Collectors in 2021 | [S, citing [cardladder.com/pricing](https://www.cardladder.com/pricing)] |
| **CollX** | Scanner and marketplace, sports-first | Pro $10/month or $100/year (App Store) | No | $10M Series A (2025), about $15–18.5M total | [S, [TechCrunch](https://techcrunch.com/2025/03/07/collx-raises-10m-to-grow-its-card-collection-marketplace)] |
| **Market Movers** (Sports Card Investor) | Price analytics | $9.99–$49.99/month, $99.99–$499.99/year | No | n/a | [S, App Store snapshot] |
| **Ludex** | AI scanner and price guide | $4.99–$24.99/month | No | $8M seed (March 2023) | [P, [Ludex press](https://www.ludex.com/press/trading-card-scanner-and-price-guide-app-ludex-raises-8m-in-seed-round-investors-include-nfl-athletes-brian-urlacher-and-cassius-marsh)]; pricing [S] |
| **Alt** | Marketplace, vault (Delaware), lending | Vault incl. insurance free for supported graded cards (earlier 0.39%/year) | Yes, in vault, "dynamic" | About $106M equity, $200M debt (2022) | [S, [Dealroom](https://dealroom.co/companies/alt-platform/), [fintech.global](https://fintech.global/2022/07/22/investing-platform-alt-raises-200m-in-debt/)] |
| **Courtyard** | Tokenized graded cards, Brink's vault, digital packs | n/a | Vaulted | $30M Series A (Forerunner, July 2025), about $37.5M total | [P, [Courtyard blog](https://courtyard.io/blog/post/courtyard-io-raises-30-million-series-a-to-reimagine-collecting-71e8c1e9ef05)] |
| **Arena Club** | Grading, vault, showroom (Derek Jeter) | n/a | Not found | $10M Series A, about $20M total | [S, [SportBusiness](https://sportbusiness.com/news/derek-jeters-arena-club-raises-10m-in-funding-round)] |
| **Fanatics Collect** (ex-PWCC) | Marketplace and vault | Vault free; fees on withdrawal or sale | "Fully insured" in vault | Part of Fanatics | [S, [Topps FAQ](https://topps.com/pages/ship-to-vault)] |
| **eBay vault** (PSA-operated terms) | ≥$250 graded singles | Fees on eBay fee page | eBay-held insurance in vault | n/a | [P, [terms](https://www.ebay.com/vault/terms)] |
| **PSA app** | Free collection value tracking | Free | No | n/a | [S] |

**Pattern [U]:** insurance today is either (1) generalist collectibles policies that are not card-native, or (2) custodial, meaning it applies only while the card sits in someone's vault or mailbag. **Nobody found offers card-native, cert-number-scheduled, at-home coverage tied to live comps.** That is the white space. WAX Flex (dynamic premium) is the closest substitute, and Collectors is the best-placed incumbent to fill it.

---

## 3. Insurance mechanics

### Rates, deductibles, structure

- **Rates:**
  - The "industry typical" rate is about $0.50 per $100 of value per year for collectibles [S, [PropertyCasualty360, 2010](https://propertycasualty360.com/2010/07/25/who-will-cover-my-shrunken-heads)].
  - Recent guides cite CIS/American Collectors at $0.50–$1.00 per $100 [S, [thecardshopfinder](https://thecardshopfinder.com/blog/how-to-insure-valuable-card-collection/)], and $150–500/year for $50k–250k of graded cards [S, [Pregrade](https://pregradecards.com/blog/insurance-graded-cards-coverage-guide-2026)].
  - Other guides say 0.5–2% of value [S, [Benzinga](https://benzinga.com/money/best-collectibles-insurance)].
  - **No carrier publishes a rate table**. Founders should get 3–5 real quotes for test collections [U].
- **Deductibles:** CIS collector policies start at $0 and dealer policies at $500 [P].
- **Scheduled vs blanket:**
  - CIS covers unscheduled items on a market-value basis but requires scheduling at $25k and above [P].
  - Chubb and American Collectors use agreed value with newly-acquired-item grace periods (90 and 30 days) [P].
  - WAX offers blanket coverage for large collections [P, First Connect].
- **Homeowners/renters sublimits:** ISO HO forms carry a $1,500 special limit on stamps and securities. Trading cards aren't clearly named, and losses are often settled at ACV [S, [Property Insurance Coverage Law](https://www.propertyinsurancecoveragelaw.com/blog/review-of-the-farmers-next-generation-homeowners-policy-part-4-special-limits-on-certain-personal-property/)]. Some carrier forms do name cards: one reported State Farm form limits stamps, trading cards and comics to $2,500, and another form caps $200 per card and $2,500 total [S, same]. **This sublimit gap is the core consumer pitch, but founders should pull 3–4 actual HO-3/HO-4 forms to quote verbatim [U].**
- **Claims valuation for graded cards [U, synthesis]:**
  - Agreed value means the scheduled amount minus deductible [P, American Collectors FAQ].
  - Market value means comps at claim time, which works against the insured in a falling market.
  - Graded cards have unusually good evidence for this: the cert number (PSA API), PSA SecureScan images (PSA says these are useful "for insurance purposes" [S, via PSA FAQ snippet]), and grade-specific sold comps.
  - Weak points: population changes, regrades/crossovers, cracked slabs, and counterfeit slabs.

### How a startup sells insurance

- **Producer license:** anyone who sells, solicits or negotiates P&C insurance must be licensed in each state [P, [NAIC Producer Licensing Model Act #218](https://content.naic.org:443/sites/default/files/model-law-218.pdf)]. Unlicensed referral-fee rules vary by state [U]. Check before paying influencers or dealers per policy.
- **Distribution models:**
  - (1) **Agency/producer:** license the entity, appoint with carriers or an MGA, earn commission.
  - (2) **MGA:** underwriting and binding authority delegated by a carrier. Higher economics, but the carrier needs data, capital and controls. Example: WAX on Chubb paper.
  - (3) **Embedded:** use an embedded-insurance platform (CardCastle + Sure) or a shipping insurer (Cabrella).
  - (4) **"Brand + agency"** (Hodinkee + Chubb).
- **Commission benchmarks:**
  - WAX pays agents 8% on new and renewal business [P].
  - One carrier schedule shows personal inland marine at 15% [P, [Encova exhibit](https://encova.com/globalassets/encova-site/corporate-communications/exhibit-c---commission-rates-updated-6.10.22.pdf)].
  - Overrides are commonly 1–5% [S, [InsurerBrain](https://www.insurerbrain.com/wiki/Definition:Commission_override)].
  - Total MGA compensation of about 20–30% of premium [U, not sourced] is a common industry rule of thumb that should be validated with the brokerage-VP founder.
- **Where the brokerage-VP founder fits [U]:**
  - Licensing and appointments.
  - Carrier relationships (personal-lines inland marine, specialty).
  - Credibility with carrier program managers.
  - A possible agent channel (independent agents cross-selling to HNW clients).
  - BrokerTech Ventures and InsurTech NY's MGA Lab (93 applicants and 13 selected in 2026 [S, [InsurTech NY](https://www.insurtechny.com/?p=16241)]) are broker- and MGA-focused programs.

---

## 4. Market size and rough TAM/SAM/SOM

### Data points

- **Collectors:**
  - 19% of US adults bought Pokémon cards for themselves in the past six months [S, Circana March 2025 via [Chain Store Age](https://chainstoreage.com/study-toys-was-fastest-growing-industry-early-2025)].
  - 12% of Americans collect "some type of trading cards" [S, MagnifyMoney survey, about 2022, [SCD](https://www.sportscollectorsdaily.com/collecting-survey/)].
- **Market size estimates:**
  - US trading cards about $5.9B (2025) [S, [Grand View](https://www.grandviewresearch.com/industry-analysis/us-trading-cards-market-report)].
  - Global sports cards about $13.5B [S].
  - Global TCG $7.8–13.3B [S].
  - These are low quality; methodologies differ.
- **eBay:**
  - Collectibles were "the largest contributor to GMV growth in Q4 2025," driven by trading cards. Trading-card GMV growth accelerated for 10 straight quarters (through Q2 2025).
  - eBay expected a 2-point GMV headwind in 2026 from lapping cards and bullion.
  - No dollar figure was disclosed [S, earnings transcripts: [Q4 2025](https://www.marketbeat.com/earnings/reports/2026-2-18-ebay-inc-stock/), [Q3 2025](https://www.fool.com/earnings/call-transcripts/2025/10/29/ebay-ebay-q3-2025-earnings-call-transcript)].
- **Shows:**
  - The National in Rosemont (August 2026) was its third straight record year. The organizer lists 100,000+ [S/P, [NSCC media](https://www.nsccshow.com/media-center), [SC Daily](https://www.sportscollectorsdaily.com/2026-national-continues-record-setting-growth/)].
  - Card Ladder reported $450M spent in January 2026 alone [S, CP24].
- **Average collection value signal:** Collectr has more than 4M users and $1.5B tracked, about $375 per user [S]. That figure is skewed by free users and TCG raw cards.

### Rough sizing (all [U]: explicit assumptions, meant to be argued with)

| Layer | Assumption | Result |
|---|---|---|
| **Graded cards in circulation (US)** | About 100–150M slabs. Uses 26.8M (2025) + 20M (2024) + roughly 15–25M per year in earlier years + 2026 run rate; about 85% US | — |
| **Value of graded cards** | Median graded card is low ($30–$100), but the value is fat-tailed. Assume an average of $150–$300 | **$15–45B** |
| **TAM (insurance premium)** | If all were insured at 0.5–1.0% | **$75–450M premium per year** |
| **SAM** | US collectors with ≥$10k in graded cards who would consider standalone coverage. Assume 200k–600k households holding about 40% of value; at 0.75% | **About $45–135M premium per year** |
| **SOM (year 5)** | 5,000–15,000 policies × $300 average premium | **$1.5–4.5M GWP** → about $0.3–1.1M commission at 20–25% (MGA) or $0.12–0.36M at 8% (agent) |
| **Software SOM** | 20k–60k paying subscribers × $60/year | $1.2–3.6M ARR |

**Implication [U]:** insurance commission alone at agent economics doesn't build a VC-scale company. MGA economics plus software plus B2B data or partnership revenue might support a seed round. Collectr (about 5 people, eight-figure ARR) shows that a lean subscription business in this hobby can be very profitable without insurance.

### Path to profitability (illustrative only [U])

- Lean team of 3–4 founders and contractors, burning about $40–60k per month (about $0.6M per year).
- Break-even mixes:
  - About 8k subscribers at $60/year, plus 2k policies × $300 × 20%, plus show and dealer revenue. That totals roughly $0.6M.
  - Or about 1,500 dealer and shop policies at higher average premium.
- The base-case timeline is 24–36 months *if* a carrier or MGA partnership is in place by month 6–9.

---

## 5. Valuation data sources and constraints

| Source | Access | Constraints | Conf. |
|---|---|---|---|
| **PSA Public API** | REST, OAuth2 using PSA account credentials | Cert verification only (card, grade). No pricing. Free tier rate-limited | [P, [psacard.com/publicapi](https://www.psacard.com/publicapi)]; scope [S, [cardgrader.ai](https://cardgrader.ai/blog/psa-api)] |
| **eBay Marketplace Insights API** (sold items) | "Limited Release." Buy APIs are only for developers approved by eBay business units | Needs approval. Default 5,000 calls per day elsewhere. Finding API completed items only went back 90 days (community answer) | [P, [eBay Buy APIs](https://developer.ebay.com/api-docs/buy/static/buy-overview.html)]; 90 days [S] |
| **Card Ladder** | Consumer subscription; Collectors-owned | ToS (Ladder Studios, updated 2024-12-30) couldn't be fetched. Assume no redistribution. Licensing would mean negotiating with a competitor's parent | [S, [cardladder.com/terms](https://cardladder.com/terms)] |
| **130point** | Public sold-price lookup | No API or terms found [U] | — |
| **Beckett price guide** | Subscription | Beckett has sued scrapers for ToS breach and copying [S, [Cardboard Connection](https://www.cardboardconnection.com/law-of-cards-beckett-sues-two-more-for-scraping-data/amp)] | |
| **Affiliate feeds** (eBay Partner Network, TCGplayer) | Collectr uses these for values [S] | Affiliate terms govern display; not built for insurance valuation [U] | |

**Takeaway [U]:** "real-time verifiable value" is only as good as the comp feed. Every high-quality feed is owned by a potential competitor (Collectors or eBay) or locked behind approval. Cabrella's PSA deal shows insurers accept Card Ladder and Beckett as valuation references, which suggests licensing is possible.

---

## 6. Estate planning and brokerage integration

- **Fidelity Full View:** run by eMoney Advisor (a Fidelity affiliate). Manual accounts are supported, but the user must update them, and new Full View only accepts a total balance with no holdings detail [P, [Fidelity FAQ](https://www.fidelity.com/go/full-view-faqs); S, [Finance Buff](https://thefinancebuff.com/fidelity-full-view-gps-track-portfolio.html)]. Collectibles show up as "Unknown" in allocation [S, Reddit]. **No collectibles data-feed partner was found.**
- **Precedent for alternatives in wealth platforms:** Addepar's Appraisal Bureau integration syncs aggregate art valuations daily by medium, not item-level [P, [Addepar](https://integrations.addepar.com/product/appraisal-bureau)]. Addepar says about 40% of the roughly $9T on its platform is in alternatives [S]. Wag Art and Altoo offer collectibles valuation feeds into wealth platforms [S]. **A realistic long-term path is to be the card-valuation provider to aggregators (eMoney, Addepar, Plaid-style) for RIAs, rather than consumer Fidelity directly [U].** No evidence was found for Altruist or Plaid held-away collectibles support.
- **Beneficiary designation / TOD:** TOD is mainly for securities, accounts, real estate (TOD deeds in about 30 states + DC), and titled property such as vehicles in some states (e.g., South Carolina DMV titles [P, [SC statute/bill](https://www.scstatehouse.gov/sess125_2023-2024/bills/5189.htm)]). **Untitled tangible personal property like cards generally cannot carry a TOD/beneficiary designation [S/U].** Cards pass by will, trust, or a **UPC §2-513 "separate writing"** listing tangible personal property, which can be updated without re-executing the will [P, e.g. [Utah §75-2-513](https://le.utah.gov/xcode/Title75/Chapter2/C75-2-S513_1800010118000101.html), [Colorado §15-11-513](https://colorado.public.law/statutes/crs_15-11-513)]. State rules vary: for example, Minnesota excludes coin collections and Maine repealed its version [S, ezel.ai].
  - **Product implication [U]:** a "beneficiaries" feature is legally an inventory plus a state-compliant separate-writing memorandum or trust schedule, not a TOD. Estate-attorney input is needed to avoid unauthorized practice of law.
- **Tax:** net capital gains on collectibles are taxed at a maximum of 28% [P, [IRS Topic 409, reviewed 2026-09-24](https://www.irs.gov/taxtopics/tc409)]. Cost-basis records (grading fees count toward basis [U]) are a concrete record-keeping value prop. Step-up in basis at death [U, verify] makes date-of-death valuations valuable for heirs.

---

## 7. Funding landscape

- **Collectibles tech (recent rounds):**
  - Courtyard: $30M Series A (2025) [P].
  - CollX: $10M Series A (2025) [S].
  - Packz: $10.7M seed (April 2026) [S, [VCBacked](https://www.vcbacked.co/company/packz)].
  - CardNexus: €3.5M (June 2026) [S, [Pulse 2.0](https://pulse2.com/cardnexus-raises-e3-5-million-to-build-a-mobile-marketplace-for-trading-card-games/amp/)].
  - Chance Studios: $3.2M (2026) [S].
  - Arena Club: $10M Series A [S].
  - Collectors: $4.3B valuation (2022) [S].
  - Fanatics Collectibles reportedly raised $350M at a $10.4B valuation (date unverified) [S, [FOS](https://frontofficesports.com/fanatics-trading-cards-raises-350m-valued-at-10-4b)].
- **Collectibles insurtech:** WAX seed of about $10M [S]. No 2025–26 card-insurtech rounds were found.
- **Non-VC options:**
  - BrokerTech Ventures (broker-backed, $50k per company, 2026 cohort of 9) [S].
  - InsurTech NY MGA Lab [S].
  - Dearborn Labs Launchpad (targets MGAs already writing more than $10M in premium, so too late-stage) [S, [Coverager](https://coverager.com/dearborn-labs-announces-launchpad-an-ai-insurance-accelerator-that-funds-and-builds-ai-infrastructure-for-mgas/)].
  - Carrier venture arms (Nationwide, Starr, Tokio Marine listed as InsurTech NY partners) [S].
  - Angels from the hobby (Collectr's model: $500k friends and family [S]; CollX and Courtyard had athlete angels).
  - Revenue-based financing once ARR exists [U].
- **Pitch framing [U]:** VCs will ask "why won't Collectors do this?" The evidence above (Cabrella exclusivity, the PSA app) makes that the first slide to address.

---

## 8. Revenue streams and unit-economics benchmarks

| Stream | Benchmark | Conf. |
|---|---|---|
| Consumer subscription | Collectr $7.99/month; CollX $10/month; Card Ladder $20/month; Market Movers $9.99–49.99/month; Ludex $4.99–24.99/month | [S] |
| Insurance commission | Agent 8% (WAX); carrier inland marine 15%; MGA total about 20–30% | [P]/[P]/[U] |
| Affiliate / marketplace | Collectr monetizes eBay/TCGplayer affiliate data and an ad network (550M impressions) | [S] |
| Grading submission service | Bulk "submitter" margin on PSA/CGC tiers. PSA Collectors Club is required for Value tiers [U] | [U] |
| Shipping / show-floor coverage | Cabrella model (per-shipment opt-in fee) | [P] |
| Lending against collections | WAX Credit, Alt Advance | [P]/[S] |
| B2B valuation/data feed | Appraisal Bureau → Addepar precedent | [P] |
| Dealer / card-shop policies | Shops report a lack of carriers | [S] |
| Estate add-ons | Separate-writing generation, heir reports, attorney referrals | [U] |

---

## Where the founders' assumptions look wrong or unverified

1. **"Only WAX works with an insurer":** false (§2). WAX is the closest analog, but it is generalist, Chubb-backed, and already ships dynamic pricing.
2. **"Grading checkout is the on-ramp":** PSA gave the inbound-shipping insurance slot exclusively to Cabrella (April 2026). The checkout belongs to PSA, and Card Shield would need to be a PSA partner or approach the customer *before* or *after* grading.
3. **"PSA prices rising sharply":** true at the bottom end ($19.99 → $39.99 in about 13 months). But PSA also cut the floor (Standard $59.99 vs $79.99 Priority) and rationed capacity. Higher prices may signal higher-value submissions, which is good for insurance, but also fewer, pricier submissions.
4. **"Narrowness makes underwriting easier":** partly true (cert API, images, comps). Untested on volatility, theft clustering, fake slabs, and concentration at shows and in the mail. No public loss data was found.
5. **"Graded cards only":** the PSA app, Collectr and Cabrella all handle raw cards. Graded-only cuts the funnel but improves verifiability. This is a deliberate trade-off to defend.
6. **"Shows up in Fidelity as part of the portfolio and beneficiary process":** Fidelity Full View only supports manual totals today. Beneficiary designation for cards isn't legally a TOD. Both pieces are far off.
7. **"Cheaper than general insurance":** standalone collectibles rates ($0.50–1.00 per $100) are already low. Card Shield's advantage over CIS or American Collectors would have to come from UX, valuation and claims speed rather than price, unless loss data later shows that graded cards deserve lower rates.

---

## Open questions for the founders (for the grill sessions)

1. Why would PSA/Collectors not extend Cabrella (or build in-house) to at-home collection coverage within 12–18 months, given they already own grading, the vault, Card Ladder, the app and the checkout? What is the counter-position: partner with them, sell to them, or go around them?
2. What is the minimum collection value at which a collector will pay a separate premium? Is the target the about-$375 median app user or the top 5%?
3. Agent, MGA, or embedded partner? Which carrier would you approach first, and what loss data or underwriting rules would they need from a pre-revenue startup?
4. How does the product beat WAX Flex (dynamic premium, 150% agreed value, in-app bind, Chubb paper) for a card collector specifically?
5. Where does live valuation data come from, legally? What happens to agreed values and premiums when the market drops 30%?
6. Is the first customer the collector, the card shop or dealer (which reportedly can't get coverage), or the show organizer?
7. Is the estate feature an inventory, or a legal instrument? Who drafts state-compliant separate-writing memos, and how do you avoid unauthorized practice of law?
8. Graded-only versus raw cards: what do you lose by excluding raw cards when PSA and Collectr include them?
9. What is the fraud model: fake slabs, cert swaps, inflated declared values, claims after a market drop?
10. Is this a venture business or a profitable niche agency plus app? Your answer determines whether VC is even the right capital.
11. How would claims be handled differently ("niche claims process"), and who adjusts claims: the carrier, a TPA, or you?
12. Does the brokerage-VP founder's employer have conflict, non-compete, or IP claims, and could that brokerage be a distribution partner?

## Suggested next steps (evidence-gathering, not prescriptions)

**Customer discovery at card shows** (dealers and collectors separately). Ask:
- "What's in your collection, roughly by value band (<$1k, 1–10k, 10–50k, 50k+)? How much is graded?"
- "Is any of it insured today? With whom, and how did you choose? Have you ever made a claim, and how did it go?"
- "Do you know what your homeowners/renters policy pays for cards?" (Then show the $1,500/$2,500 sublimit examples.)
- "What do you use to track value: PSA app, Collectr, Card Ladder, a spreadsheet? What's missing?"
- "If something happened to you, would your family know what the cards are worth and how to sell them?"
- "What would you pay per year to insure $10k of slabs? $50k?" (Then anchor to real quotes from CIS and American Collectors.)
- Dealers: "Have you been declined or non-renewed? What do you pay, and what does it exclude: shows, transit, inventory in the car?"
- Track: collection value, graded share, current insurance, and stated price at three value bands.

**Desk validation (cheap):**
- Get live quotes from CIS, American Collectors and WAX for three test collections ($5k, $25k, $100k graded).
- Pull 3–4 HO-3/HO-4 forms and quote the card sublimits verbatim.
- Ask PSA/Collectors business development and Cabrella whether partners are allowed beyond inbound shipping.
- Approach the eBay developer program about Marketplace Insights access.

**Pilot shapes that the evidence supports considering:**
- (a) **Show-floor pilot:** a booth at a regional show (before the next National, August 2027) offering a free "collection inventory + sublimit check + beneficiary list" report, with referral to a partner policy (CIS, American Collectors or WAX) through the founder's licensed agency. Measure attach rate.
- (b) **Dealer/shop program:** 10–20 card shops, coverage brokered through the founder's network. Measure declines, premiums and loss experience.
- (c) **Advisor channel:** 3–5 RIAs or estate attorneys get a PDF/CSV valuation schedule for clients' slabs. This tests the "B2B valuation feed" thesis before any Fidelity or Addepar conversation.
