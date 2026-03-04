# /legal-review — Legal Review Routing

## Purpose

Routes any matter to GC for formal legal review. Produces a Legal Review Memo. This command can be invoked standalone or is triggered automatically by `/start-initiative` when legal triggers are detected.

## Usage

```
/legal-review [INI-YYYY-### | contract file | description of matter]
```

---

## Intake Process

1. Identify the matter type (contract, regulatory, employment, IP, litigation, M&A, other)
2. Confirm: is this matter already on the GC's active docket?
3. If new: generate Legal Review Request with full context
4. Route to GC agent for review

---

## Legal Review Request Format

```
LEGAL REVIEW REQUEST
════════════════════════════════════════════════
Request ID: LRR-YYYY-###
Requesting Agent/Executive: [Role]
Initiative/Matter: [ID or description]
Date Submitted: [ISO date]
Urgency: [ROUTINE (5 days) | PRIORITY (48 hours) | URGENT (same day)]
════════════════════════════════════════════════

MATTER SUMMARY:
[2–3 paragraph description of the matter, transaction, or decision
requiring legal review]

LEGAL TRIGGERS IDENTIFIED:
[ ] Contract value >$250K
[ ] Cross-border transaction >$500K
[ ] Data processing change
[ ] Regulatory filing
[ ] Employment change >50 headcount
[ ] IP creation or licensing
[ ] M&A or partnership
[ ] Revenue recognition change
[ ] Litigation risk
[ ] Public statement
[ ] Other: ___________

DOCUMENTS FOR REVIEW:
[List of attached documents with version numbers]

BUSINESS TIMELINE:
[What is the business deadline driving this review?]

SPECIFIC LEGAL QUESTIONS:
1. [Specific question you need GC to answer]
2. [Additional questions if applicable]

CONTACT:
[Primary contact for follow-up questions]
════════════════════════════════════════════════
```

---

## GC Review SLAs

| Urgency | Response Target |
|---|---|
| ROUTINE | 5 business days |
| PRIORITY | 48 hours |
| URGENT | Same business day |
| EMERGENCY (active legal threat) | 2 hours |

---

## Possible GC Outcomes

- **LEGAL CLEARANCE GRANTED** — may proceed as planned
- **CONDITIONAL CLEARANCE** — may proceed after completing specified actions
- **LEGAL HOLD** — do not proceed; cannot be overridden by CEO; Board required to override

---

## Tracking

All legal review requests are logged in the Legal Review Register with:
- Request ID, date, matter, requestor
- GC assigned reviewer
- Status (pending, in-review, complete, on hold)
- Outcome and date closed

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
