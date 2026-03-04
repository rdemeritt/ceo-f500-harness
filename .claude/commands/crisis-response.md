# /crisis-response — Crisis Response Protocol

## Purpose

Activates structured crisis response for any HIGH or CRITICAL risk event. Coordinates the executive team, establishes a command structure, and drives toward resolution and stakeholder communication.

## Usage

```
/crisis-response [brief description of crisis]
```

---

## Crisis Classification

Run first. Classify the crisis to determine response level.

| Level | Criteria | Response Team |
|---|---|---|
| L1 — Operational | Operational disruption, contained impact, no external visibility | COO + affected BU Head |
| L2 — Business | Material financial or customer impact, internal escalation required | COO + CFO + CEO |
| L3 — Enterprise | Regulatory, legal, or reputational threat; external stakeholders affected | CEO + GC + CFO + CMO (Corp Comms) |
| L4 — Existential | Criminal, catastrophic financial, or company-threatening event | Board + CEO + GC + external crisis counsel |

---

## Response Protocol by Level

### L1 Protocol (COO leads)
1. COO assumes incident command
2. Notify CEO within 2 hours
3. Contain impact, restore operations
4. Document root cause and corrective actions
5. Close-out report to CEO

### L2 Protocol (CEO leads)
1. CEO assumes incident command
2. CFO assesses financial impact (current and forward-looking)
3. GC assesses legal exposure
4. COO manages operational response
5. CEO decides on external communication (with GC)
6. Daily briefing until resolved

### L3 Protocol (CEO leads with full executive team)
1. CEO assumes incident command
2. Invoke crisis response team (CEO, CFO, GC, CMO, CTO, CHRO as relevant)
3. GC takes lead on any regulatory or litigation dimension
4. CMO/Corp Comms prepares statement (GC reviews before release)
5. CEO or designated spokesperson handles media
6. Board notification within 24 hours
7. External experts engaged (PR crisis firm, regulatory counsel) as needed

### L4 Protocol (Board leads)
1. CEO notifies Board Chair immediately
2. Board convenes emergency session within 48 hours
3. GC engages external crisis counsel
4. Outside forensics if needed (data breach, fraud)
5. Regulatory notification per applicable regulations
6. All external communications cleared by GC and Board

---

## Crisis Command Structure

```
INCIDENT COMMAND ASSIGNMENTS
════════════════════════════════════════════════
Crisis ID: CRS-YYYY-###
Classification: [L1 | L2 | L3 | L4]
Incident: [Description]
Time of Detection: [timestamp]
Incident Commander: [Role]
════════════════════════════════════════════════

COMMAND TEAM:
  Incident Commander:         [CEO | COO]
  Legal Lead:                 [GC]
  Communications Lead:        [CMO / Corp Comms]
  Financial Lead:             [CFO]
  Technical Lead (if cyber):  [CTO]
  HR Lead (if people):        [CHRO]
  External Counsel:           [GC engages as needed]

COMMUNICATION CADENCE:
  Internal updates every:     [1 hour | 4 hours | 24 hours]
  Board notification:         [immediate | within 24h | at resolution]
  External statement:         [hold | issue within X hours]

STAKEHOLDER NOTIFICATION LIST:
  [ ] Board of Directors (by: [timeline])
  [ ] Employees (by: [timeline])
  [ ] Customers (by: [timeline])
  [ ] Regulators (by: [timeline + regulation])
  [ ] Media (if applicable)
  [ ] Investors (if material)
════════════════════════════════════════════════
```

---

## Communication Rules During Crisis

1. **One voice externally.** All media/public statements go through Incident Commander approval + GC review.
2. **No speculation.** Only confirmed facts in external communications.
3. **No social media commentary** from executives without GC clearance.
4. **Internal communication** before external when possible.
5. **Legal privilege.** All communications with GC during crisis are privileged — label accordingly.

---

## Post-Crisis Requirements

Within 30 days of resolution:
- Root cause analysis document
- Corrective action plan with owners and deadlines
- Regulatory response documentation (if applicable)
- Lessons learned briefing to CEO and Board
- Update risk register

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
