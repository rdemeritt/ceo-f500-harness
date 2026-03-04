# /regulatory-check — Regulatory Compliance Screen

## Purpose

Screens any initiative or business action against the applicable regulatory frameworks. Identifies mandatory filings, compliance obligations, and automatic GC routing requirements.

## Usage

```
/regulatory-check [INI-YYYY-### | description of action]
```

---

## Regulatory Framework Screening Matrix

### Federal (US) — Always Applicable

| Regulation | Trigger | Action Required |
|---|---|---|
| SOX Section 302/906 | Any change to financial controls or processes | CFO + GC review; Audit Committee notification |
| SOX Section 404 | Annual internal control assessment | CFO + IA + external auditor |
| SEC Rule 10b-5 | Material non-public information handling | GC immediate stop; MNPI protocol |
| SEC Regulation FD | Material disclosure to select investors | GC review; may require public disclosure |
| SEC Form 8-K | Material corporate events | GC + CFO; file within 4 business days |
| FCPA | Any international business dealings | GC + compliance review |
| WARN Act | Mass layoffs ≥50 employees in 30 days | GC + CHRO; 60-day notice required |
| OSHA | Workplace safety incidents | CHRO + GC; report within 8 hours (severe) |
| FTC | Marketing claims, competitive practices | GC + CMO |
| DOL | Wage and hour, benefits changes | CHRO + GC |

### Data Privacy

| Regulation | Trigger | Action Required |
|---|---|---|
| GDPR | Any processing of EU resident data | GC + CTO; DPA required for new processing |
| CCPA/CPRA | Any processing of California resident data | GC + CTO; annual disclosure review |
| HIPAA | Any healthcare information | GC + CTO; Business Associate Agreement required |
| COPPA | Any data involving children <13 | GC + CTO + CMO; parental consent required |

### Industry-Specific (configure per company)

| Regulation | Industry | Action Required |
|---|---|---|
| [REGULATION_1] | [INDUSTRY_1] | [REQUIREMENT] |
| [REGULATION_2] | [INDUSTRY_2] | [REQUIREMENT] |

---

## Screening Output

```
REGULATORY COMPLIANCE SCREEN
════════════════════════════════════════════════
Initiative/Matter: [ID or description]
Screened: [ISO date]
Company Type: [PUBLIC | PRIVATE]
Jurisdictions: [US | EU | OTHER]
════════════════════════════════════════════════

TRIGGERED REGULATIONS:
  [List each triggered regulation]
  Trigger reason: [What in this initiative triggers it]
  Required action: [Specific compliance step]
  Deadline: [Filing or notice deadline if applicable]
  Owner: [GC | CFO | CHRO | CTO]

NOT TRIGGERED:
  [Key regulations screened but not triggered]

MANDATORY GC ROUTING: [YES | NO]
  [List specific regulations requiring GC review]

MANDATORY FILINGS:
  [List any required regulatory filings with deadlines]

RECOMMENDED ACTIONS:
  1. [First action with owner and deadline]
  2. [Second action with owner and deadline]

OVERALL COMPLIANCE STATUS: [CLEAR | ACTION REQUIRED | IMMEDIATE ESCALATION]
════════════════════════════════════════════════
```

---

## Escalation Rules

| Situation | Action |
|---|---|
| SEC material event | GC + CFO immediately; 8-K filing within 4 days |
| MNPI identified | GC stop-the-line; trading windows + disclosure review |
| Data breach | CTO + GC; breach notification per regulation (72 hours GDPR) |
| FCPA potential violation | GC + outside criminal counsel immediately |
| OSHA severe injury | CHRO + GC; report within 8 hours |
| Antitrust concern | GC + outside antitrust counsel immediately |

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
