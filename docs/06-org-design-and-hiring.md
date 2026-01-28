# Org Design and Hiring

How to structure teams and hire.

**Use this when:**

- Scaling engineering organization
- Restructuring teams after growth or change
- Establishing hiring practices
- Evaluating team health and structure

---

## Team Structure Models

### Team Topologies (Simplified)

| Type | Purpose | Size | Dependencies |
|------|---------|------|--------------|
| **Stream-aligned** | Delivers value for a business domain | 5-9 | Minimal, owns end-to-end |
| **Platform** | Provides capabilities to other teams | 4-8 | Serves stream-aligned teams |
| **Enabling** | Helps teams adopt new capabilities | 2-4 | Temporary, consultative |
| **Complicated-subsystem** | Manages complex technical domain | 3-6 | Provides APIs/interfaces |

### Sizing Guidelines

| Org Size | Recommended Structure |
|----------|----------------------|
| 5-15 engineers | 1-2 teams, minimal hierarchy |
| 15-40 engineers | 3-6 teams, tech leads, 1-2 managers |
| 40-100 engineers | Departments, directors, platform team emerges |
| 100+ engineers | Multiple departments, VP layer, specialized teams |

### Team Health Indicators

| Healthy | Warning Signs |
|---------|---------------|
| Owns decisions end-to-end | Needs approval for everything |
| Ships independently | Blocked by other teams weekly |
| Clear mission | Unclear why they exist |
| Sustainable pace | Constant crunch |
| Low turnover | Frequent departures |

---

## Span of Control

| Role | Direct Reports | Notes |
|------|----------------|-------|
| Tech Lead | 0 (IC role) | Technical leadership, not people management |
| Engineering Manager | 5-8 | First-line people management |
| Senior EM | 6-10 | Can handle larger teams if experienced |
| Director | 4-7 managers | Or mix of managers and senior ICs |
| VP | 4-6 directors | Strategic focus, limited direct ICs |

**Warning signs**:
- Manager with 12+ reports = burnout, insufficient 1:1 time
- Manager with 2 reports = overhead, consider restructure

---

## Hiring Framework

### Job Architecture

| Level | Scope | Experience | Title Examples |
|-------|-------|------------|----------------|
| L1 | Task | 0-2 years | Junior Engineer |
| L2 | Feature | 2-4 years | Engineer |
| L3 | Project | 4-7 years | Senior Engineer |
| L4 | Team/System | 7-12 years | Staff Engineer |
| L5 | Organization | 12+ years | Principal Engineer |

### Hiring Process

1. **Intake**: Role requirements, level, team fit
2. **Sourcing**: Referrals, recruiting, inbound
3. **Screen**: Resume review, recruiter call (30 min)
4. **Technical**: Coding + system design (2-4 hours)
5. **Behavioral**: Values, collaboration (1 hour)
6. **Debrief**: Structured decision meeting
7. **Offer**: Competitive, transparent

### Interview Scorecard

**Template**: [hiring-scorecard.md](../templates/hiring-scorecard.md)

| Dimension | What to Assess |
|-----------|----------------|
| **Technical** | Problem-solving, code quality, system thinking |
| **Communication** | Clarity, listening, documentation |
| **Collaboration** | Teamwork, conflict resolution, feedback |
| **Growth** | Learning orientation, self-awareness |
| **Values fit** | Alignment with engineering principles |

### Scoring
- 1: Strong no hire
- 2: No hire
- 3: Lean no
- 4: Lean yes
- 5: Hire
- 6: Strong hire

**Decision rule**: Any 1 or 2 is a veto. Average < 4 is no hire.

---

## Onboarding

**Template**: [onboarding-30-days.md](../templates/onboarding-30-days.md)

### Week 1: Setup
- [ ] Accounts and access provisioned
- [ ] Dev environment working
- [ ] Onboarding buddy assigned
- [ ] First 1:1 with manager

### Week 2: Context
- [ ] Architecture overview session
- [ ] Team mission and current priorities
- [ ] Key stakeholder introductions
- [ ] First small task completed

### Week 3-4: Contribution
- [ ] First PR merged
- [ ] Shadow on-call rotation
- [ ] Attend team ceremonies
- [ ] 30-day check-in with manager

### Success Metrics
- Time to first PR: < 1 week
- Time to first feature: < 4 weeks
- 30-day sentiment: Positive

---

## Performance Management

### Feedback Cadence

| Type | Frequency | Purpose |
|------|-----------|---------|
| 1:1 | Weekly | Coaching, blockers, alignment |
| Skip-level | Monthly | Career, concerns, culture |
| Written review | Semi-annual | Formal assessment, calibration |
| 360 feedback | Annual | Peer perspectives |

### Performance Conversations
- **High performer**: Growth opportunities, retention
- **Solid performer**: Clear path to next level
- **Underperformer**: Clear expectations, support, timeline

---

## Checklist

- [ ] Team structure documented with clear missions
- [ ] Span of control within guidelines
- [ ] Job levels defined
- [ ] Interview process standardized
- [ ] Scorecard used for all hires
- [ ] Onboarding checklist exists
- [ ] Feedback cadences established

---

## Output

After implementing this framework:
- Teams structured for autonomy and delivery
- Hiring decisions consistent and defensible
- New hires productive faster
- Performance expectations clear
