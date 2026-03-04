# /ideate — Creative Idea Development Workflow

## Purpose

Takes a rough, partial, or half-formed idea and expands it into structured creative territories ready for executive evaluation. This is a pre-governance, pre-brief creative exploration. No filters are applied during generation — viability, budget, and legal review come after.

## Usage

```
/ideate [partial idea, fragment, or rough concept]
```

**Examples:**
```
/ideate a loyalty program that doesn't feel like a loyalty program
/ideate something that makes our annual report worth reading
/ideate a product launch that gets people talking before we say a word
/ideate use AI to reduce customer support friction
```

---

## Workflow

### Step 1: Idea Intake
- Accept the partial idea as-is — do not evaluate, filter, or judge it at intake
- If the input is fewer than 5 words or is ambiguous, prompt: "Give me one more sentence — what's the instinct behind this?"
- Capture the submitter and date for the creative record

### Step 2: CCO Expansion (Core Step — No Self-Censoring)

Invoke the **CCO agent** to expand the seed idea into **three distinct creative territories**.

Each territory must:
- Have a punchy name (2–4 words)
- Express a clear creative insight (the "why this works" — one sentence)
- Describe the core idea in plain language (3–5 sentences)
- Include at least one unexpected or lateral angle the obvious version would miss
- Propose 2–3 potential expressions or executions (formats, channels, touchpoints)
- Draw at least one reference from outside the industry (art, science, culture, history, sport, etc.)

The CCO must produce all three territories before any evaluation begins. Volume before precision.

### Step 3: Multi-Lens Review

Once territories are formed, route them in parallel for rapid reaction — **not approval**, reaction:

| Agent | Lens | Question They Answer |
|---|---|---|
| CMO | Brand | Does this fit or productively challenge our brand position? |
| CRO | Market | Is there a customer who would pay for or respond to this? |
| CTO | Feasibility | Is there a technology dependency that enables or limits this? |

Each agent provides a 2–3 sentence reaction per territory. No scores. No kill decisions. This is input to the CCO, not a gate.

### Step 4: CCO Synthesis

CCO receives the lens reactions and produces:
- A **recommended territory** (with rationale)
- A **dark horse territory** (the boldest option — worth keeping in play)
- Any territory recommended for **parking** (not killed, just not prioritized now)
- Flags for **GC routing** if any concept involves real people, regulatory-adjacent claims, or culturally sensitive territory

### Step 5: Output — Creative Territory Document

Produce the structured output below. This is the artifact that advances to brief development or is archived for future use.

---

## Output Format

```
CREATIVE TERRITORIES
════════════════════════════════════════════════════════
Seed Idea:    [Original input, verbatim]
Submitted:    [Submitter / Date]
CCO:          [Agent exit signal]
════════════════════════════════════════════════════════

TERRITORY 1: [NAME]
─────────────────────────────────────────────
Insight:      [One sentence — the "why this works"]
Concept:      [3–5 sentences describing the idea]
Executions:   • [Expression 1]
              • [Expression 2]
              • [Expression 3 — optional]
Reference:    [Outside-industry inspiration]
CMO Reaction: [2–3 sentences]
CRO Reaction: [2–3 sentences]
CTO Reaction: [2–3 sentences — only if tech-relevant]

TERRITORY 2: [NAME]
─────────────────────────────────────────────
[Same structure]

TERRITORY 3: [NAME]
─────────────────────────────────────────────
[Same structure]

════════════════════════════════════════════════════════
CCO RECOMMENDATION
─────────────────────────────────────────────
Recommended:  [Territory name + rationale]
Dark Horse:   [Territory name + why it's worth keeping]
Parking Lot:  [Territory name + why it's deferred, not killed]

NEXT STEPS
─────────────────────────────────────────────
[ ] Route recommended territory to CMO for brief development
[ ] Flag [territory] to GC: [reason, if applicable]
[ ] Advance to /start-initiative when brief is approved
[ ] Archive all territories in creative record
════════════════════════════════════════════════════════
```

---

## Rules for This Workflow

1. **No ideas are killed in this workflow** — territories are recommended, deferred, or parked. Killing happens in brief development and governance, not here.
2. **CCO speaks before evaluators** — the multi-lens review cannot begin until all three territories are fully formed. Evaluation during generation poisons the well.
3. **Governance gates are downstream** — this command produces creative fuel, not approved initiatives. Route to `/start-initiative` to begin the governance lifecycle.
4. **GC flags are non-optional** — if CCO identifies a concept touching real people, regulatory claims, or sensitive territory, that flag must appear in the output. GC is not routed here, but the flag is set.
5. **The dark horse must survive** — the CCO must preserve one bold option even if lens reactions are cool. The team decides what bold is worth, not the CCO.

---

## When to Advance to `/start-initiative`

A creative territory is ready to advance when:
- CMO confirms brand fit or productive tension worth exploring
- CRO sees a credible customer response or revenue angle
- The idea can be expressed as a strategic objective (not just an execution)

A territory should stay in ideation when:
- It needs more development before a brief can be written
- Key feasibility questions are unresolved
- Sponsor has not been identified

---

## Related Commands

- `/start-initiative` — advance a creative territory into the full governance lifecycle
- `/board-report` — if the idea reaches strategic significance
- `/legal-review` — standalone GC routing if concepts require early legal guidance
- `/risk-assessment` — if the territory involves material business risk

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
