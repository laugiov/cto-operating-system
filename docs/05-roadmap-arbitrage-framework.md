# Roadmap Arbitrage Framework

## Purpose

Systematic approach to prioritization when everything is urgent and resources are constrained.

## When to Use

- Quarterly planning with competing priorities
- Mid-quarter reprioritization requests
- Resource allocation conflicts between teams
- Justifying technical investments to business stakeholders

---

## The Framework

Prioritization is arbitrage: finding the highest value per unit of scarce resource.

```
Priority Score = (Impact × Confidence) / (Effort × Risk)
```

But numbers alone don't decide. The framework structures the conversation.

---

## Step 1: Categorize Work

All work falls into four categories:

| Category | Description | Typical Allocation |
|----------|-------------|-------------------|
| **Features** | New user-facing functionality | 40-60% |
| **Reliability** | SLO improvements, incident prevention | 15-25% |
| **Platform** | Developer experience, infrastructure | 10-20% |
| **Debt** | Refactoring, upgrades, cleanup | 10-20% |

### Setting Allocation
1. Review current state (what does the system need?)
2. Consider company stage (growth vs. consolidation)
3. Account for error budget status
4. Get leadership alignment on allocation

**Rule**: If reliability allocation drops below 15%, you're borrowing from the future.

---

## Step 2: Score Impact

### Impact Dimensions

| Dimension | Low (1) | Medium (2) | High (3) |
|-----------|---------|------------|----------|
| **Revenue** | No impact | Indirect impact | Direct revenue |
| **Users** | < 1% affected | 1-10% affected | > 10% affected |
| **Strategic** | Not aligned | Somewhat aligned | Core to strategy |
| **Risk reduction** | Nice to have | Reduces known risk | Prevents likely incident |

**Total Impact** = Sum of applicable dimensions (max 12)

### Impact Evidence
Don't guess. Require evidence:
- Revenue: Finance projection or historical data
- Users: Product analytics
- Strategic: CEO/CPO confirmation
- Risk: Incident history or threat model

---

## Step 3: Estimate Effort

### Effort Scale

| T-Shirt | Engineering Weeks | Confidence |
|---------|-------------------|------------|
| XS | < 1 week | High |
| S | 1-2 weeks | High |
| M | 2-4 weeks | Medium |
| L | 1-2 months | Medium |
| XL | > 2 months | Low |

### Effort Includes
- Development time
- Code review
- Testing
- Documentation
- Rollout and monitoring

### Confidence Adjustment
If estimate confidence is low, multiply effort by 1.5-2x for planning.

---

## Step 4: Assess Risk

| Risk Factor | Questions |
|-------------|-----------|
| **Technical** | New technology? Complex integration? Unknown unknowns? |
| **Dependency** | External teams? Third-party APIs? Customer coordination? |
| **Reversibility** | Can we roll back? Data migrations? |
| **Timing** | Hard deadline? Market window? |

### Risk Score
- **Low**: Well-understood, reversible, no dependencies
- **Medium**: Some unknowns or dependencies
- **High**: New territory, irreversible, critical timing

---

## Step 5: The Arbitrage Decision

### Build the Matrix

| Initiative | Impact | Effort | Risk | Score | Category |
|------------|--------|--------|------|-------|----------|
| Example A | 9 | M (3) | Low | 9/3=3.0 | Feature |
| Example B | 6 | S (2) | Med | 6/3=2.0 | Debt |
| Example C | 12 | L (5) | High | 12/7.5=1.6 | Platform |

### Decision Rules

1. **Above the line**: Fits in quarter with buffer
2. **Below the line**: Explicitly not doing (communicate this)
3. **Stretch**: Will do if capacity opens up
4. **Cut**: Remove from consideration entirely

### The Conversation
- Present the matrix to stakeholders
- Discuss disagreements on scoring
- Make explicit trade-offs visible
- Document the decision in a [decision memo](../templates/decision-memo.md)

---

## Handling Incoming Requests

Mid-quarter "urgent" requests follow the same framework:

1. **Score it**: Apply impact/effort/risk
2. **Compare it**: Where does it rank vs. current work?
3. **Trade it**: What comes out if this goes in?
4. **Decide it**: Accept, defer, or decline with rationale
5. **Document it**: Update roadmap and communicate

**Rule**: No stealth additions. Every addition removes something or extends timeline.

---

## Checklist

- [ ] Work categorized (Features, Reliability, Platform, Debt)
- [ ] Allocation percentages agreed with leadership
- [ ] Impact scored with evidence
- [ ] Effort estimated with confidence levels
- [ ] Risk assessed
- [ ] Priority matrix created
- [ ] Above/below line decisions made
- [ ] Trade-offs documented

---

## Output

After applying this framework:
- Prioritization decisions defensible with data
- Stakeholders understand what's not being done (and why)
- Engineering capacity protected from "everything is P0"
- Trade-offs visible and documented
