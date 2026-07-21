# Mode: career-plan

Generates or updates a 12-month career plan with measurable milestones for the transition to the next leadership level.

## When to use

- First run: create the baseline plan
- Quarterly: review and adjust
- After a diagnostic that reveals a change in priorities
- When an external opportunity or threat arises (job opening, executive feedback, company change)

## Flow

### 1. Read full context

- `profile.md`
- `operating-model.md`
- `career-plan.md` → the current career plan (this is what you update)
- `coach-log.md` → previous diagnostics (read on demand for history)
- `research/market-product-leadership-career.md` — market research
- Read `references/frameworks/first-90-days.md`

### 2. Define the "Definition of Done" for the promotion

Ask (if not documented): "What needs to be true for the company to promote you to Head of Product? Who decides? What are the explicit and implicit criteria?"

If the leader doesn't know: this is the first gap to resolve. The plan starts by mapping the criteria.

### 3. Plan Structure — 4 Quarters

For each quarter, define:

**Q[X] — [Theme]**

| Dimension | Goal | Evidence of success | Status |
|---|---|---|---|
| Scope | | | |
| Strategy | | | |
| People | | | |
| Business | | | |
| Stakeholders | | | |

**Learning investments this Q:**
- [Course/program/reading — with estimated cost and time]

**Product deliveries that demonstrate Head-level work:**
- [Delivery 1 — how it connects to dimension X]

**Strategic conversations to initiate:**
- [With whom, about what, toward what outcome]

### 4. Sequencing by Quarter (skeleton to fill)

A four-quarter arc, each quarter with a theme, a few concrete milestones, and one learning investment. Fill with the leader's real context — the labels below are placeholders.

**[Qn/YYYY] — Diagnostic + Foundation**
- [Self-assessment with a competency toolkit]
- [Product Vision v1 documented and presented]
- [First simplified P&L for the product]
- [Strategy Session inaugurated]
- Investment: [course/program — cost or time]

**[Qn/YYYY] — Demonstration**
- [Product Vision refined with CEO feedback]
- [Org design documented (current + target)]
- [First executive narrative delivered to C-level]
- [Evidence of team development (assessment delta)]
- Investment: [course/program — cost or time]

**[Qn/YYYY] — Consolidation**
- [P&L ownership demonstrated]
- [Skip-levels established]
- [Influence map updated with completed actions]
- Investment: [course/program — cost or time]

**[Qn/YYYY] — Transition**
- [Business case for the target role documented]
- [First 90 days in the target role planned]
- [Formal promotion conversation]
- [Consolidated evidence across all five leadership dimensions]

### 5. Pre-Mortem of the Plan

"It's [target date] and this plan failed. Top 3 most likely reasons:"
1. [Based on profile — e.g.: a trap recorded in profile.md delayed action]
2. [Based on context — e.g.: operational crisis consumed strategic time]
3. [Based on market — e.g.: company shifted priorities]

For each: "What do I do NOW to mitigate?"

### 6. Accountability Design

- **Weekly check:** mode `weekly-check` — classify the week as L/N/O
- **Monthly diagnostic:** mode `diagnostic` — update scores
- **Quarterly review:** this mode — adjust the plan
- **External accountability person:** [who? mentor? coach? peer?]

### 7. Generate output

---
**Career Plan — the leader**
**Goal:** Head of Product — the company
**Horizon:** [current date] → [target date]
**Based on diagnostic from:** [date of last diagnostic]

[4 detailed quarters]

**Total estimated investment:** [sum of courses/programs]

**Pre-mortem — risks and mitigations:**
[3 risks + mitigations]

**Accountability:**
[Cadence + who tracks]

**Coach's provocation:**
[A question that forces the leader to confront the most uncomfortable gap in the plan]

---

### 8. Save

Save to `career-plan.md` (the canonical career plan — update it in place; do not create a second plan file).
Update `coach-state.md` Current Standing with a reference to the revised plan.

Before closing, run the SKILL.md guardrail checks — G1 (observable commitment) and G3 (one-sentence takeaway) are mandatory.

Offer: "Do you want to run the first weekly check now?"
