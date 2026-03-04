# Skill: Cross-Functional Coordination

## Purpose
Patterns for coordinating work across executive functions, resolving dependencies, and managing handoffs between agents.

## When to Invoke
- Managing a multi-function initiative
- Resolving cross-BU resource conflicts
- Structuring executive team meetings
- Tracking cross-functional dependencies

## Dependency Mapping Pattern

For any initiative touching 2+ functions:

```
CROSS-FUNCTIONAL DEPENDENCY MAP
Initiative: [INI-YYYY-###]

WORKSTREAMS:
  WS1: [Name] | Owner: [Role] | Target: [date]
  WS2: [Name] | Owner: [Role] | Target: [date]
  WS3: [Name] | Owner: [Role] | Target: [date]

DEPENDENCIES:
  WS2 cannot start until WS1 delivers: [specific artifact]
  WS3 requires input from WS1 AND WS2
  GC review must complete before WS2 begins

CRITICAL PATH:
  WS1 → GC Review → WS2 → WS3 → IA Validation → CEO Approval

PARALLEL WORKSTREAMS (can run simultaneously):
  WS2 and CHRO review (no dependency)
  Risk assessment and financial modeling (no dependency)
```

## Executive Alignment Meeting Pattern

### Weekly Operating Review (COO chairs)
```
Duration: 45 minutes
Attendees: COO + BU Heads + Chief of Staff

Agenda:
  5 min  — Metrics pulse (GREEN/YELLOW/RED by initiative)
  20 min — Blockers only (no status updates for GREEN items)
  10 min — Decisions needed (items requiring cross-BU alignment)
  10 min — Next week priorities

Rules:
  - No powerpoint
  - GREEN items are not discussed unless someone raises a concern
  - Every blocker gets an owner and a resolution date
  - Decisions documented in real-time by Chief of Staff
```

### RACI for Initiative Decisions
| Decision | R (Responsible) | A (Accountable) | C (Consulted) | I (Informed) |
|---|---|---|---|---|
| Budget approval | CFO | CEO | COO, GC | Board if >$10M |
| Legal clearance | GC | GC | CEO | All exec team |
| Operational plan | COO | COO | BU Heads | CEO |
| Go-to-market | CMO | CMO | CRO, GC | CEO |
| Technology choice | CTO | CTO | COO, CFO | CEO |
| People decisions | CHRO | CHRO | GC, COO | CEO |

## Handoff Protocol
Every handoff between agents must include:
1. Work product (the actual deliverable)
2. Exit state signal (the explicit phrase)
3. Open items (anything the receiver needs to know)
4. Decisions made (what was already decided and why)
5. Authority granted (any delegated authority for the next stage)
