# /risk-assessment — Enterprise Risk Assessment

## Purpose

Produces a standardized risk assessment and score for any initiative, decision, or emerging risk. Risk scoring drives governance routing per the Decision Authority Matrix.

## Usage

```
/risk-assessment [INI-YYYY-### | description of risk/decision]
```

---

## Risk Scoring Methodology

### Likelihood Score (1–5)
| Score | Definition |
|---|---|
| 1 | Rare — unlikely to occur (< 10% probability) |
| 2 | Unlikely — possible but not expected (10–25%) |
| 3 | Possible — could occur under certain conditions (25–50%) |
| 4 | Likely — will probably occur (50–75%) |
| 5 | Almost Certain — expected to occur (>75%) |

### Impact Score (1–5)
| Score | Definition |
|---|---|
| 1 | Negligible — no material business impact |
| 2 | Minor — limited financial, operational, or reputational impact |
| 3 | Moderate — significant but manageable impact |
| 4 | Major — material financial loss, significant reputational damage, or regulatory penalty |
| 5 | Catastrophic — existential threat, criminal liability, or company-ending consequence |

### Risk Score = Likelihood × Impact

| Score | Level | Governance Action |
|---|---|---|
| 1–3 | LOW | BU Head manages; log in risk register |
| 4–6 | MEDIUM | COO notified within 24 hours; mitigation plan required |
| 7–8 | HIGH | CEO stop-the-line; initiative paused pending CEO decision |
| 9–10 | CRITICAL | Board emergency session within 48 hours |

---

## Risk Assessment Template Output

```
ENTERPRISE RISK ASSESSMENT
════════════════════════════════════════════════
Initiative/Matter: [ID or description]
Assessed by: Risk Assessment System
Date: [ISO date]
════════════════════════════════════════════════

RISK INVENTORY:

Risk 1: [Risk name]
  Category:    [Financial | Legal | Operational | Reputational | Strategic | Regulatory | Cyber]
  Description: [What could go wrong and how]
  Likelihood:  [1–5] — [Rationale]
  Impact:      [1–5] — [Rationale]
  Score:       [1–25] → [LOW | MEDIUM | HIGH | CRITICAL]
  Mitigations: [Specific mitigation actions]
  Owner:       [Role responsible]
  Residual score after mitigation: [1–25]

[Repeat for each identified risk]

────────────────────────────────────────────────
AGGREGATE RISK PROFILE:
  Highest risk score:     [score] — [level]
  Number of HIGH risks:   [n]
  Number of CRITICAL:     [n]

GOVERNANCE ACTION REQUIRED:
  [LOW: Proceed — log in register]
  [MEDIUM: COO notification — proceed with mitigation plan]
  [HIGH: STOP — CEO must review before proceeding]
  [CRITICAL: STOP — Board emergency session required]

RECOMMENDED MITIGATION INVESTMENTS:
[Any specific investments, insurance, or controls recommended]
════════════════════════════════════════════════
```

---

## Risk Categories Reference

| Category | Examples |
|---|---|
| Financial | Budget overrun, cash flow, credit, FX, commodity |
| Legal | Contract, litigation, IP, employment, FCPA |
| Regulatory | SOX, GDPR, SEC, industry-specific compliance |
| Operational | Process failure, vendor, supply chain, talent |
| Reputational | Media, social, ESG, customer trust |
| Strategic | Competitive, market, M&A execution, technology disruption |
| Cyber | Data breach, ransomware, system outage, fraud |

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
