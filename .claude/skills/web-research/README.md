# Skill: Web Research (Apify)

## Purpose

Provides governed web research capability to authorized agents via the Apify MCP server. Agents use this skill to gather external intelligence — competitive data, regulatory updates, market information, news, company profiles, and SEC filings — without leaving the harness or operating outside their authority.

## Prerequisites

- Apify MCP server configured (see `SETUP.md` Step 5)
- `APIFY_TOKEN` set in environment
- Research request routed through an authorized agent (see Agent Access below)

---

## Agent Access

Not all agents are authorized to initiate web research. Research has cost implications and can surface sensitive competitive or regulatory information that requires appropriate handling.

| Agent | Research Access | Scope |
|---|---|---|
| Chief of Staff | Full | Initiative background, company research, general intelligence |
| CEO | Full | Strategic intelligence, market context, leadership research |
| CMO | Full | Market research, brand monitoring, competitor campaigns, consumer trends |
| CRO | Full | Competitive intelligence, prospect research, market sizing, win/loss data |
| CISO | Full | Threat intelligence, CVE/vulnerability monitoring, dark web exposure |
| IR | Full | Analyst coverage, peer company monitoring, consensus tracking, SEC filings |
| GC | Full | Regulatory monitoring, case law context, legislative tracking |
| CTO | Full | Technology landscape, vendor research, open-source ecosystem |
| CFO | Read results only | Cannot initiate research; receives financial intelligence summaries |
| CHRO | Limited | Public compensation benchmarks, employer brand, labor market data |
| Internal Audit | None | Read-only to internal systems; must request via Chief of Staff |
| Board | None | Receives synthesized briefings only; does not initiate research |

---

## Actor Catalog

### Pinned Actors (Available in This Harness)

| Actor | ID | Best For | Approx. Cost |
|---|---|---|---|
| RAG Web Browser | `apify/rag-web-browser` | General web search + page summarization for LLM ingestion | ~$0.01/query |
| Google Search Scraper | `apify/google-search-scraper` | Structured SERP data, news search, competitive queries | $0.50/1,000 pages |
| Website Content Crawler | `apify/website-content-crawler` | Full site crawl for competitor, regulatory, or vendor analysis | ~$0.10–$1/site |
| Cheerio Scraper | `apify/cheerio-scraper` | Fast structured data extraction from static HTML sites | ~$0.05/run |
| LinkedIn Scraper | `get-leads/linkedin-scraper` | Company profiles, executive data, org structure, job postings | ~$0.10–$0.50/run |
| SEC EDGAR Scraper | `scraped/edgar-filing-data-scraper-sec-company-filings` | 10-K, 10-Q, 8-K, proxy filings for public companies | ~$0.05–$0.20/run |
| Advanced News Scraper | `dorcy/advanced-news-scraper` | News monitoring across 4,500+ sources | ~$0.10–$0.50/run |

**Dynamic actor discovery is disabled.** Agents may not search the Apify Store and invoke unlisted actors. If a use case requires an actor not in this list, route to CTO to evaluate and add to the pinned list.

---

## Research Type Routing

Match the research request to the correct actor(s):

### Competitive Intelligence
**Lead agent:** CRO or CMO
**Actors:** `apify/google-search-scraper` → `apify/website-content-crawler` → `get-leads/linkedin-scraper`
**Pattern:** Search for competitor, crawl their site and LinkedIn, synthesize profile using the competitive-intelligence skill template.

### Market and Industry Research
**Lead agent:** CMO or Chief of Staff
**Actors:** `apify/rag-web-browser` → `dorcy/advanced-news-scraper`
**Pattern:** RAG browser for narrative context, news scraper for recent developments.

### Regulatory Monitoring
**Lead agent:** GC
**Actors:** `apify/google-search-scraper` → `apify/cheerio-scraper`
**Pattern:** Search regulatory body sites (SEC.gov, FTC.gov, etc.), scrape new rule postings or guidance documents.
**Note:** Always cite primary source URL. Never treat scraped regulatory text as authoritative without GC verification against primary source.

### Threat Intelligence (CISO)
**Lead agent:** CISO
**Actors:** `apify/google-search-scraper` → `apify/rag-web-browser`
**Pattern:** Search for CVEs, vendor advisories, threat actor activity. Scope searches to security-specific sources (CISA, NVD, vendor advisory pages).
**Restriction:** Do not scrape dark web sources or access non-indexed content. All threat intelligence from public sources only.

