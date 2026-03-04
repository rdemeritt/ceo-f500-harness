# /earnings-prep — Earnings Preparation Workflow

## Purpose

Manages the full earnings preparation process for public companies: from financial close through earnings release, script preparation, and investor Q&A prep. Coordinates CFO, GC, CEO, and IR.

## Usage

```
/earnings-prep [Q1|Q2|Q3|Q4|FY] [YEAR]
```

*(For private companies: use /qbr instead)*

---

## Earnings Calendar (Auto-generated)

| Milestone | Target Date | Owner |
|---|---|---|
| Financial close | [T–30 days] | CFO |
| Draft press release | [T–21 days] | CFO + IR |
| GC legal review of release | [T–18 days] | GC |
| Audit/review complete | [T–15 days] | CFO + External Auditor |
| Board Audit Committee review | [T–12 days] | CFO + Audit Committee |
| CEO script draft | [T–10 days] | CEO + CFO + IR |
| Q&A preparation session | [T–7 days] | CEO + CFO + IR |
| Final press release approved | [T–5 days] | GC + CFO + CEO |
| Reg FD blackout begins | [T–5 days] | GC enforces |
| Earnings release | [Earnings Date] | CFO + IR |
| Earnings call | [Earnings Date] | CEO + CFO |

---

## Earnings Release Document

### Required Sections
1. **Headlines** — Revenue, EPS, key metric vs. consensus
2. **Financial tables** — GAAP P&L, Balance Sheet, Cash Flow
3. **Non-GAAP reconciliation** (if applicable) — GC + CFO must validate
4. **Business highlights** — Key operational developments
5. **Full-year guidance** (if provided) — CFO + CEO decision
6. **Safe harbor statement** — GC required; always include

### Legal Review Requirements
- GC must review complete release before Board Audit Committee
- Any non-GAAP metric must be reconciled to GAAP
- All forward-looking statements require safe harbor language
- Any guidance must be approved by CFO + CEO + GC
- Competitive or market share claims must be substantiated

---

## Regulation FD Compliance

**GC enforces Reg FD from blackout start through earnings release.**

During blackout:
- No individual investor meetings disclosing material information
- No selective disclosure to analysts
- Any material disclosure must be simultaneous public disclosure
- All investor inquiries routed through IR + GC approval

---

## Earnings Call Script Structure

1. **Safe harbor / legal disclaimers** (IR reads)
2. **CEO opening** — quarter narrative, strategic highlights, outlook (5–7 minutes)
3. **CFO financial review** — detailed financial walk (8–10 minutes)
4. **Q&A** — CEO + CFO, moderated by IR
5. **Closing** — CEO (1–2 minutes)

### Q&A Preparation
- IR compiles expected analyst questions
- CFO and CEO pre-prepare answers
- GC reviews any legally sensitive questions
- "Parking lot" list prepared for questions that cannot be answered

---

## Hard Constraints

- **NEVER** release financials before external audit review is complete
- **NEVER** provide guidance without CFO + CEO + Board Audit Committee alignment
- **NEVER** use non-standard metrics without GAAP reconciliation
- **NEVER** make selective disclosures to individual investors
- **NEVER** issue earnings release without GC legal clearance

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
