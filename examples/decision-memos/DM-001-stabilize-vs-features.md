# Decision Memo: Stabilization vs. Feature Velocity

> Anonymized example.

## Metadata

| Field | Value |
|-------|-------|
| **ID** | DM-001 |
| **Status** | Decided |
| **Author** | Engineering Leadership |
| **Date** | Quarter start + 5 days |
| **Approver** | CTO |
| **Review Date** | Quarter end |

---

## Context

Previous quarter saw significant feature velocity (12 major features shipped) but reliability degraded:
- SLO compliance dropped from 99.9% to 99.2%
- Error budget exhausted by week 8 of 12
- 3 SEV1 incidents (vs. 0 in prior quarter)
- On-call burden increased 40% (avg 4.2 pages/night vs. 3.0)

Product has communicated 8 high-priority features for the upcoming quarter to support a partnership launch. Engineering capacity is 45 engineer-weeks after accounting for on-call, meetings, and PTO.

**Error budget policy reminder**: When error budget is exhausted, reliability work becomes mandatory until budget is restored.

We must decide how to allocate capacity between stabilization and new features.

---

## Options Considered

### Option 1: Feature-First (70% features, 30% reliability)

**Description**: Prioritize partnership features, minimal reliability work.

| Aspect | Assessment |
|--------|------------|
| Pros | Meets product timeline, partnership not at risk |
| Cons | Reliability likely degrades further, team burnout risk |
| Effort | Standard |
| Risk | High - more incidents likely |

Projected outcome:
- 6-7 features delivered
- SLO likely drops to 98.5-99%
- On-call burden increases further

### Option 2: Balanced (50% features, 50% reliability)

**Description**: Split capacity evenly, prioritize most critical features.

| Aspect | Assessment |
|--------|------------|
| Pros | Addresses reliability without abandoning roadmap |
| Cons | Fewer features, product timeline pressure |
| Effort | Standard |
| Risk | Medium - partial progress on both fronts |

Projected outcome:
- 4-5 features delivered
- SLO recovers to 99.5%
- On-call burden stabilizes

### Option 3: Stability-First (30% features, 70% reliability)

**Description**: Focus on reliability, minimal new features.

| Aspect | Assessment |
|--------|------------|
| Pros | Addresses root causes, sustainable foundation |
| Cons | Partnership features at risk, product relationship strained |
| Effort | Standard |
| Risk | Low technical, high business |

Projected outcome:
- 2-3 features delivered
- SLO recovers to 99.9%
- On-call burden returns to normal

### Option 4: Do Nothing (Continue current pattern)

**Description**: Maintain current allocation and hope for the best.

| Aspect | Assessment |
|--------|------------|
| Pros | No difficult conversations |
| Cons | Problems compound, incident likely |
| Effort | None |
| Risk | Very high |

---

## Decision

**We will adopt Option 2: Balanced allocation (50% features, 50% reliability).**

---

## Rationale

- **Error budget exhaustion**: Our error budget policy requires reliability focus when exhausted. Option 1 violates this policy.
- **Partnership risk is manageable**: 4-5 features can support a reduced partnership scope. Product confirmed 4 are "must have," 4 are "nice to have."
- **Team sustainability**: Current on-call burden is unsustainable. Two engineers have flagged burnout concerns.
- **Next quarter setup**: Investing in reliability now sets up a stronger foundation for full feature velocity.
- **Option 3 too aggressive**: Business impact of only 2-3 features is significant. Balanced approach is defensible.

Trade-offs accepted:
- Product will need to negotiate reduced scope with partner
- 4 "nice to have" features deferred to next quarter
- Some business stakeholder disappointment expected

---

## Reversibility

| Aspect | Reversible? | Notes |
|--------|-------------|-------|
| Allocation decision | Yes | Can adjust at mid-quarter checkpoint |
| Deferred features | Yes | Can be pulled forward if reliability improves faster |
| Partnership scope reduction | Partially | Once communicated, harder to change back |
| Team assignments | Yes | Can rebalance based on progress |

**Key irreversible element**: External communication to partner about reduced scope. This should be the last action taken, after internal alignment is confirmed.

---

## Consequences

- [ ] Product to reprioritize roadmap (Day +5)
- [ ] Engineering to identify top 5 reliability improvements (Day +7)
- [ ] Weekly SLO review added to exec meeting (ongoing)
- [ ] OKRs updated to include reliability targets (Day +10)
- [ ] Mid-quarter checkpoint to assess and adjust (Week 6)

---

## Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Reliability work takes longer than expected | Medium | Medium | Time-boxed work, weekly reviews |
| Partner pushes back on reduced scope | Medium | High | CPO to manage relationship, escalation path defined |
| Team perceives this as feature freeze | Low | Medium | Clear communication that this is balanced, not stopped |

---

## Stakeholders Consulted

- CPO - Confirmed 4 must-have features, accepted scope reduction
- VP Engineering - Supported balanced approach
- On-call engineers - Validated burnout risk
- Partner team lead - Informed of potential scope change

---

## Related Documents

- Q1 Incident Summary
- SLO Dashboard
- Revised Roadmap
