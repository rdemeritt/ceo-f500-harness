# /start-initiative — Initiative Launch Workflow

## Purpose

Kicks off the full enterprise initiative lifecycle. Validates strategic alignment, creates a structured initiative brief, and routes through the governance gate before any execution begins.

## Usage

```
/start-initiative [objective or initiative description]
```

## Workflow

### Step 1: Intake
- Capture the initiative objective, sponsor name, and time horizon
- If not provided, prompt: "What is the strategic objective? Who is the executive sponsor? What is the target completion timeframe?"

### Step 2: Strategic Alignment Check
- Map the initiative to current company OKRs
- If no OKR match: HALT. "This initiative does not align to current OKRs. Route to CEO for strategic priority confirmation before proceeding."
- If OKR match confirmed: continue

### Step 3: Initiative Brief Creation
Invoke Chief of Staff agent to draft the Initiative Brief using the standard template from `AGENTS.md`. Brief must include:
- Initiative ID (auto-generate: INI-YYYY-###)
- Strategic alignment (OKR mapping)
- Business case
- Resource requirements (budget estimate, headcount)
- Risk summary
- Governance requirements (thresholds that apply)

### Step 4: Governance Threshold Assessment
Automatically determine which approvals are required:

```
Budget estimate provided?
  If YES:
    <$50K        → BU Head approves → skip to Stage 2
    $50K-$999K   → CFO + COO route
    $1M-$9.99M   → CFO + COO + CEO route
    ≥$10M        → Board approval required

  If NO:
    → Flag as "Budget TBD — CFO review required"
    → Default to highest applicable route

Legal triggers present?
  Check list of automatic triggers in CLAUDE.md
  If ANY match → mandatory GC routing added to approval chain

Regulatory triggers?
  Run /regulatory-check automatically
  If flagged → add regulatory review to approval chain
```

### Step 5: Approval Chain Construction
Output the complete approval chain required before execution:
- List each required approver in sequence
- List any parallel approvals that can happen simultaneously
- Estimate minimum timeline based on chain length

### Step 6: Route and Confirm
- Route Initiative Brief to first required approver
- Record initiative in the active initiative register
- Confirm to user: 5-point launch confirmation

---

## 5-Point Launch Confirmation Output

```
INITIATIVE LAUNCH CONFIRMED
════════════════════════════════════════
✓ Initiative ID:     [INI-YYYY-###]
✓ Title:             [Initiative Name]
✓ OKR Alignment:     [OKR reference]
✓ Governance Route:  [List of required approvers]
✓ First Step:        [Routed to: role — action required]
════════════════════════════════════════
Status: PENDING GOVERNANCE APPROVAL
Next: [First approver] must review and respond
```

---

## Hard Gates (Stop-the-Line)

- **HALT if:** No OKR alignment AND no CEO confirmation of new strategic priority
- **HALT if:** Budget estimate exists AND no CFO routing for amounts >$50K
- **HALT if:** Any automatic legal trigger present AND GC not in approval chain
- **HALT if:** Any CRITICAL risk score — route to CEO immediately before proceeding

---

## Related Commands

- `/governance-check` — validate governance status of an active initiative
- `/budget-request` — formal budget approval workflow
- `/legal-review` — standalone legal review routing
- `/risk-assessment` — standalone risk scoring

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
