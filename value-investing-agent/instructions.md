 Value Investing Agent — Task Instructions

 > Agent specification for collecting financial metrics across 19 tickers into a Google Sheets value investing tracker
>
> Sheet: Value Investing (Google Sheets)
> Rows to update: 2–20 (skip empty rows and IEF row for stock-specific columns)
> Do NOT edit the sheet directly — collect all values first, then present a paste-ready table.
>
> ---
>
> ## Tickers
>
> Row 2: TSM | Row 3: NVDA | Row 4: AAPL | Row 5: META | Row 6: GOOGL
> Row 7: PFE | Row 8: JNJ | Row 9: PSA | Row 10: KMB | Row 11: PG
> Row 12: KO | Row 13: WMT | Row 14: NKE | Row 15: AMCR | Row 16: AGCO
> Row 17: URI | Row 18: BRK-B | Row 19: V | Row 20: IEF (bond ETF — skip stock columns)
>
> ---
>
> ## Column Reference Map
>
> | Col | Header | Source | Notes |
> |-----|--------|--------|-------|
> | C | 股票代號 | — | Input ticker |
> | E | 殖利率(yield) | dividend.com | Yield % |
> | F | 股息(div) | dividend.com | Annual dividend $ |
> | G | 股息連續成長 | dividend.com | Consecutive years of increases |
> | H | 負債比< 50% | statementdog.com | V if all 5 years below 50%, else X |
> | I | 自由現金流量 | statementdog.com | V if 5-year sum > 0, else X |
> | J | ROE 五年穩定 | statementdog.com | V if all 5 years above 10%, else X |
> | K | 本益比在(V/X) | morningstar.com | V if L < M, else X |
> | L | 本益比 | morningstar.com | Current P/E |
> | M | 五年內平均本益比 | morningstar.com | 5-Yr Avg P/E |
> | N | EPS | finance.yahoo.com | EPS TTM |
> | O | PeterLynch Price | Calculated | = L × N |
> | P | Fair Price | valueinvesting.io | Fair value $ |
> | R | Jitta Score | jitta.com | Score number |
>
> ---
>
> ## Step 1 — Columns E, F, G (Dividend.com)
>
> URL: https://www.dividend.com
>
> 1. Click the magnifying glass icon in the top-right nav (NOT the hero search bar)
> 2. 2. Wait 2 seconds
>    3. 3. Type the ticker and click the stock link
>       4. 4. Collect:
>          5.    - E = First value under YIELD & DIV column
>                -    - F = Second value under YIELD & DIV column
>                     -    - G = Years of Dividend Increase
>                      
>                          - **Exceptions:**
>                          - - BRK-B pays no dividend — leave E/F/G as —
>                            - - IEF is a bond ETF — use its distribution yield for E, leave G as —
>                              - - If no dividend history, leave all three as —
>                               
>                                - ---
>
> ## Step 2 — Column H (Debt Ratio)
>
> URL: https://statementdog.com/analysis/$TICKER/financial-structure-ratio
>
> 1. Select 年報 (Annual Report toggle)
> 2. 2. Look at 負債比率 row across last 5 years
>    3. 3. V = all 5 years below 50%
>       4. 4. X = any year is 50% or above
>         
>          5. > Note: Statementdog has a daily free-view limit. If blocked, wait until next day.
>             >
>             > ---
>             >
>             > ## Step 3 — Column I (Free Cash Flow)
>             >
>             > URL: https://statementdog.com/analysis/$TICKER/cash-flow-statement
>             >
>             > 1. Select 年報
>             > 2. 2. Find 自由現金流量 row
>             >    3. 3. V = 5-year total sum > 0
>             >       4. 4. X = 5-year total ≤ 0
>             >         
>             >          5. ---
>             >         
>             >          6. ## Step 4 — Column J (ROE 5yr Stability)
>             >         
>             >          7. URL: https://statementdog.com/analysis/$TICKER/roe-roa
>
> 1. Select 年報
> 2. 2. Look at ROE row across last 5 years
>    3. 3. V = all 5 years above 10%
>       4. 4. X = any year is 10% or below
>         
>          5. ---
>         
>          6. ## Step 5 — Columns K, L, M (P/E Ratio — Morningstar)
>         
>          7. URL (try NYSE first): https://www.morningstar.com/stocks/xnys/$TICKER/valuation
> If no data: try xnas: https://www.morningstar.com/stocks/xnas/$TICKER/valuation
>
> Find the Price/Earnings row in the valuation table:
> - L = Current P/E (the "Current" column)
> - - M = 5-Yr average P/E (the "5-Yr" column)
>   - - K = V if L < M; X if not
>    
>     - ---
>
> ## Step 6 — Column N (EPS TTM — Yahoo Finance)
>
> URL: https://finance.yahoo.com/quote/$TICKER/
>
> Find EPS (TTM) in the summary statistics section.
>
> ---
>
> ## Step 7 — Column O (PeterLynch Price)
>
> No web visit needed — calculated:
> Column O = Column L × Column N (Current P/E × EPS TTM)
>
> ---
>
> ## Step 8 — Column P (Fair Value — valueinvesting.io)
>
> Search the web for: `fair value $TICKER site:valueinvesting.io`
> Read the fair value from the search snippet/summary.
>
> ---
>
> ## Step 9 — Column R (Jitta Score)
>
> URL (try NYSE first): https://www.jitta.com/stock/nyse:$TICKER
> If not found: try nasdaq:$TICKER
> For BRK-B: use nyse:brk.b (lowercase, dot notation)
>
> Find and record the Jitta Score on the summary page.
> > IEF (bond ETF) is not on Jitta — leave as —
> >
> > ---
> >
> > ## Output Format
> >
> > Present results as a single paste-ready table:
> >
> > | Row | Ticker | E (Yield%) | F (Div$) | G (Yrs) | H (Debt) | I (FCF) | J (ROE) | K (PE cmp) | L (PE curr) | M (PE 5yr) | N (EPS) | O (PL Price) | P (Fair Val) | R (Jitta) |
> > |-----|--------|------------|----------|---------|----------|---------|---------|------------|-------------|------------|---------|--------------|--------------|-----------|
> >
> > ---
> >
> > ## Known Issues / Site Quirks
> >
> > | Site | Issue | Workaround |
> > |------|-------|------------|
> > | dividend.com | Cloudflare blocks direct URL navigation | Always start from homepage, use search bar |
> > | statementdog.com | Daily free-view limit | Wait until next day or log in |
> > | morningstar.com | May be inaccessible in some environments | Fill manually if blocked |
> > | valueinvesting.io | Free view limit after a few stocks | Search web for "fair value $TICKER site:valueinvesting.io" |
> > | jitta.com | Some NYSE tickers only work under nasdaq: prefix | Try both prefixes |
> > | jitta.com | IEF and some ETFs not listed | Leave as — |
> >
> > ---
> >
> > *Last sheet structure verified: 2026-06-24*
> > *To run: open this file in Claude Chrome Extension and say "Execute rows 2–20" (or specify rows)*
