# Job Search Agent — Task Instructions

> Agent specification for daily job screening across LinkedIn, Cake.me, 104.com.tw, and Yourator

---

## Candidate Profile

- **Role:** Frontend Engineer, 3+ years production experience
- **Core skills:** React, TypeScript, Next.js, Vite
- **AI/LLM experience:** Claude API, Vercel AI SDK, OpenAI API, prompt engineering, streaming chat UI
- **Side work:** LLM evaluation / AI data quality (DataAnnotation, freelance)
- **English:** TOEFL 103, TOEIC 975, Master's degree from Arizona State University, US work experience
- **GitHub:** github.com/joy21fs

---

## Location Constraints

- ✅ Taichung-based (any district)
- ✅ 100% Remote (Taiwan-eligible)
- ❌ Taipei-only office (non-remote)
- ❌ Requires relocation

---

## Work Style Preferences

- No overtime culture
- Independent work style
- English-language environment preferred (not required)

---

## Target Role Types

1. Frontend Engineer with AI/LLM focus
2. AI Application Engineer / Full Stack + AI integration
3. AI Automation Engineer (n8n, Make, Claude Code, MCP)
4. LLM Evaluator / AI Data Quality roles
5. Solutions Engineer / Technical Account Manager (low client contact frequency)
6. AI Quality Analyst / Bilingual AI Trainer

---

## Hard Filters — Always Skip

- ❌ Gambling / gambling-adjacent industry (crypto exchanges, offshore payments, etc.)
- ❌ Taipei-only office (non-remote)
- ❌ Partial remote / hybrid-only (100% remote required)
- ❌ Field sales (primarily external client visits)
- ❌ Pure marketing, pure admin with no technical component
- ❌ Technical Writer

---

## Search Platforms & Keywords

| Platform | Keywords | Filters |
|----------|----------|---------|
| LinkedIn | `frontend engineer AI LLM -Binance`, `AI automation engineer Taiwan`, `solutions engineer Taiwan remote` | Remote (f_WT=2), Past 24h (f_TPR=r86400) |
| Cake.me | `AI automation engineer remote`, `Frontend Engineer AI LLM remote`, `AI engineer LLM remote Taiwan` | Remote filter on |
| 104.com.tw | `AI LLM 工程師`, `前端工程師 AI`, `生成式 AI 工程師` | area=6014010000 (Taichung) OR ro=1 (remote) |
| Yourator | `AI LLM engineer remote`, `frontend AI remote` | remote=true |

---

## Evaluation Rubric (8 Dimensions)

For each qualifying job listing, evaluate:

1. **Job title & company name**
2. **Match score (1–10)** — honest rating, no inflation
3. **Strengths** — skills/experience that align
4. **Gaps** — missing skills or requirements I don't have
5. **Red flags** — overtime culture, vague title, unclear scope
6. **Salary** — stated range or "not disclosed"
7. **Remote/location** — Taichung / 100% remote / hybrid
8. **Verdict:** Invest 🟢 / Consider 🟡 / Skip 🔴 — one sentence reason

> "Be honest. Do not inflate match scores. If a role requires skills I don't have, say so clearly."

---

## Output Format

Output in **Traditional Chinese (繁體中文)**, structured as:

```
# 求職日報 — [Date]
搜尋平台 / 篩選條件 / 本日數量摘要

## 🟢 Invest（積極投遞）
## 🟡 Consider（列入考慮）
## 🔴 Skip（略過）— 快速列表
## 📌 本週待辦追蹤
## 💡 本日重點觀察
下一次日報排程：[Next weekday date]
```

---

## Output Destination

Append each daily report to this Google Doc:
https://docs.google.com/document/d/1869Kg6ki_oPdEJvRiw3JXy4tqZwbhQfMLjzBSyjwHbU/edit

One report per day, newest at the bottom.

---

## Known Platform Issues & Workarounds

| Platform | Issue | Workaround |
|----------|-------|------------|
| LinkedIn | Binance dominates AI search results | Add `-Binance` to all keywords |
| LinkedIn | Needs Remote filter | Always use `f_WT=2` in URL |
| Cake.me | Hyphenated slug returns empty results | Use URL-encoded spaces: `/AI%20engineer%20remote` |
| 104.com.tw | Defaults to Taipei | Use `area=6014010000` for Taichung |
| 104.com.tw | Job detail URL sometimes 404 | Search by company name instead |
| Yourator | Limited AI/LLM remote stock | Lower priority; try multiple keyword sets |
