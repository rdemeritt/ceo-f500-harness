# Agent Output Guide — Fortune 500 AI Business Operating System

## Standard Output Format

Every significant agent output must follow this structure:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
AGENT:           [Role — e.g., "CFO"]
INITIATIVE:      [INI-YYYY-### | Matter Description]
OUTPUT TYPE:     [Brief | Decision | Finding | Recommendation | Approval | Hold]
DATE:            [ISO 8601 date]
AUTHORITY LEVEL: [This agent's relevant authority for this action]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

SUMMARY:
[2–3 sentence executive summary. Lead with the decision or conclusion.
Do not bury the headline.]

DETAIL:
[Full analysis, findings, or work product]

RISKS IDENTIFIED:
[Numbered list with severity. If none: "No material risks identified."]

RECOMMENDED ACTION:
[Clear, specific directive — what should happen next]

AUTHORITY REQUIRED FOR NEXT STEP:
[Who must act next — and what they must do]

EXIT STATE:
[The agent's specific exit signal phrase from AGENTS.md]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Output Type Definitions

| Type | When to Use |
|---|---|
| **Brief** | Initiative briefs, situation summaries, background documents |
| **Decision** | When the agent is making a definitive choice within their authority |
| **Finding** | IA, GC, or CTO findings of an issue, risk, or gap |
| **Recommendation** | When advising a higher authority — not deciding, recommending |
| **Approval** | Formal approval within the agent's authority |
| **Hold** | GC Legal Hold, IA Stop-the-Line, or other blocking action |

---

## Stop-the-Line Output Format

When any agent invokes stop-the-line authority:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚠  STOP-THE-LINE ⚠
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
INVOKED BY:      [Agent Role]
INITIATIVE:      [INI-YYYY-###]
DATE/TIME:       [ISO 8601]
SEVERITY:        [HIGH | CRITICAL]

REASON FOR HALT:
[Specific, factual description of the concern]

WHAT CANNOT PROCEED:
[Exactly what work is suspended]

REQUIRED TO RESUME:
[Specific conditions that must be met before work can resume]

ESCALATION:
[Who has been notified and who must resolve this]

This stop-the-line CANNOT be overridden by [role]. It requires [role] to resolve.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Financial Precision Standards

All financial figures in agent outputs must include:
- Exact dollar amount (not "approximately" or "around")
- Currency (USD unless specified)
- Time period (quarter, fiscal year, annualized)
- Source of the figure (budget, actual, estimate, forecast)

**Wrong:** "Revenue was roughly $50 million"
**Right:** "Revenue was $52.3M for Q1 FY2026 (actual, source: CFO financial close report)"

---

## Citation Standards

When citing regulations, cite precisely:
- **Wrong:** "per SOX rules"
- **Right:** "per SOX Section 302(a)(2), which requires CEO certification of financial statement accuracy"

When citing internal documents:
- **Wrong:** "per our policies"
- **Right:** "per Decision Authority Matrix, CLAUDE.md Section 1: Financial Authority Thresholds"

---

## Confidentiality Classification

Apply to every output:

| Classification | Use When |
|---|---|
| PUBLIC | May be shared externally (after GC review) |
| INTERNAL | Employees only |
| CONFIDENTIAL | Need-to-know basis; specific audience |
| RESTRICTED — BOARD ONLY | Board materials and resolutions |
| PRIVILEGED — ATTORNEY-CLIENT | GC legal opinions and crisis communications |

Default for any executive output with no explicit classification: **CONFIDENTIAL**

---

*Guide Version: 1.0.0 | Fortune 500 AI Business Operating System*
