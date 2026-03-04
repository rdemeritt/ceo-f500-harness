# /research — Web Research Workflow

## Purpose

Initiates a governed web research request through the Apify MCP integration. Routes the request to the appropriate lead agent, selects the correct actors, executes the research, and returns a structured brief with sources, confidence ratings, and governance flags.

## Usage

```
/research [topic or question]
```

**Examples:**
```
/research competitive positioning of Salesforce vs HubSpot in mid-market CRM
/research recent SEC enforcement actions in our industry
/research what analysts are saying about our sector heading into Q2
/research threat landscape for critical infrastructure — water sector
/research executive leadership changes at [Company Name] last 6 months
/research GDPR enforcement trend in EU — Q1 2026
```

---

## Workflow

### Step 1: Request Classification

Classify the research request into one of the following types:

| Type | Trigger Keywords | Lead Agent | Primary Actors |
|---|---|---|---|
| **Competitive** | competitor, vs., market share, win/loss, pricing, positioning | CRO or CMO | Google Search → Website Crawler → LinkedIn |
| **Market / Industry** | market, industry, trend, sector, consumer, forecast | CMO or Chief of Staff | RAG Browser → News Scraper |
| **Regulatory** | regulation, rule, enforcement, compliance, guidance, agency | GC | Google Search → Cheerio Scraper |
| **Threat Intelligence** | vulnerability, CVE, breach, threat actor, attack, exploit | CISO | Google Search → RAG Browser |
| **Investor / Analyst** | analyst, consensus, target price, rating, earnings, peer | IR | EDGAR Scraper → RAG Browser → Google Search |
| **Company / M&A** | company profile, acquisition target, diligence, leadership | Chief of Staff or CRO | Website Crawler → LinkedIn → EDGAR Scraper |
| **News Monitoring** | news, press, media, coverage, announcement, statement | Corp Comms or Chief of Staff | News Scraper → Google Search |
| **Technology** | vendor, platform, open source, technology, tool, architecture | CTO | Google Search → Website Crawler |

If the request spans multiple types, designate a primary lead agent and flag secondary agents for review.

### Step 2: Authorization Check

Before executing:
- Confirm the requesting agent is authorized to initiate this research type (see web-research skill)
- If the request involves personal data (individual names, profiles), flag for GC + CISO before proceeding
- If the request could surface MNPI, halt and route to GC immediately

### Step 3: Actor Selection and Execution

Lead agent selects actors from the pinned catalog in `.claude/skills/web-research/README.md`. Execution sequence:

```
1. Primary actor runs → raw data collected
2. If depth needed: secondary actor runs → additional context
3. Lead agent synthesizes findings
4. Governance flags assessed
5. Output formatted per Research Brief template
```

**Hard limit:** No more than 3 actors per research request without explicit approval from the lead agent's reporting executive. Prevents runaway cost from poorly scoped queries.

### Step 4: Research Brief Production

Lead agent produces the Research Brief using the standard template:

```
RESEARCH BRIEF
════════════════════════════════════════════════════
Topic:          [Research subject, verbatim from request]
Requested by:   [Agent / user / Initiative ID]
Lead agent:     [Role that synthesized]
Actors used:    [Exact actor IDs invoked]
Date:           [ISO date]
Classification: [INTERNAL | CONFIDENTIAL | RESTRICTED]
════════════════════════════════════════════════════

SUMMARY:
[3–5 sentence synthesis. Lead with the most actionable finding.]

FINDINGS:
[Structured findings. Each claim cited to a source number.]

SOURCE LOG:
  [1] [Full URL] — Published: [date] — Scraped: [date] — Confidence: HIGH/MEDIUM/LOW
  [2] ...

DATA GAPS:
[What could not be found. Flag if gaps are material to the decision.]

GOVERNANCE FLAGS:
[ ] MNPI risk — route to GC + IR before any distribution
[ ] PII collected — route to GC + CISO before retention or use
[ ] Competitive sensitivity — mark CONFIDENTIAL, limit distribution
[ ] Regulatory relevance — route to GC for interpretation
[ ] Requires primary source verification before acting on findings

RECOMMENDED ACTION:
[What should happen with this research — route to whom, for what purpose]

EXIT STATE:
[Lead agent's standard exit signal]
════════════════════════════════════════════════════
```

### Step 5: Distribution Routing

Based on research type and content:

| Research Type | Default Distribution |
|---|---|
| Competitive | CRO + CMO, flag to CEO if material |
| Regulatory | GC review first, then to relevant BU |
| Threat Intelligence | CISO → CTO → CEO if HIGH/CRITICAL |
| Investor / Analyst | IR → CFO → CEO |
| M&A / Company | Chief of Staff → CEO, flag to GC if diligence trigger |
| News Monitoring | Corp Comms → CMO → CEO if crisis-adjacent |

---

## Governance Hard Stops

**HALT immediately and route to GC if:**
- Research reveals potential MNPI about the company or a material counterparty
- Personal data about individuals is collected beyond names and titles
- Any finding constitutes material non-public information under Reg FD
- Research involves accessing or attempting to access non-public systems

**HALT and route to CISO if:**
- Threat intelligence reveals an active, unmitigated vulnerability in company systems
- Research uncovers evidence of an active breach or threat actor targeting the company

**HALT and invoke Stop-the-Line if:**
- The research request itself appears designed to access information through improper means
- An actor returns data that could only have come from a non-public source

---

## Cost Controls

```
Before executing any research run:
  Estimate cost using actor catalog in web-research skill
  If estimated cost < $1:   Self-authorize
  If estimated cost $1–$10: Log in research register, lead agent approves
  If estimated cost > $10:  Reporting executive approval before running
  If estimated cost > $100: CFO notification; route to /budget-request
```

---

## Related Commands

- `/ideate` — use research findings as creative fuel for campaign concepts
- `/risk-assessment` — convert threat intelligence findings into scored risk items
- `/regulatory-check` — route regulatory research findings through compliance screen
- `/m-and-a-diligence` — advance company research into M&A diligence workflow
- `/crisis-response` — activate if news monitoring surfaces a crisis signal

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
