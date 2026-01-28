# Operating Rhythm

## Purpose

Define recurring cadences that keep engineering organizations aligned and accountable.

## When to Use

- Establishing cadences for a new team or organization
- Auditing existing meeting load for effectiveness
- Onboarding leaders to your operating model

---

## Cadence Overview

| Cadence | Frequency | Duration | Attendees | Purpose |
|---------|-----------|----------|-----------|---------|
| Daily standup | Daily | 15 min max | Team (5-8 people) | Coordination, blockers |
| Weekly exec review | Weekly | 60 min | Leadership (5-7 people) | Status, decisions, escalations |
| Team 1:1s | Weekly | 30 min | Manager + report | Coaching, feedback |
| Monthly tech governance | Monthly | 90 min max | Tech leads + leadership (8-12 people) | Architecture, standards, debt |
| Quarterly planning | Quarterly | Half-day | All eng leadership | OKRs, roadmap, resource allocation |
| Incident review | Within 5 days of SEV1/2 | 60 min | Involved parties | Postmortem review |

---

## Weekly Executive Review

**Template**: [weekly-exec-review.md](../templates/weekly-exec-review.md)

### Agenda (60 minutes)
1. **Metrics snapshot** (5 min) - SLO status, velocity, incidents
2. **Blockers and escalations** (15 min) - Cross-team dependencies, resource conflicts
3. **Key decisions needed** (20 min) - Decision memos requiring approval
4. **Updates by area** (15 min) - Round-robin, exceptions only
5. **Action items** (5 min) - Capture and assign

### Rules
- No status updates that could be async (use written updates)
- Decisions require a written memo (no "let's discuss and decide")
- Blockers must have a proposed resolution

---

## Monthly Tech Governance

**Template**: [monthly-tech-governance.md](../templates/monthly-tech-governance.md)

### Agenda (90 minutes)
1. **SLO review** (15 min) - Services below target, error budget status
2. **Security posture** (15 min) - Open vulnerabilities, exception status
3. **Technical debt** (20 min) - Debt register review, prioritization
4. **Architecture decisions** (30 min) - Review pending ADRs/decision memos
5. **Standards updates** (10 min) - Tooling, libraries, patterns

### Inputs Required
- SLO dashboard export
- Security scan summary
- Updated debt register
- Pending decision memos

---

## Quarterly Planning

**Template**: [quarterly-planning.md](../templates/quarterly-planning.md)

### Process (2-4 hours)

#### Pre-work (1 week before)
- Teams submit proposals and capacity estimates
- Leadership reviews and identifies conflicts
- Draft OKRs circulated for feedback

#### Planning Session
1. **Review previous quarter** (30 min) - OKR scoring, lessons learned
2. **Company priorities** (15 min) - Top-down context
3. **Team proposals** (60 min) - Bottom-up needs
4. **Negotiate and prioritize** (45 min) - Resolve conflicts
5. **Finalize OKRs** (30 min) - Commit to outcomes

### Outputs
- Finalized OKRs with owners
- Resource allocation decisions
- Key dependencies documented
- Risk register updated

---

## Meeting Hygiene

### Every Meeting Must Have
- [ ] Written agenda sent 24h in advance
- [ ] Clear owner responsible for outcomes
- [ ] Defined attendees (required vs. optional)
- [ ] Time-boxed sections
- [ ] Action items captured with owners and dates

### Meeting Load Targets
| Role | Max recurring meetings/week |
|------|----------------------------|
| IC Engineer | 4 hours |
| Tech Lead | 8 hours |
| Engineering Manager | 12 hours |
| Director+ | 15 hours |

If exceeding these, audit meeting value ruthlessly.

---

## Async Communication

Not everything needs a meeting.

| Use Meeting For | Use Async For |
|-----------------|---------------|
| Decisions requiring debate | Status updates |
| Sensitive feedback | Information sharing |
| Complex problem-solving | FYI announcements |
| Relationship building | Documentation review |

### Async Tools
- **Status updates**: Weekly written update, Slack channel
- **Decisions**: Decision memo + comment period
- **Documentation**: PR-based review

---

## Checklist

- [ ] Weekly exec review scheduled and templated
- [ ] Monthly tech governance on calendar
- [ ] Quarterly planning dates set for the year
- [ ] Meeting hygiene rules documented and shared
- [ ] Async channels established

---

## Output

After implementing this rhythm:
- Predictable decision-making cadence
- Reduced ad-hoc meetings
- Clear escalation paths
- Documented decisions and outcomes
