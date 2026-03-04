# Setup Guide — Fortune 500 AI Business Operating System

## Overview

This system transforms Claude Code into a Fortune 500 executive AI team. Before using the system, complete this 4-step setup to configure it for your specific company.

---

## Step 1: Configure Company Identity (5 minutes)

Open `CLAUDE.md` and replace ALL placeholders in the Integration Configuration section:

```
PROJECT_NAME=        → Your company's legal name
INDUSTRY=            → Your primary industry (e.g., "Enterprise SaaS", "Healthcare", "Financial Services")
FISCAL_YEAR_END=     → e.g., "December 31" or "March 31"
HEADQUARTERS=        → e.g., "San Francisco, CA, USA"
PUBLIC_OR_PRIVATE=   → PUBLIC or PRIVATE
STOCK_TICKER=        → e.g., "ACME" (or delete this line if private)
BOARD_SIZE=          → Number of board members
ANNUAL_REVENUE_RANGE=→ e.g., "$500M–$1B"
EMPLOYEE_COUNT_RANGE=→ e.g., "2,000–5,000"
PRIMARY_REGULATOR=   → e.g., "SEC", "FDA", "OCC", "FTC"
ERP_SYSTEM=          → SAP, Oracle, NetSuite, or other
CRM_SYSTEM=          → Salesforce, HubSpot, or other
GRC_PLATFORM=        → Archer, ServiceNow, or other
LEGAL_COUNSEL_FIRM=  → Your primary outside counsel firm
AUDITOR=             → Your external audit firm
```

---

## Step 2: Configure Industry-Specific Regulations (15 minutes)

Open `.claude/skills/regulatory-compliance/README.md` and add your industry-specific regulatory frameworks to the "Industry-Specific" table.

Examples by industry:
- **Financial Services:** FINRA, OCC, Fed, FDIC, Basel III, Dodd-Frank
- **Healthcare:** HIPAA, FDA, CMS, Joint Commission
- **Energy:** FERC, NERC, EPA, DOE
- **Defense:** ITAR, CMMC, DFARS
- **Education:** FERPA, COPPA, Title IV

---

## Step 3: Calibrate the Decision Authority Matrix (10 minutes)

Open `CLAUDE.md` and adjust the DAM thresholds to match your company's actual approval levels. The defaults are typical Fortune 500 thresholds — adjust for your size and risk appetite:

```
< $50,000   → BU Head             (adjust if your org is smaller/larger)
$50K–$1M    → COO + CFO           (adjust to your actual policies)
$1M–$10M    → CEO + CFO + GC      (adjust to your actual policies)
≥ $10M      → Board               (adjust to your actual policies)
```

Also adjust the automatic legal triggers in `CLAUDE.md` to match your GC's actual review thresholds.

---

## Step 4: Populate Agent Context (30 minutes)

For each agent in `.claude/agents/`, add company-specific context:

**In each agent file, add a "Company Context" section with:**
- Current OKRs (company and function level)
- Current approved budget
- Active initiatives this quarter
- Key stakeholders and their names
- Current risk posture (HIGH-level known risks)
- Recent Board/CEO priorities

This context helps each agent operate with awareness of your actual business state.

---

## Verification Checklist

Before first use:

- [ ] All CLAUDE.md placeholders replaced
- [ ] Industry regulations configured
- [ ] DAM thresholds calibrated to company policy
- [ ] At least CEO, CFO, and GC agents have company context
- [ ] Hooks config is reviewed and appropriate
- [ ] Templates reviewed by GC for any legal language gaps

---

## Quick Start Test

After setup, test the system with:

```
/start-initiative "Test initiative — improve Q1 customer retention by 10%"
```

Verify:
1. Chief of Staff creates an initiative brief
2. OKR alignment check runs
3. Governance threshold assessment fires
4. Correct approval chain is constructed
5. Brief is routed to CFO and GC (should trigger for any budget estimate)

---

## Known Limitations

1. **No live system integrations** — Agents reference ERP, CRM, and GRC systems but cannot connect to them without MCP tools or API integrations configured separately
2. **Financial data is not live** — Agents require financial data to be provided in context; they cannot pull from live financial systems without integration
3. **HITL required for real decisions** — This system provides decision support and governance structure; actual binding decisions require human executive review and approval

---

## Support

This system is built on the Safe Agentic Workflow architecture (Bybren LLC, 2026).
Architecture reference: https://github.com/bybren-llc/safe-agentic-workflow

---

*Setup Guide Version: 1.0.0 | Fortune 500 AI Business Operating System*
