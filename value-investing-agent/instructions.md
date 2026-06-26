# Value Investing Agent — Task Instructions

> Agent specification for collecting financial metrics across 19 tickers into a Google Sheets value investing tracker

**Sheet:** Value Investing (Google Sheets)
**Rows to update:** 2–20 (skip empty rows and IEF row for stock-specific columns)
**Rule:** Do NOT edit the sheet directly — collect all values first, then present a paste-ready table.

---

## Tickers

| Row | Ticker | Notes |
|-----|--------|-------|
| 2 | TSM | Taiwan Semiconductor |
| 3 | NVDA | NVIDIA |
| 4 | AAPL | Apple |
| 5 | META | Meta Platforms |
| 6 | GOOGL | Alphabet |
| 7 | PFE | Pfizer |
| 8 | JNJ | Johnson & Johnson |
| 9 | PSA | Public Storage |
| 10 | KMB | Kimberly-Clark |
| 11 | PG | Procter & Gamble |
| 12 | KO | Coca-Cola |
| 13 | WMT | Walmart |
| 14 | NKE | Nike |
| 15 | AMCR | Amcor |
| 16 | AGCO | AGCO Corporation |
| 17 | URI | United Rentals |
| 18 | BRK-B | Berkshire Hathaway B |
| 19 | V | Visa |
| 20 | IEF | iShares 7-10 Year Treasury Bond ETF (bond ETF — skip stock columns) |

---

## Column Reference Map

| Col | Header | Source | Notes |
|-----|--------|--------|-------|
| C | 股票代號 | — | Input ticker |
| D | 股價 | Yahoo Finance | Current price |
| E | 52w High | Yahoo Finance | 52-week high |
| F | 52w Low | Yahoo Finance | 52-week low |
| G | EPS | Statementdog | TTM EPS |
| H | P/E | Calculated | D/G |
| I | Forward P/E | Yahoo Finance | Forward P/E ratio |
| J | 殖利率 | Dividend.com | Dividend yield % |
| K | 配息頻率 | Dividend.com | Annual / Quarterly / Monthly |
| L | Payout Ratio | Dividend.com or Morningstar | % |
| M | FCF per Share | Valueinvesting.io or Morningstar | Free cash flow per share |
| N | ROE | Morningstar | Return on equity % |
| O | Debt/Equity | Morningstar | Debt-to-equity ratio |
| P | Jitta Score | Jitta.com | Quality score 0–10 |
| Q | Jitta Line | Jitta.com | Intrinsic value estimate |

---

## Data Collection Rules

### Per-Site Instructions

**Yahoo Finance** (finance.yahoo.com)
- Navigate to `/quote/[TICKER]`
- Collect: current price, 52w high, 52w low, forward P/E
- Note: BRK-B uses "BRK-B" in URL

**Statementdog** (statementdog.com)
- Navigate to `/analysis/[TICKER]`
- Collect: EPS (TTM)
- Note: TSM uses "2330" on Taiwanese version

**Dividend.com** (dividend.com)
- Navigate to `/dividends/[TICKER]`
- Collect: dividend yield, payout frequency, payout ratio
- Note: IEF — skip this source (bond ETF)

**Morningstar** (morningstar.com)
- Navigate to `/stocks/xnas/[TICKER]/quote`
- Collect: ROE, debt/equity, payout ratio (if not found on Dividend.com)
- Note: May hit daily view limit — use fallback if blocked

**Valueinvesting.io** (valueinvesting.io)
- Navigate to `/stock/[TICKER]`
- Collect: FCF per share
- Note: May require ticker format adjustment

**Jitta** (jitta.com)
- Navigate to `/stock/[TICKER]`
- Collect: Jitta Score, Jitta Line
- Note: Requires login; Cloudflare may block — retry or skip

---

## Exception Handling

| Ticker | Issue | Workaround |
|--------|-------|------------|
| TSM | Statementdog uses TWD ticker "2330" | Use 2330 for Statementdog; TSM for others |
| BRK-B | Yahoo Finance URL uses "BRK-B" | Use BRK-B in URL |
| IEF | Bond ETF — no dividend.com page | Skip dividend yield, payout ratio for IEF |
| Any | Cloudflare block on Jitta | Wait 30s and retry once; skip if blocked again |
| Any | Morningstar daily view limit | Use Macrotrends as fallback for ROE/D/E |

---

## Output Format

After collecting all data, output a paste-ready table:

```
Row | Ticker | Price | 52wH | 52wL | EPS | P/E | Fwd P/E | Yield | Freq | Payout | FCF/sh | ROE | D/E | Jitta | JLine
2   | TSM    | ...   | ...  | ...  | ... | ... | ...     | ...   | ...  | ...    | ...    | ... | ... | ...   | ...
...
```

Mark any missing data as `N/A`. Do not skip rows.
