# Innovation & AI/R&D Lab

How to run an R&D lab without it becoming a science project.

**Use this when:**
- Starting an R&D or innovation function
- Adding AI/ML capabilities
- Governing experimental work

---

## Operating Model

### Time Allocation

| Model | Description | Best For |
|-------|-------------|----------|
| **Dedicated team** | Full-time R&D team (3-5 people) | Orgs > 50 engineers, strategic bets |
| **20% time** | 1 day/week for exploration | Smaller orgs, culture building |
| **Sprint rotation** | 1-2 sprints/quarter for experiments | Balanced approach |
| **Hackathons** | Quarterly concentrated innovation | Quick validation, team building |

### Recommended: Hybrid Model
- Small dedicated team (2-3) for continuity
- 10-20% time from product teams for participation
- Quarterly demo days for visibility
- Monthly triage for prioritization

---

## Innovation Pipeline

```
Idea → One-pager → Experiment Card → Evaluation → Decision → Productization
```

### Stage Gates

| Stage | Artifact | Decision Maker | Success Criteria |
|-------|----------|----------------|------------------|
| **Idea** | Slack thread or brief | Anyone | Worth 30 min discussion |
| **One-pager** | [lab-proposal-onepager.md](../templates/lab-proposal-onepager.md) | Lab lead | Worth 1-2 week experiment |
| **Experiment** | [experiment-card.md](../templates/experiment-card.md) | Lab lead | Hypothesis testable |
| **Evaluation** | [model-eval-report.md](../templates/model-eval-report.md) | Lab + stakeholders | Success criteria met |
| **Decision** | Decision memo | Leadership | Productize, iterate, or kill |
| **Productization** | Engineering handoff | Product + Engineering | Production-ready |

---

## Experiment Card

**Template**: [experiment-card.md](../templates/experiment-card.md)

### Required Fields
- **Hypothesis**: "We believe [action] will result in [outcome]"
- **Success criteria**: Measurable thresholds
- **Kill criteria**: When to stop
- **Time box**: Maximum duration (default: 2 weeks)
- **Resources**: People, compute, data
- **Risks**: What could go wrong

### Example
```
Hypothesis: Fine-tuning a small LLM on our support tickets will
reduce average resolution time by 20%.

Success criteria:
- Resolution time decreases by ≥15%
- User satisfaction maintains ≥4.0/5.0
- Cost per query < $0.02

Kill criteria:
- Accuracy < 70% after tuning
- Cost exceeds $0.10 per query
- Cannot meet data privacy requirements

Time box: 3 weeks
```

---

## AI/ML Governance

### Data Governance

| Requirement | Implementation |
|-------------|----------------|
| **Data boundaries** | Approved datasets only, documented provenance |
| **PII handling** | Anonymization required, retention limits |
| **Training data** | Licensed or owned, no scraped data without review |
| **Model inputs** | Logged for audit, no sensitive data without encryption |

### Model Registry

Track all models, even experiments:

| Field | Description |
|-------|-------------|
| Model ID | Unique identifier |
| Purpose | What it does |
| Training data | Dataset references |
| Version | Current version |
| Owner | Responsible team/person |
| Status | Experiment / Staging / Production / Deprecated |
| Evaluation | Link to eval report |

### Red Teaming (Defensive)

Before any model touches users:
- [ ] Prompt injection testing
- [ ] Output safety evaluation
- [ ] Bias and fairness assessment
- [ ] Edge case behavior review
- [ ] Failure mode documentation

---

## Metrics

### Innovation Health

| Metric | What It Measures | Target |
|--------|------------------|--------|
| **Time-to-learn (TTLearn)** | Idea to validated learning | < 4 weeks |
| **Experiment velocity** | Experiments completed/quarter | 6-12 |
| **Success rate** | Experiments meeting success criteria | 20-40% |
| **Productization rate** | Experiments reaching production | 10-20% |
| **Cost per experiment** | Total cost / experiments | Decreasing |

### What Not to Measure
- Ideas generated (vanity metric)
- Lines of code (irrelevant for R&D)
- Time spent (measure outcomes, not effort)

---

## Budget and Resources

### Typical Allocation

| Resource | Guideline |
|----------|-----------|
| Headcount | 5-10% of engineering |
| Compute | Dedicated budget, not shared prod quota |
| Time | 10-20% from participating teams |
| Training | Budget for courses, conferences, papers |

### Cost Control
- Time-boxed experiments (default: 2 weeks max)
- Compute quotas per experiment
- Monthly budget review
- Auto-shutdown for idle resources

---

## Handoff to Production

### Productization Checklist
- [ ] Code meets production standards (not notebook code)
- [ ] Tests exist (unit, integration, evaluation)
- [ ] Documentation complete
- [ ] Monitoring and alerting defined
- [ ] Rollback plan documented
- [ ] On-call ownership assigned
- [ ] Security review completed
- [ ] Performance benchmarks met

### What Doesn't Transfer
- Notebook code (must be rewritten)
- Undocumented models
- Experiments without evaluation
- "It works on my machine"

---

## Common Failure Modes

| Failure | Prevention |
|---------|------------|
| Innovation theater (demos without impact) | Require productization path |
| Science projects (no business value) | Tie to business outcomes |
| Premature scaling (scaling unproven ideas) | Enforce evaluation gates |
| No governance (AI risks) | Red teaming, model registry |
| Talent hoarding (lab becomes silo) | Rotation, knowledge sharing |

---

## Checklist

- [ ] Innovation model chosen and resourced
- [ ] Pipeline stages defined with templates
- [ ] Experiment card template in use
- [ ] Model registry established
- [ ] Red teaming process defined
- [ ] Metrics tracked
- [ ] Productization criteria documented
- [ ] Budget and compute quotas set

---

## Output

After implementing this:
- Path from idea to production
- Experiments time-boxed and evaluated
- AI/ML governance in place
- Innovation tied to business outcomes
