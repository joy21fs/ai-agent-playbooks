 Job Search Agent — Task Instructions

 > Agent specification for daily job screening across LinkedIn, Cake.me, 104.com.tw, and Yourator
>
> ---
>
> ## Candidate Profile
>
> **Role:** Frontend Engineer, 3+ years production experience
> **Core skills:** React, TypeScript, Next.js, Vite
> **AI/LLM experience:** Claude API, Vercel AI SDK, OpenAI API, prompt engineering, streaming chat UI
> **Side work:** LLM evaluation / AI data quality (DataAnnotation, freelance)
> **English:** TOEFL 103, TOEIC 975, Master's degree from Arizona State University, US work experience
> **GitHub:** github.com/joy21fs
>
> ## Location Constraints
>
> - ✅ Taichung-based (any district)
> - - ✅ 100% Remote (Taiwan-eligible)
>   - - ❌ Taipei-only office (non-remote)
>     - - ❌ Requires relocation
>      
>       - ## Work Style Preferences
>      
>       - - No overtime culture
>         - - Independent work style
>           - - English-language environment preferred (not required)
>            
>             - ---
>
> ## Target Role Types (Priority Order)
>
> 1. Frontend Engineer with AI/LLM focus
> 2. 2. AI Application Engineer / Full Stack + AI integration
>    3. 3. AI Automation Engineer (n8n, Make, Claude Code, MCP)
>       4. 4. LLM Evaluator / AI Data Quality roles
>          5. 5. Solutions Engineer / Technical Account Manager (low client-facing frequency)
>             6. 6. AI Quality Analyst / Bilingual AI Trainer
>               
>                7. ---
>               
>                8. ## Hard Filters — Auto-Skip
>               
>                9. - ❌ Gambling / 博弈 industry (and adjacent: crypto exchanges, suspicious offshore payment patterns)
> - ❌ Taipei-only office (not remote, not Taichung)
> - - ❌ Partial remote / hybrid only (only accept 100% remote)
>   - - ❌ Field sales / outside sales (external client visits as primary job function)
>     - - ❌ Non-engineering roles with no technical component (pure marketing, pure admin)
>       - - ❌ Technical Writer roles (pure writing, no engineering)
>        
>         - ---
>
> ## Search Platforms & Keywords
>
> | Platform | Keywords | Filters |
> |----------|----------|---------|
> | LinkedIn | `frontend engineer AI LLM -Binance`, `AI automation engineer Taiwan`, `solutions engineer Taiwan remote` | f_WT=2 (Remote), f_TPR=r86400 (past 24h) |
> | Cake.me | `AI automation engineer remote`, `Frontend Engineer AI LLM remote`, `AI engineer LLM remote Taiwan` | Remote filter on |
> | 104.com.tw | `AI LLM 工程師`, `前端工程師 AI`, `生成式 AI 工程師` | area=6014010000 (Taichung) OR ro=1 (remote) |
> | Yourator | `AI LLM engineer remote`, `frontend AI remote` | remote=true |
>
> ---
>
> ## Evaluation Format (per listing)
>
> For each qualifying job, evaluate across 8 dimensions:
>
> ```
> ### [N]. [Job Title] @ [Company]
> **Platform:** LinkedIn / Cake / 104 / Yourator
> **Job Type:** Engineer / AI Quality / Solutions / Other
> **Match Score:** X / 10
> **Strengths:** (direct profile-to-JD matches)
> **Gaps:** (honest assessment of missing skills)
> **Red Flags:** (company or role concerns, or "None")
> **Salary:** (disclosed amount or "Not disclosed")
> **Location:** Taichung in-person / 100% Remote
> **Link:** [URL]
> **Verdict:** 🟢 Invest / 🟡 Consider / 🔴 Skip — [one-sentence reason]
> ```
>
> **Scoring guidance:**
> - 8–10: Strong match on both technical skills and role type
> - - 6–7: Good match with 1–2 gaps that are learnable
>   - - 4–5: Partial match, significant gaps or concerns
>     - - 1–3: Poor fit, skip unless exceptional circumstances
>      
>       - > **Honesty rule:** Do not inflate scores. If a role requires skills the candidate does not have, say so clearly.
>         >
>         > ---
>         >
>         > ## Report Output Format
>         >
>         > ```
>         > # 求職日報 — [Date]
>         >
>         > 搜尋平台：LinkedIn、Cake.me、104.com.tw、Yourator
>         > 篩選條件：台中在地 OR 100% 遠端｜非博弈｜非外勤業務
>         > 本日符合條件職缺數：X 筆
>         > 值得行動（Invest + Consider）：X 筆
>         >
>         > ---
>         >
>         > ## 🟢 Invest（積極投遞）
>         > [listings]
>         >
>         > ## 🟡 Consider（列入考慮）
>         > [listings]
>         >
>         > ## 🔴 Skip（略過）
>         > [quick table with reason]
>         >
>         > ---
>         >
>         > ## 📌 本週待辦追蹤
>         > [running table of all open applications]
>         >
>         > ## 💡 本日重點觀察
>         > [market trends, platform notes, search optimizations]
>         >
>         > 下一次日報排程：[next weekday date]
>         > ```
>         >
>         > **Language:** Traditional Chinese (繁體中文)
>         > **Output destination:** Append to Google Doc (one entry per day, newest at bottom)
>         >
>         > ---
>         >
>         > ## Known Search Quirks
>         >
>         > | Platform | Issue | Workaround |
>         > |----------|-------|------------|
>         > | LinkedIn | Binance dominates AI search results | Add `-Binance` to search keywords |
>         > | LinkedIn | Remote filter required | Always use `f_WT=2` |
>         > | Cake.me | Hyphenated slugs return no results | Use URL-encoded spaces: `/AI%20engineer%20remote` |
>         > | 104.com.tw | Defaults to Taipei | Use `area=6014010000` for Taichung |
>         > | 104.com.tw | Job detail URLs sometimes 404 | Search by company name instead |
>         > | Yourator | Low AI/LLM remote inventory | Lower search priority; try multiple keyword sets |
>         >
>         > ---
>         >
>         > *Last updated: 2026-06-26*
