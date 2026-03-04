# /governance-check — Governance Health Check

## Purpose

Validates the governance status of an active initiative. Returns GREEN / YELLOW / RED status across all governance dimensions. Run before any major milestone or before escalating to the next approval stage.

## Usage

```
/governance-check [INI-YYYY-###]
```

## Validation Checks

### 1. Initiative Brief Completeness
- [ ] Initiative Brief exists with correct ID
- [ ] All required sections are populated
- [ ] Executive sponsor is confirmed
- [ ] OKR alignment is documented

### 2. Financial Authorization
- [ ] Budget estimate is on file
- [ ] CFO approval obtained (if ≥$50K)
- [ ] CEO co-sign obtained (if ≥$1M)
- [ ] Board resolution on file (if ≥$10M)
- [ ] No unbudgeted spend has occurred

### 3. Legal Clearance
- [ ] Legal trigger screening completed
- [ ] GC clearance document on file (if any trigger matched)
- [ ] No active legal holds on this initiative
- [ ] Applicable regulatory filings identified

### 4. Risk Assessment
- [ ] Risk assessment completed and scored
- [ ] Risk score ≤6 (if 7+, CEO notification on file)
- [ ] High/Critical risks have documented mitigation owners
- [ ] Risk register updated with initiative risks

### 5. Audit Trail Integrity
- [ ] All decision records are timestamped
- [ ] No gaps in approval sequence
- [ ] All required co-signatures obtained in correct order
- [ ] Conflict of interest declarations on file (or "none declared")

---

## Output Format

```
GOVERNANCE CHECK REPORT
════════════════════════════════════════════════
Initiative: [INI-YYYY-###] — [Title]
Date Checked: [ISO date]
Checked by: Governance System
════════════════════════════════════════════════

OVERALL STATUS: [GREEN | YELLOW | RED]

DIMENSION SCORES:
  Brief Completeness:    [GREEN | YELLOW | RED]
  Financial Auth:        [GREEN | YELLOW | RED]
  Legal Clearance:       [GREEN | YELLOW | RED]
  Risk Assessment:       [GREEN | YELLOW | RED]
  Audit Trail:           [GREEN | YELLOW | RED]

ISSUES REQUIRING ATTENTION:
[List each RED or YELLOW item with specific remediation required]

RECOMMENDED ACTION:
  GREEN:  Proceed to next stage
  YELLOW: Resolve noted items within 48 hours — proceed with caution
  RED:    DO NOT PROCEED — resolve all RED items before continuing
════════════════════════════════════════════════
```

## Status Definitions

| Status | Meaning |
|---|---|
| GREEN | All 5 validations pass — governance is clean |
| YELLOW | Minor gaps — proceed cautiously, resolve within 48 hours |
| RED | Critical blockers — initiative must pause until resolved |

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
