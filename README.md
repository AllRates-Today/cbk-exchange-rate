# Central Bank of Kuwait Exchange Rates API — cbk-exchange-rate

[![npm version](https://img.shields.io/npm/v/cbk-exchange-rate.svg)](https://www.npmjs.com/package/cbk-exchange-rate)
[![license](https://img.shields.io/npm/l/cbk-exchange-rate.svg)](https://github.com/AllRates-Today/cbk-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/cbk-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/KWD today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fcbk%3Fsource%3DUSD%26target%3DKWD&query=%24.rate&label=USD%2FKWD%20published%20by%20Central%20Bank%20of%20Kuwait&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/cbk/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fcbk%3Fsource%3DUSD%26target%3DKWD&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/cbk/)

**Official Central Bank of Kuwait (Kuwait) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Central Bank of Kuwait itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Central Bank of Kuwait's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2008** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Central Bank of Kuwait itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Central Bank of Kuwait table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/cbk?source=USD&target=KWD"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/cbk').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Central Bank of Kuwait table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-08** by Central Bank of Kuwait — 134 rates, first 60 shown. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | KWD | reference | 0.083896 |
| AFN | KWD | reference | 0.004751 |
| ALL | KWD | reference | 0.003757 |
| AMD | KWD | reference | 0.000851 |
| AOA | KWD | reference | 0.000335 |
| ARS | KWD | reference | 0.000203 |
| AUD | KWD | reference | 0.21438 |
| AZN | KWD | reference | 0.181265 |
| BAM | KWD | reference | 0.176343 |
| BBD | KWD | reference | 0.152996 |
| BDT | KWD | reference | 0.002502 |
| BGN | KWD | reference | 0.183033 |
| BHD | KWD | reference | 0.819371 |
| BIF | KWD | reference | 0.000103 |
| BMD | KWD | reference | 0.30815 |
| BND | KWD | reference | 0.240676 |
| BOB | KWD | reference | 0.025797 |
| BRL | KWD | reference | 0.06136 |
| BSD | KWD | reference | 0.30815 |
| BTN | KWD | reference | 0.003184 |
| BWP | KWD | reference | 0.021725 |
| BZD | KWD | reference | 0.153217 |
| CAD | KWD | reference | 0.216041 |
| CDF | KWD | reference | 0.000133 |
| CHF | KWD | reference | 0.36995 |
| CLP | KWD | reference | 0.000315 |
| CNY | KWD | reference | 0.045971 |
| COP | KWD | reference | 0.000095 |
| CRC | KWD | reference | 0.000676 |
| CUP | KWD | reference | 0.01284 |
| CVE | KWD | reference | 0.003123 |
| CZK | KWD | reference | 0.014145 |
| DJF | KWD | reference | 0.00173 |
| DKK | KWD | reference | 0.04619 |
| DOP | KWD | reference | 0.005048 |
| DZD | KWD | reference | 0.002291 |
| ECS | KWD | reference | 0.000012 |
| EGP | KWD | reference | 0.005884 |
| ERN | KWD | reference | 0.020441 |
| ETB | KWD | reference | 0.001908 |
| EUR | KWD | reference | 0.345251 |
| FJD | KWD | reference | 0.136896 |
| GBP | KWD | reference | 0.407051 |
| GEL | KWD | reference | 0.118748 |
| GHS | KWD | reference | 0.026148 |
| GMD | KWD | reference | 0.004133 |
| GNF | KWD | reference | 0.000035 |
| GTQ | KWD | reference | 0.040307 |
| GYD | KWD | reference | 0.001473 |
| HKD | KWD | reference | 0.039266 |
| HNL | KWD | reference | 0.01148 |
| HTG | KWD | reference | 0.002353 |
| HUF | KWD | reference | 0.000943 |
| IDR | KWD | reference | 0.000017 |
| INR | KWD | reference | 0.003186 |
| IQD | KWD | reference | 0.000203 |
| IRR | KWD | reference | 0.000007 |
| ISK | KWD | reference | 0.00252 |
| JMD | KWD | reference | 0.00194 |
| JOD | KWD | reference | 0.434626 |

[Full table on the Central Bank of Kuwait rates page](https://allratestoday.com/central-bank-rates-api/cbk/) · Source: [Official rates published by CBK, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/cbk/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install cbk-exchange-rate
```

```bash
yarn add cbk-exchange-rate
```

```bash
pnpm add cbk-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/cbk-exchange-rate`](https://www.npmjs.com/package/@allratestoday/cbk-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'cbk-exchange-rate';

const pair = await getRate('USD', 'KWD', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Central Bank of Kuwait rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'KWD', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'cbk',
  name: 'Central Bank of Kuwait',
  rate_date: '2026-10-08',   // Central Bank of Kuwait's own publication date
  source: 'USD',
  target: 'KWD',
  rate: 0.30815,
  rate_type: 'reference',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'cbk-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'cbk',
  name: 'Central Bank of Kuwait',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "KWD", "type": "reference", "value": 0.30815 },
    // … the rest of the published table (134 currencies vs KWD)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2008 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'cbk-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'KWD' });
```

**Response:**

```javascript
{
  bank: 'cbk',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'cbk-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'KWD', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'cbk',
  source: 'USD',
  target: 'KWD',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 0.30815, rate_type: 'reference', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Central Bank of Kuwait currently publishes rates covering **134 currencies** against the KWD (as of the latest table):

🇦🇪 `AED` · 🇦🇫 `AFN` · 🇦🇱 `ALL` · 🇦🇲 `AMD` · 🇦🇴 `AOA` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇦🇿 `AZN` · 🇧🇦 `BAM` · 🇧🇧 `BBD` · 🇧🇩 `BDT` · 🇧🇬 `BGN` · 🇧🇭 `BHD` · 🇧🇮 `BIF` · 🇧🇲 `BMD` · 🇧🇳 `BND` · 🇧🇴 `BOB` · 🇧🇷 `BRL` · 🇧🇸 `BSD` · 🇧🇹 `BTN` · 🇧🇼 `BWP` · 🇧🇿 `BZD` · 🇨🇦 `CAD` · 🇨🇩 `CDF` · 🇨🇭 `CHF` · 🇨🇱 `CLP` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇨🇷 `CRC` · 🇨🇺 `CUP` · 🇨🇻 `CVE` · 🇨🇿 `CZK` · 🇩🇯 `DJF` · 🇩🇰 `DKK` · 🇩🇴 `DOP` · 🇩🇿 `DZD` · 🇪🇨 `ECS` · 🇪🇬 `EGP` · 🇪🇷 `ERN` · 🇪🇹 `ETB` · 🇪🇺 `EUR` · 🇫🇯 `FJD` · 🇬🇧 `GBP` · 🇬🇪 `GEL` · 🇬🇭 `GHS` · 🇬🇲 `GMD` · 🇬🇳 `GNF` · 🇬🇹 `GTQ` · 🇬🇾 `GYD` · 🇭🇰 `HKD` · 🇭🇳 `HNL` · 🇭🇹 `HTG` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇳 `INR` · 🇮🇶 `IQD` · 🇮🇷 `IRR` · 🇮🇸 `ISK` · 🇯🇲 `JMD` · 🇯🇴 `JOD` · 🇯🇵 `JPY` · 🇰🇪 `KES` · 🇰🇬 `KGS` · 🇰🇭 `KHR` · 🇰🇲 `KMF` · 🇰🇵 `KPW` · 🇰🇷 `KRW` · 🇰🇿 `KZT` · 🇱🇦 `LAK` · 🇱🇧 `LBP` · 🇱🇰 `LKR` · 🇱🇷 `LRD` · 🇱🇸 `LSL` · 🇱🇾 `LYD` · 🇲🇦 `MAD` · 🇲🇩 `MDL` · 🇲🇬 `MGA` · 🇲🇲 `MMK` · 🇲🇳 `MNT` · 🇲🇴 `MOP` · 🇲🇷 `MRU` · 🇲🇺 `MUR` · 🇲🇻 `MVR` · 🇲🇼 `MWK` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇲🇿 `MZN` · 🇳🇦 `NAD` · 🇳🇬 `NGN` · 🇳🇮 `NIO` · 🇳🇴 `NOK` · 🇳🇵 `NPR` · 🇳🇿 `NZD` · 🇴🇲 `OMR` · 🇵🇦 `PAB` · 🇵🇪 `PEN` · 🇵🇬 `PGK` · 🇵🇭 `PHP` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇵🇾 `PYG` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇸 `RSD` · 🇷🇺 `RUB` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇸🇧 `SBD` · 🇸🇨 `SCR` · 🇸🇩 `SDG` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇱 `SLL` · 🇸🇴 `SOS` · 🇸🇷 `SRD` · 🇸🇻 `SVC` · 🇸🇾 `SYP` · 🇸🇿 `SZL` · 🇹🇭 `THB` · 🇹🇳 `TND` · 🇹🇷 `TRY` · 🇹🇼 `TWD` · 🇹🇿 `TZS` · 🇺🇦 `UAH` · 🇺🇬 `UGX` · 🇺🇸 `USD` · 🇺🇾 `UYU` · 🇺🇿 `UZS` · 🇻🇪 `VEF` · 🇻🇳 `VND` · 🇼🇸 `WST` · 🇾🇪 `YER` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW`

## 🏛️ Source

The Central Bank of Kuwait manages the Kuwaiti dinar — the world’s highest-valued currency unit, pegged to an undisclosed basket of currencies. It publishes official daily exchange rates covering more than 130 currencies, with an archive reaching back to 2008 for the majors and to 2017 for the wider board.

- Publisher's own page: [Exchange rates](https://www.cbk.gov.kw/en/monetary-policy/market-operations/exchange-rates) · [www.cbk.gov.kw](https://www.cbk.gov.kw)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Central Bank of Kuwait rates page](https://allratestoday.com/central-bank-rates-api/cbk/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Central Bank of Kuwait quotes **KWD per 1 unit of foreign currency** (e.g. `base: "USD", quote: "KWD"` means KWD per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`reference` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Central Bank of Kuwait rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/cbk/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('cbk')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate cbk ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Central Bank of Kuwait does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via KWD from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Central Bank of Kuwait |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'cbk-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('cbk-exchange-rate');

getRate('USD', 'KWD', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2008 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/cbk.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/cbk/latest.json`

## 🔗 Links

- [Central Bank of Kuwait rates page](https://allratestoday.com/central-bank-rates-api/cbk/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/cbk-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/cbk-exchange-rate)

## 📜 License

MIT