### SEC Filings and Investor Research
**Lead agent:** IR or CFO
**Actors:** `scraped/edgar-filing-data-scraper-sec-company-filings` → `apify/rag-web-browser`
**Pattern:** Pull EDGAR filings for target company, use RAG browser for analyst commentary and news context.
**MNPI Warning:** SEC data is public record — but any analysis that combines public data with MNPI requires immediate GC notification. IR must apply Reg FD judgment to all output.

### Company and Executive Research (M&A / Diligence)
**Lead agent:** Chief of Staff or CRO
**Actors:** `apify/website-content-crawler` → `get-leads/linkedin-scraper` → `scraped/edgar-filing-data-scraper-sec-company-filings`
**Pattern:** Crawl company site, scrape LinkedIn for leadership profiles, pull SEC filings if public. Follow M&A diligence skill protocols.

### News Monitoring
**Lead agent:** Corp Comms or Chief of Staff
**Actors:** `dorcy/advanced-news-scraper` → `apify/google-search-scraper`
**Pattern:** News scraper for volume monitoring, Google Search for targeted queries. Flag any results that require Corp Comms or GC response.

---

## Output Standards for Research Results

All web research output must include:

1. **Source list** — Every factual claim linked to its source URL and retrieval date
2. **Data freshness** — Explicitly state when each source was published or scraped
3. **Confidence level** — HIGH (primary source), MEDIUM (reputable secondary), LOW (inferred or indirect)
4. **Completeness caveat** — "This research represents publicly available information as of [date] and may be incomplete"
5. **Legal boundary statement** — Confirm no restricted data sources were accessed

### Research Output Template

```
RESEARCH BRIEF
════════════════════════════════════════════════════
Topic:          [Research subject]
Requested by:   [Agent / Initiative ID]
Lead agent:     [Who synthesized]
Actors used:    [List of Apify actors invoked]
Date:           [ISO date]
════════════════════════════════════════════════════

SUMMARY:
[3–5 sentence synthesis of key findings]

FINDINGS:
[Structured findings with citations]

SOURCE LOG:
  [1] [URL] — [publication date] — Confidence: HIGH/MEDIUM/LOW
  [2] ...

DATA GAPS:
[What was not findable via public sources — flag for primary research if needed]

GOVERNANCE FLAGS:
[ ] MNPI risk — route to GC + IR before distribution
[ ] Competitive sensitivity — mark CONFIDENTIAL
[ ] Regulatory relevance — route to GC for review
[ ] Requires verification against primary source before action

RECOMMENDED NEXT STEP:
[What should happen with these findings]
════════════════════════════════════════════════════
```

---

## Cost Governance

Web research consumes Apify platform credits. Apply the following controls:

| Research Scope | Estimated Cost | Approval Required |
|---|---|---|
| Single query (RAG browser) | < $0.05 | Agent self-authorizes |
| Standard research brief (3–5 actors) | $0.10 – $1.00 | Agent self-authorizes |
| Deep competitive crawl (full site) | $1 – $10 | CMO or CRO approval |
| Bulk research (10+ companies) | $10 – $100 | CFO awareness required |
| Enterprise research program (recurring) | > $100/month | CFO budget line item |

**No agent may initiate a research run expected to exceed $10 without prior approval from their reporting executive.**

---

## Legal Boundaries (Always Active)

These constraints apply to all research regardless of agent or urgency:

- **Public sources only** — Only scrape publicly accessible, indexed web content. No access to paywalled content, non-public databases, or authenticated portals.
- **No misrepresentation** — Never impersonate a user, company, or identity to access information.
- **robots.txt compliance** — Apify actors are configured to respect robots.txt by default. Do not override.
- **Personal data handling** — Any research that surfaces personally identifiable information (PII) about individuals must be flagged to GC + CISO before retention or use. GDPR and CCPA apply.
- **No competitor system access** — Never attempt to access competitor systems, intranets, or any non-public infrastructure.
- **SEC/MNPI** — Any research touching material non-public information must stop immediately and route to GC.

Violations of these boundaries are a stop-the-line event.

---

_Skill Version: 1.0.0 | Fortune 500 AI Business Operating System_
