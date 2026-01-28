# Decision Memos Playbook

How to document technical decisions so they're useful later.

**Use this when:**

- Architectural decisions affecting multiple teams
- Technology selection or migration
- Trade-offs between competing priorities
- Decisions that will be questioned later
- Any choice you'd want documented if you left the company

---

## Why Write Decision Memos

### Without Decision Memos
- "Why did we choose this database?" → Nobody remembers
- "Should we reconsider?" → No context on what was considered
- "Who approved this?" → Unknown
- New team members → Repeat past mistakes

### With Decision Memos
- Decisions searchable and auditable
- Context preserved for future evaluation
- Onboarding accelerated
- Revisiting decisions is informed, not from scratch

---

## Decision Memo Structure

**Template**: [decision-memo.md](../templates/decision-memo.md)

### Required Sections

| Section | Purpose | Length |
|---------|---------|--------|
| **Title** | Clear statement of decision | 1 line |
| **Status** | Draft / In Review / Decided / Superseded | 1 word |
| **Context** | Why this decision is needed now | 2-5 sentences |
| **Options Considered** | What alternatives were evaluated | 3-5 options |
| **Decision** | What was chosen | 1-2 sentences |
| **Rationale** | Why this option won | 3-5 bullets |
| **Consequences** | What changes as a result | 3-5 bullets |
| **Risks** | What could go wrong | 2-4 bullets |
| **Review Date** | When to revisit | Date |

### Optional Sections
- Stakeholders consulted
- Related decisions
- Implementation plan
- Metrics for success

---

## Writing Good Context

### Bad Context
> "We need to choose a message queue."

### Good Context
> "Our current architecture uses direct HTTP calls between services.
> As we scale to 10M events/day, we're seeing cascading failures when
> downstream services are slow. We evaluated this after three incidents
> in Q3 where payment service latency caused checkout failures."

### Context Checklist
- [ ] What triggered this decision?
- [ ] What are the constraints (time, money, people)?
- [ ] What happens if we don't decide?
- [ ] Who is affected?

---

## Evaluating Options

### Option Template
For each option:
1. **Description**: What is it?
2. **Pros**: Why it might work
3. **Cons**: Why it might not
4. **Effort**: Rough estimate
5. **Risk**: What could go wrong

### Fair Evaluation
- Give each option genuine consideration
- Include "do nothing" as an option
- Don't strawman alternatives
- Quantify where possible

### Example Options Table

| Option | Pros | Cons | Effort | Risk |
|--------|------|------|--------|------|
| Kafka | Battle-tested, scalable | Operational complexity | 3 months | Medium |
| SQS | Managed, simple | AWS lock-in | 1 month | Low |
| RabbitMQ | Flexible, team knows it | Scaling concerns | 2 months | Medium |
| Do nothing | No effort | Problems continue | None | High |

---

## Making the Decision

### Decision Criteria
Rank what matters:
1. Time to implement (are we deadline-driven?)
2. Operational cost (can we maintain it?)
3. Scalability (will it handle growth?)
4. Team expertise (do we know it?)
5. Reversibility (can we change later?)

### Decision Format
> **Decision**: We will use SQS for async communication between services.

State it clearly. No hedging.

---

## Writing Rationale

### Bad Rationale
> "SQS seemed like the best choice."

### Good Rationale
> - Team expertise: 3 engineers have SQS experience; 0 have Kafka
> - Time: SQS implementation estimated at 4 weeks vs. 12 for Kafka
> - Scale: SQS handles our projected load for 2 years
> - Cost: Managed service reduces operational burden on 4-person team
> - Reversibility: Message abstraction layer allows future migration

### Rationale Principles
- Tie back to decision criteria
- Acknowledge trade-offs
- Be honest about what you don't know
- Future-proof: explain what might change this decision

---

## Consequences and Risks

### Consequences
What changes after this decision:
- Teams affected
- Systems modified
- Processes updated
- Training needed

### Risks
What could invalidate this decision:
- Scale beyond projections
- Vendor changes
- Team expertise leaves
- Requirements change

For each risk, note:
- Likelihood (Low/Medium/High)
- Impact (Low/Medium/High)
- Mitigation (what we'll do if it happens)

---

## Review Process

### Who Reviews
- Technical stakeholders (affected teams)
- Architecture/platform team
- Security (if applicable)
- Leadership (if org-wide impact)

### Review Timeline
1. **Draft**: Author writes initial version
2. **Review period**: 3-5 business days for comments
3. **Discussion**: Meeting if needed (async preferred)
4. **Decision**: Approver signs off
5. **Communication**: Announcement to affected parties

### Approval Authority

| Impact | Approver |
|--------|----------|
| Single team | Tech Lead or EM |
| Multiple teams | Director or Architect |
| Organization-wide | VP/CTO |

---

## Decision Lifecycle

| Status | Meaning |
|--------|---------|
| **Draft** | Under development |
| **In Review** | Open for comments |
| **Decided** | Approved and active |
| **Superseded** | Replaced by newer decision |
| **Deprecated** | No longer applicable |

### Revisiting Decisions
- Set review date at time of decision
- Trigger review if assumptions change
- Document why decision changed (don't just delete)

---

## Checklist

- [ ] Context explains why now
- [ ] Multiple options genuinely considered
- [ ] Decision stated clearly
- [ ] Rationale ties to criteria
- [ ] Consequences documented
- [ ] Risks identified with mitigations
- [ ] Review date set
- [ ] Stakeholders have reviewed
- [ ] Decision communicated

---

## Output

After adopting decision memos:
- Decisions discoverable and searchable
- New team members understand "why"
- Revisiting decisions is informed
- Organizational learning preserved
- Reduced decision thrash
