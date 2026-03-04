# /m-and-a-diligence — M&A Due Diligence Workflow

## Purpose

Manages the structured due diligence process for acquisitions, mergers, or major investments. Coordinates all executive functions across the full diligence lifecycle.

## Usage

```
/m-and-a-diligence [target company name] [deal type: acquisition|merger|investment|partnership]
```

**Board pre-approval required before this command initiates diligence.**

---

## Phase 0: Board Authorization
- Board resolution confirming authorization to pursue this target
- NDAs executed (GC manages)
- External advisors engaged: investment bank + M&A counsel (GC selects)
- Data room access established
- Diligence team assembled

---

## Diligence Workstream Structure

### Workstream 1: Financial Due Diligence
*CFO leads + external financial advisor*
- Historical P&L (3 years minimum)
- Quality of earnings analysis
- Revenue recognition review
- Working capital analysis
- Debt, contingent liabilities, off-balance-sheet items
- Tax structure and exposures
- Financial projections and model review
- Integration synergy validation

### Workstream 2: Legal Due Diligence
*GC leads + external M&A counsel*
- Corporate structure and ownership
- Material contracts (customers, vendors, employees)
- IP ownership and freedom to operate
- Litigation and regulatory history
- Employment law compliance
- Environmental liabilities
- Regulatory approvals required for close

### Workstream 3: Commercial Due Diligence
*CRO + CMO lead*
- Customer base quality and concentration risk
- Revenue retention and churn history
- Market position and competitive dynamics
- Customer references (if permitted)
- Sales pipeline quality
- Pricing power assessment

### Workstream 4: Technology Due Diligence
*CTO leads*
- Technology architecture and scalability
- Technical debt assessment
- IP ownership and third-party dependencies
- Security posture and vulnerability history
- System integration complexity
- Cloud infrastructure and costs

### Workstream 5: HR Due Diligence
*CHRO leads*
- Key talent identification and retention risk
- Compensation and benefits comparison
- Culture assessment
- Employment agreements and non-competes
- HR compliance and litigation history
- Headcount synergy analysis

### Workstream 6: Operational Due Diligence
*COO leads*
- Operations model and efficiency
- Supply chain and vendor dependencies
- Integration complexity and cost
- Day-1 operational readiness requirements
- 100-day plan feasibility

---

## Decision Gates

| Gate | Trigger | Decision Maker |
|---|---|---|
| IOI (Indication of Interest) | After Workstream 1+2 initial reads | CEO + CFO |
| LOI (Letter of Intent) | After all workstreams initial complete | CEO + CFO + Board |
| Final Bid | After full diligence complete | CEO + CFO + Board |
| Board Approval | Before signing | Board resolution |
| Regulatory Clearance | Before close | GC manages |

---

## Diligence Risk Register

Track deal-specific risks:

| Risk | Category | Severity | Mitigation |
|---|---|---|---|
| Revenue concentration (top customer >20%) | Financial | HIGH | Price adjustment or reps/warranties |
| IP ownership dispute | Legal | HIGH | Escrow or deal structure |
| Technology debt >$X | Technology | MEDIUM | Price adjustment or integration budget |
| Key person dependency | HR | HIGH | Retention package |

---

## MNPI Protocol

**GC enforces from first contact through public announcement.**
- Diligence team members on restricted list immediately
- No trading in target or acquirer stock during diligence
- All communications marked CONFIDENTIAL — M&A RESTRICTED
- Wall crossed advisors documented

---

## Hard Constraints

- **NEVER** initiate formal diligence without Board pre-approval
- **NEVER** sign NDAs without GC review
- **NEVER** share company MNPI with target without GC clearance
- **NEVER** make final bid without Board resolution
- **NEVER** proceed to close without all regulatory approvals (GC confirms)

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
