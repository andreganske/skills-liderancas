# Mode: org-design

Designs the current and future product org. A Head of Product owns the structure.

## When to use

- "How do I scale the team?"
- "What's the ideal structure?"
- "Who do I need to hire?"
- Before proposing organizational changes to the CEO
- When a product's PM vacancy needs to be defined

## Flow

### 1. Map current state

Ask (or read from context):
- How many PMs? Which products?
- What is the PM:Eng:Design ratio?
- Who reports to whom?
- Where are the bottlenecks?

**Current state (example):**
```
The leader
├── PM-A — Product A core, a new product area
├── PM-B — Product B (possible move to the new product area)
└── [Open] — Product C (PM vacancy to fill)
```

Moves under evaluation: PM-B → the new product area; a team member → PM of another product.

### 2. Org design principles for product

| Principle | What it means | Anti-pattern |
|---|---|---|
| **Teams by outcome, not by component** | Team owns "reduce churn" not "reports screen" | Feature team without outcome ownership |
| **Autonomy with alignment** | Team decides how, the lead/Head defines what | Micromanagement disguised as alignment |
| **Mandatory trio** | PM + Design + Eng Lead = minimum unit | PM without a designer or without an eng lead |
| **Cognitive load** | Each PM masters only 1-2 areas of complexity | PM responsible for 5 products |
| **Sustainability** | Org works without individual heroism | Depends on 1 person for everything |

### 3. Scaling model (Cagan)

| Size | Structure | Product leader |
|---|---|---|
| 1-3 PMs | The leader manages directly | The leader today |
| 4-7 PMs | The leader + informal leads | The leader, delegating more |
| 8-15 PMs | Head + 2-3 leads | Head of Product (the leader's target) |
| 15+ PMs | VP/CPO + Directors | VP/CPO |

**For the company:** with 3 products and a scaling goal, the target org over the next 12-18 months would be:

```
The leader (Head of Product)
├── [Lead/Senior PM] — Product A (core engine + integrations)
├── [PM] — a new product area
├── [PM] — Product B
└── [PM] — Product C
```

### 4. Exercise

"Design the ideal product org for the company 18 months from now. Justify each position in terms of business impact, not in terms of workload."

Provocations:
- "How many PMs do you need to deliver the North Star?"
- "If you could only hire 1 person, who would it be and why?"
- "Does this org work if you go on vacation for 2 weeks?"

### 5. Output

- Current + target org chart (with transition timeline)
- Job descriptions for new roles (in impact language)
- Sequenced hiring plan
- Risks: what breaks if hiring doesn't happen in time?

Before closing, run the SKILL.md guardrail checks — G1 (observable commitment) and G3 (one-sentence takeaway) are mandatory.

Save to `org-design-drafts/YYYY-MM-DD.md`.
