# Skill: Revenue Operations

## Purpose
Patterns for building and operating a revenue engine — pipeline management, forecasting, deal structure, and CRM hygiene.

## When to Invoke
- Pipeline review and forecast preparation
- Deal structure and pricing decisions
- CRM data quality issues
- Sales process design or troubleshooting

## Forecasting Methodology

### Forecast Categories
| Category | Definition | Close probability |
|---|---|---|
| Commit | Will close this period — rep is committing | 90%+ |
| Best Case | Likely to close; some risk remains | 50–89% |
| Pipeline | In play; outcome uncertain | 20–49% |
| Omitted | Known opportunity, not forecasting this period | <20% |

### Forecast Call Structure (Weekly)
```
1. Rep commits for current quarter (no hedging)
2. Manager applies judgment overlay
3. CRO produces company forecast:
   - Commit: $[X]
   - Best Case upside: +$[X]
   - Downside risk: -$[X]
4. CFO and CEO review; flag gaps vs. plan
5. Actions assigned to close gaps
```

## Pipeline Health Metrics

| Metric | Target | Caution | Red |
|---|---|---|---|
| Pipeline coverage (vs. quota) | 3–4x | 2–3x | <2x |
| Avg deal size vs. target | ±20% | ±30% | >±30% |
| Avg sales cycle vs. benchmark | ±20% | ±30% | >±30% |
| Win rate | Benchmark | Declining | Declining >10% |
| Stage progression velocity | On trend | Slowing | Stalled deals >30 days |

## Deal Governance Rules

### Standard Deal (within normal parameters)
- CRO approves
- Standard contract terms
- No GC routing required

### Non-Standard Deal (triggers review)
Any deal with:
- Custom SLAs → COO + CTO review
- IP licensing or data sharing → GC mandatory
- Revenue recognition questions → CFO mandatory
- Contract value >$500K with non-standard terms → GC mandatory
- Government or regulated entity → GC mandatory
- Multi-year with unusual payment terms → CFO mandatory

### Discount Authority Matrix
| Discount Level | Authority |
|---|---|
| 0–10% | Account Executive |
| 10–20% | Sales Manager |
| 20–30% | VP Sales or CRO |
| >30% | CRO + CFO |
| >40% | CRO + CFO + CEO |

## CRM Data Standards

Required fields for pipeline integrity:
- Close date (specific date — not "end of quarter")
- Commit category (from methodology above)
- Next step (specific action + date)
- Economic buyer confirmed (name, not just "working with procurement")
- Competitive status (sole source / competitive / unknown)
- Deal amount (final, not range)

Clean CRM is not optional. CRO enforces data quality monthly.
