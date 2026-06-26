# ai-agent-playbooks

> LLM-powered agent workflows built with Claude — for real-world automation tasks
>
> This repo documents two production-style AI agent workflows designed and operated using Claude. Each agent takes a structured prompt instruction as its "brain" and executes multi-step, multi-source tasks autonomously.
>
> ---
>
> ## Workflows
>
> ### 1. [Job Search Agent](./job-search-agent/)
>
> A daily job screening agent that:
> - Searches 4 platforms (LinkedIn, Cake.me, 104.com.tw, Yourator) for new listings
> - - Applies multi-criteria filtering (location: Taichung or 100% remote; excludes gambling industry, field sales)
>   - - Scores each listing (1–10) against a candidate profile across 8 evaluation dimensions
>     - - Appends a structured daily report to Google Docs
>      
>       - **Demonstrates:** Multi-source data aggregation, structured scoring logic, edge case handling, natural language output formatting
>      
>       - ---
>
> ### 2. [Value Investing Agent](./value-investing-agent/)
>
> A financial data pipeline that:
> - Collects 9 financial metrics per stock across 8+ websites (Dividend.com, Statementdog, Morningstar, Yahoo Finance, Valueinvesting.io, Jitta)
> - - Handles site-specific quirks (Cloudflare blocks, daily view limits, ticker format variations)
>   - - Outputs a paste-ready table for a Google Sheets value investing tracker
>     - - Covers 19 tickers including stocks and bond ETFs with per-asset exception handling
>      
>       - **Demonstrates:** Multi-step sequential task execution, site-specific navigation logic, data normalization, structured tabular output
>      
>       - ---
>
> ## How These Work
>
> Both agents run via Claude with a detailed markdown instruction file as the system prompt. Claude executes each step — navigating websites, extracting data, applying logic, and formatting output — without custom code or API integrations.
>
> **Execution environment:** Claude Chrome Extension (browser-based agent)
> **Output targets:** Google Docs (job reports), Google Sheets (investment data)
>
> ---
>
> ## Structure
>
> ```
> ai-agent-playbooks/
> ├── README.md
> ├── job-search-agent/
> │   ├── instructions.md      # Full agent specification / task prompt
> │   └── sample-output.md     # Example daily report output
> └── value-investing-agent/
>     ├── instructions.md      # Full agent specification / task prompt
>     └── sample-output.md     # Example data table output
> ```
>
> ---
>
> ## Skills Demonstrated
>
> - Prompt engineering for multi-step agentic tasks
> - - Task decomposition and sequential execution design
>   - - Edge case specification (missing data, site limits, ticker format variants)
>     - - Output schema design for structured reports and tables
>       - - Real-world automation without traditional code
>        
>         - ---
>
> *Built by [@joy21fs](https://github.com/joy21fs) · 2026*
