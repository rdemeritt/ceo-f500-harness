# /budget-request — Budget Approval Workflow

## Purpose

Initiates the formal budget approval process for any initiative or unplanned spend. Routes through the correct authority chain per the Decision Authority Matrix.

## Usage

```
/budget-request [INI-YYYY-### | description] [amount] [capex|opex|both]
```

---

## Budget Request Form

```
BUDGET REQUEST
════════════════════════════════════════════════
Request ID: BRQ-YYYY-###
Requesting Executive: [Role]
Initiative: [INI-YYYY-### or description]
Date: [ISO date]
════════════════════════════════════════════════

FINANCIAL DETAILS:
  Request Type:          [Capex | Opex | Both]
  Total Amount:          $[amount]
  Capex Portion:         $[amount]
  Opex Portion:          $[amount] (annualized)
  Budget Period:         [Quarter/Year]
  Spend Timing:          [Monthly breakdown]

BUDGET STATUS:
  In annual budget:      [Yes / No / Partial]
  If No — Reason:        [Why unbudgeted?]
  If Partial — Gap:      $[unbudgeted amount]
  Offset source:         [What budget is reduced to fund this?]

BUSINESS CASE:
  Strategic initiative:  [INI-YYYY-### and OKR]
  Expected return:       [ROI, payback period, NPV if applicable]
  Revenue impact:        $[amount] [incremental | protected]
  Cost savings:          $[amount] [annualized]
  Risk if not funded:    [What happens if this is denied?]

ROI ANALYSIS:
  Year 1 return:         $[amount]
  Year 2 return:         $[amount]
  Year 3 return:         $[amount]
  Payback period:        [months]
  Net Present Value:     $[amount]
  Discount rate used:    [%]

VENDOR / CONTRACT:
  Vendor name:           [if applicable]
  Contract term:         [duration]
  Contract value:        $[total]
  GC review required:    [Yes if >$250K]

APPROVAL CHAIN (auto-populated per DAM):
  [ ] BU Head (< $50K)
  [ ] CFO (≥ $50K)
  [ ] COO co-sign ($50K–$1M)
  [ ] CEO co-sign (≥ $1M)
  [ ] Board resolution (≥ $10M)
════════════════════════════════════════════════
```

---

## CFO Evaluation Criteria

When CFO reviews this request:
1. **Strategic fit** — Is this funded to an approved OKR?
2. **ROI validity** — Are assumptions reasonable and documented?
3. **Cash impact** — What is the effect on liquidity and forecast?
4. **Authority** — Who must co-sign per DAM?
5. **Legal** — Is GC routing required?
6. **Offset** — Is there an offset or is this a net increase to budget?

---

## Possible Outcomes

- **APPROVED** — Budget authorized at requested amount
- **CONDITIONALLY APPROVED** — Approved at reduced amount or with conditions
- **DENIED** — Not approved; specific reason provided; re-submit path available
- **DEFERRED** — Held for next budget cycle

---

## Tracking

All budget requests logged in Budget Authorization Register with:
- BRQ-ID, amount, type, initiative, requestor
- Approval chain status
- Outcome, approver, date
- Associated financial commitment reference

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
