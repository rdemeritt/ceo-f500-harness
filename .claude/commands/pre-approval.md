# /pre-approval — Pre-Approval Validation Pipeline

## Purpose

Runs the full 7-gate pre-approval validation before routing any initiative or decision to executive approvers. This is the equivalent of `/pre-pr` in a software context — it ensures everything is in order before consuming executive time.

## Usage

```
/pre-approval [INI-YYYY-###]
```

**All 7 gates are mandatory blockers.** A RED result on any gate stops the pipeline.

---

## Gate 1: Financial Materiality Check

Verify:
- Budget figure is confirmed (not estimated range)
- Correct DAM authority level identified
- All required financial approvals are in the routing chain
- Prior-period budget baseline available for comparison

Output: PASS / FAIL (with specific gap if FAIL)

---

## Gate 2: Legal and Regulatory Screen

Verify:
- All automatic legal triggers have been checked (CLAUDE.md trigger list)
- GC clearance on file if any trigger matched
- No active legal holds affecting this domain
- Regulatory filing requirements identified and calendared

Output: PASS / FAIL

---

## Gate 3: Risk Assessment Validation

Verify:
- Risk assessment has been completed using the standard template
- Risk score assigned (1–10)
- Mitigation plans documented for all risks scored ≥4
- Risk register updated
- Risk score <7 (if 7+, CEO notification must be on file before proceeding)

Output: PASS / FAIL

---

## Gate 4: Conflict of Interest Declaration

Verify:
- All agents involved in the initiative have declared or disclaimed conflicts
- Any declared conflict has a documented recusal decision
- Recusal decisions are signed by the next authority level

Output: PASS / FAIL

---

## Gate 5: Board Threshold Check

Verify:
- If budget ≥$10M: Board resolution exists and is dated within 90 days
- If M&A related: Board pre-approval exists
- If none of these: confirm no Board threshold is triggered

Output: PASS / NOT APPLICABLE / FAIL

---

## Gate 6: ESG and Reputational Impact Screen

Assess:
- Does this initiative involve environmental impact that requires disclosure?
- Are there material social impacts (labor practices, community, customers)?
- Is there reputational exposure (media, social, regulatory)?
- Has Corp Comms been consulted if any external-facing element exists?

Output: PASS / REVIEW RECOMMENDED / FAIL (if disclosure required and not addressed)

---

## Gate 7: Documentation Readiness

Verify that the following are complete and filed:
- [ ] Initiative Brief (complete, signed by sponsor)
- [ ] Risk Assessment (complete)
- [ ] Budget Authorization (on file from CFO)
- [ ] Legal Clearance (on file from GC, if required)
- [ ] Approval Routing Chain (confirmed, in correct order)
- [ ] Executive Summary (1-page, ready for approvers)

Output: PASS / FAIL (list missing documents)

---

## Final Output

```
PRE-APPROVAL PIPELINE REPORT
════════════════════════════════════════════════
Initiative: [INI-YYYY-###] — [Title]
Run Date: [ISO date]
════════════════════════════════════════════════

Gate 1: Financial Materiality     [PASS | FAIL]
Gate 2: Legal/Regulatory Screen   [PASS | FAIL]
Gate 3: Risk Assessment           [PASS | FAIL]
Gate 4: Conflict of Interest      [PASS | FAIL]
Gate 5: Board Threshold           [PASS | N/A | FAIL]
Gate 6: ESG/Reputational          [PASS | REVIEW | FAIL]
Gate 7: Documentation             [PASS | FAIL]

OVERALL: [ALL GATES CLEAR — READY FOR APPROVAL ROUTING |
          BLOCKED — [N] GATE(S) FAILED — REMEDIATION REQUIRED]

FAILED GATES REMEDIATION:
[Specific action required for each failed gate]
════════════════════════════════════════════════
```

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
