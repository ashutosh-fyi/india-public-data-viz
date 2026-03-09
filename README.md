# India Public Data Visualised

Interactive visualisations built from publicly available Indian government datasets — with context on why the numbers matter right now.

## India's LPG Vulnerability — Strait of Hormuz Crisis Dashboard

**[View Live Dashboard](https://ashutosh-fyi.github.io/india-public-data-viz/)**

![Choropleth preview](india_lpg_choropleth.png)

### Why this, why now?

This started with a [tweet from @PetroleumMin](https://x.com/PetroleumMin/status/2031058085952000251) sharing the state-wise breakdown of active domestic LPG connections. A seemingly routine data release — until you overlay it with what's happening in the Strait of Hormuz right now.

**329.7 million households** depend on LPG for daily cooking. That's the number on this map. Here's what makes it urgent:

- **67% of India's LPG is imported.** Domestic production covers only ~12.8 MT against a total requirement of ~36 MT.
- **85–90% of those imports flow through the Strait of Hormuz** — the same chokepoint that Iran's IRGC has effectively blockaded since late February 2026, following the US-Israel strikes.
- **India has ~10 days of LPG buffer stock** (~1 MT storage against ~3 MT monthly demand). Compare that to 40+ days of strategic petroleum reserves for crude oil. LPG has no such cushion.
- **103.3 million of those connections are Ujjwala (PMUY) beneficiaries** — the poorest households, already underconsuming at 3.95 cylinders/year vs ~8 for others. They'll be hit first.
- **38 Indian ships are reported stuck** in the Persian Gulf region. Several tankers carrying crude and LPG to India are unable to move freely.
- The government has already [ordered refiners to maximise domestic LPG output](https://www.business-standard.com/economy/news/govt-orders-refiners-to-boost-lpg-output-as-hormuz-disruption-worsens-126030601208_1.html), [raised the booking gap to 25 days to curb hoarding](https://www.businesstoday.in/india/story/government-moves-to-curb-hoarding-as-lpg-demand-spikes-booking-gap-raised-to-25-days-519766-2026-03-09), and some cities like Pune have [shut gas crematoriums](https://www.businesstoday.in/india/story/iran-war-disrupts-lpg-supply-pune-shuts-gas-crematoriums-punjab-halts-commercial-supply-519763-2026-03-09) while Punjab has halted commercial LPG supply.

### What the dashboard shows

The dashboard layers multiple public datasets to tell the full story:

**Stat bar** — six numbers that frame the crisis at a glance:

| Metric | Value |
|---|---|
| Active LPG connections | ~3,297 lakh (329.7M households) |
| Import dependency | ~67% |
| Share of imports via Hormuz | ~85–90% |
| LPG buffer stock | ~10 days |
| Ujjwala (poorest) connections | 103.3M (31% of total) |
| Brent crude | ~$88/bbl (+23% since Feb 28) |

**Interactive choropleth map** — state-wise LPG connections with:
- Hover to see total connections, Ujjwala count, and percentage bar per state
- **Ujjwala overlay toggle** — switches the map to show concentration of the poorest households (purple scale). Bihar, UP, West Bengal, Odisha light up hardest — these states have >50% Ujjwala share.
- Click any state to zoom in

**Brent crude price chart** — daily prices from FRED showing the $71 → $114 peak → $88 trajectory, with the crisis zone (post-Feb 28) highlighted in red.

**LPG import source donut** — built from [World Bank WITS](https://wits.worldbank.org/) HS 271112 trade data (2023). Shows that 95% of India's propane imports come from four Gulf countries — all transiting the Strait of Hormuz:
- UAE: 30.5%
- Qatar: 28.4%
- Saudi Arabia: 18.2%
- Kuwait: 17.8%
- USA: 1.6% (the only significant non-Hormuz source)

**Context panel** — auto-updating blockade day counter, summary of government response, and source links.

### Data sources

| Dataset | Source | Format |
|---|---|---|
| State-wise active domestic LPG customers (Apr 2025) | [PPAC](https://ppac.gov.in/consumption/active-domestic-customers) | XLS |
| State-wise PMUY (Ujjwala) connections (Apr 2025) | [PPAC](https://ppac.gov.in/consumption/state-wise-pmuy-data) | XLS |
| Brent crude daily prices (Jan 2025–Mar 2026) | [FRED DCOILBRENTEU](https://fred.stlouisfed.org/series/DCOILBRENTEU) | CSV |
| LPG import by source country (2023, HS 271112) | [World Bank WITS](https://wits.worldbank.org/trade/comtrade/en/country/IND/year/2023/tradeflow/Imports/partner/ALL/product/271112) | Web/XLS |
| India state boundaries GeoJSON (2019) | [india-in-data/india-states-2019](https://github.com/india-in-data/india-states-2019) | GeoJSON |

### Further reading

- [How One LPG Cylinder in Your Kitchen Is Linked to the Strait of Hormuz](https://thebetterindia.com/informed-india/how-much-of-indias-crude-oil-petrol-and-lpg-depends-on-the-strait-of-hormuz-11168960) — The Better India
- [Strait of Hormuz crisis reshapes global oil markets](https://www.kpler.com/blog/us-iran-conflict-strait-of-hormuz-crisis-reshapes-global-oil-markets) — Kpler
- [LPG import dependence meets Hormuz disruption](https://www.policycircle.org/economy/india-lpg-import-hormuz-disruption/) — Policy Circle
- [20% of global oil at risk as Hormuz blockade halts ships](https://www.businesstoday.in/latest/economy/story/20-of-global-oil-at-risk-as-hormuz-blockade-halts-ships-crude-surges-36-in-a-week-of-iran-israel-conflict-519557-2026-03-07) — Business Today
- [2026 Strait of Hormuz crisis](https://en.wikipedia.org/wiki/2026_Strait_of_Hormuz_crisis) — Wikipedia
- [Govt orders refiners to boost LPG output](https://www.business-standard.com/economy/news/govt-orders-refiners-to-boost-lpg-output-as-hormuz-disruption-worsens-126030601208_1.html) — Business Standard
- [Global markets reeling as Brent surges past $114](https://markets.financialcontent.com/stocks/article/marketminute-2026-3-9-global-markets-reeling-as-brent-crude-surges-past-114-following-targeted-strikes-on-iranian-energy-infrastructure) — MarketMinute

### Tech

Leaflet.js, Canvas charts, GeoJSON, vanilla JS — no build step, no dependencies beyond Leaflet.

---

*More visualisations will be added as interesting public datasets surface.*
