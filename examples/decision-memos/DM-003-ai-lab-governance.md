# Decision Memo: AI Lab Governance

> Anonymized example.

## Metadata

| Field | Value |
|-------|-------|
| **ID** | DM-003 |
| **Status** | Decided |
| **Author** | VP Engineering |
| **Date** | 2024-02-20 |
| **Approver** | CTO, General Counsel |
| **Review Date** | 2024-08-20 |

---

## Context

Engineering has been experimenting with AI/ML for 6 months in an ad-hoc manner:
- 3 engineers spending ~20% time on AI projects
- 5 experiments completed, 2 showing promise
- No formal governance, data handling, or evaluation process
- Legal has raised concerns about training data and output liability
- One experiment accidentally used customer data without proper anonymization

We need to formalize AI experimentation to enable continued innovation while managing risk.

---

## Options Considered

### Option 1: Pause All AI Work (Risk avoidance)

**Description**: Stop AI experimentation until comprehensive policy is developed.

| Aspect | Assessment |
|--------|------------|
| Pros | Zero risk, time to develop thorough policy |
| Cons | Lose momentum, talent frustrated, competitive disadvantage |
| Effort | None (stopping) |
| Risk | Low technical, high strategic |

### Option 2: Lightweight Governance (Guardrails only)

**Description**: Minimal process - just data boundaries and approval for production.

| Aspect | Assessment |
|--------|------------|
| Pros | Low overhead, preserves experimentation speed |
| Cons | May not satisfy legal, gaps in evaluation |
| Effort | S (2-3 weeks to document) |
| Risk | Medium - may need to revisit |

### Option 3: Full Governance Framework (Comprehensive)

**Description**: Complete framework with stages, gates, data governance, evaluation, and monitoring.

| Aspect | Assessment |
|--------|------------|
| Pros | Comprehensive risk management, scalable |
| Cons | Higher overhead, may slow early experimentation |
| Effort | M (6-8 weeks to implement) |
| Risk | Low |

### Option 4: External AI Only (No internal development)

**Description**: Only use third-party AI services, no internal model development.

| Aspect | Assessment |
|--------|------------|
| Pros | Lower complexity, vendor handles compliance |
| Cons | Limited differentiation, vendor lock-in, data leaves our control |
| Effort | S (evaluation and integration) |
| Risk | Medium - different risk profile, not lower |

---

## Decision

**We will adopt Option 3: Full Governance Framework, implemented incrementally.**

Phase 1 (immediate): Data boundaries and experiment registration
Phase 2 (month 1): Evaluation framework and red teaming
Phase 3 (month 2): Production pathway and monitoring

---

## Rationale

- **Legal requirement**: Counsel requires documented governance before any AI touches production
- **Incident learning**: Customer data incident showed ad-hoc approach has real risk
- **Scalability**: Framework enables more people to experiment safely, not fewer
- **Competitive necessity**: AI capabilities are strategic; pausing loses ground
- **Option 2 rejected**: Lightweight approach doesn't address legal concerns adequately

Trade-offs accepted:
- Initial overhead for experiment registration
- Slower path to production (but clearer)
- Resource investment in governance infrastructure

---

## Governance Framework

### Data Governance

| Data Type | Allowed for Training | Allowed for Eval | Approval Required |
|-----------|---------------------|------------------|-------------------|
| Synthetic data | Yes | Yes | No |
| Anonymized production data | Yes | Yes | Data team review |
| Production data (non-PII) | Case-by-case | Yes | Security + Legal |
| Production data (PII) | No | No | N/A |
| Third-party datasets | License-dependent | License-dependent | Legal review |

### Experiment Stages

```
Idea → Registration → Experiment → Evaluation → Decision → Production
```

| Stage | Gate | Approver |
|-------|------|----------|
| Registration | Data sources approved | Lab lead |
| Experiment | Time-boxed, resourced | Lab lead |
| Evaluation | Success criteria met | Lab + stakeholders |
| Production | Full review complete | CTO + Legal |

### Required Documentation

| Stage | Documentation |
|-------|---------------|
| Registration | One-pager with data sources |
| Experiment | Experiment card |
| Evaluation | Model evaluation report |
| Production | Architecture review + security review |

### Red Teaming Requirements

Before any model serves users:
- Prompt injection testing
- Output safety evaluation
- Bias assessment (where applicable)
- Edge case documentation

### Model Registry

All models (including experiments) registered with:
- Purpose and owner
- Training data provenance
- Version history
- Evaluation results
- Status (experiment/staging/production/deprecated)

---

## Consequences

- [ ] Lab lead role assigned (existing engineer, 50% allocation)
- [ ] Templates created: one-pager, experiment card, eval report
- [ ] Model registry set up (simple spreadsheet initially)
- [ ] Bi-weekly AI review meeting established
- [ ] Legal added to production approval workflow
- [ ] Data team trained on AI data requests

---

## Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Overhead slows innovation | Medium | Medium | Start lightweight, iterate based on feedback |
| Engineers resist process | Low | Medium | Involve engineers in design, show value |
| Framework becomes bureaucratic | Medium | Medium | Quarterly review, sunset unused requirements |
| Gaps discovered later | Medium | Low | Iterative approach, learn and adapt |

---

## Success Metrics

| Metric | Target |
|--------|--------|
| Experiments registered | 100% |
| Time from idea to experiment start | < 1 week |
| Time from experiment to production decision | < 6 weeks |
| Compliance incidents | 0 |
| Experiments reaching production | 15-25% |

---

## Stakeholders Consulted

- General Counsel - Confirmed framework addresses legal concerns
- Data team - Agreed to data review process
- AI engineers - Provided input on practical workflow
- Security - Approved red teaming approach
- Product - Aligned on production pathway

---

## Related Documents

- [AI Lab Operating Guide](../../docs/08-innovation-ai-rnd-lab.md)
- [Experiment Card Template](../../templates/experiment-card.md)
- [Model Evaluation Template](../../templates/model-eval-report.md)
