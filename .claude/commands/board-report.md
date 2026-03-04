# /board-report — Board Report Generator

## Purpose

Generates a complete Board of Directors report package from current initiative statuses, financial data, and risk register. Produces a structured deck-ready document suitable for Board consumption.

## Usage

```
/board-report [Q1|Q2|Q3|Q4] [YEAR]
```

---

## Report Package Structure

### Section 1: CEO Letter
- Opening from CEO
- Quarter narrative (what happened, what it means)
- Forward-looking statement
- Key decisions requested from Board this session

### Section 2: Financial Performance
*CFO agent produces this section*
- P&L vs. plan (revenue, gross margin, EBITDA, EPS if public)
- Cash and liquidity position
- Balance sheet highlights
- Full-year forecast vs. original plan
- Key variances explained (>10% variance requires explanation)

### Section 3: Strategic Initiative Status
*COO and Chief of Staff produce this section*
For each active initiative:
- Initiative ID and name
- Status: GREEN / YELLOW / RED
- Budget consumed vs. authorized
- Milestone status
- Key risks and blockers

### Section 4: Risk Register Summary
*Risk owner produces this section*
- All HIGH and CRITICAL open risks
- New risks identified since last Board meeting
- Risks closed since last Board meeting
- Enterprise risk heat map

### Section 5: Operational Metrics
*COO produces this section*
- Key operational KPIs vs. targets
- Customer metrics (revenue, retention, NPS if applicable)
- People metrics (headcount, attrition, engagement)
- Quality/efficiency metrics

### Section 6: Legal and Compliance Update
*GC produces this section*
- Active litigation summary (matters and financial exposure)
- Regulatory inquiry status
- Compliance calendar items (upcoming filings)
- Material legal developments since last meeting

### Section 7: Human Capital
*CHRO produces this section*
- Headcount vs. plan
- Key hires and departures (exec level)
- Engagement score trends
- Succession plan status for critical roles

### Section 8: Items Requiring Board Action
- Resolutions to be voted on (list with recommendation)
- Informational items requiring acknowledgment
- Executive session topics

---

## Generation Workflow

1. Chief of Staff sends data request to all contributing executives
2. Each executive submits their section within 72 hours of request
3. CFO validates all financial figures
4. GC reviews for legal/disclosure concerns before distribution
5. CEO reviews and approves complete package
6. Chief of Staff formats and distributes to Board 5 business days before meeting

---

## Distribution Standards

- Board package distributed 5 business days before meeting
- Marked CONFIDENTIAL — BOARD ONLY
- Distributed via secure board portal (not email)
- Previous meeting minutes included for approval

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
