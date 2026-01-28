# Incident Management

How to detect, respond to, and learn from incidents.

**Use this when:**
- Defining incident response process
- Training new on-call engineers
- Improving incident management
- Writing postmortems

---

## Incident Lifecycle

```
Detection → Triage → Response → Resolution → Postmortem → Prevention
```

---

## Severity Levels

| Severity | Definition | Response Time | MTTR Target | Communication |
|----------|------------|---------------|-------------|---------------|
| **SEV1** | Complete outage, revenue impact, data loss risk | Immediate | 4 hours | Exec + all-hands |
| **SEV2** | Major degradation, significant user impact | < 15 min | 24 hours | Leadership + affected teams |
| **SEV3** | Minor degradation, limited user impact | < 1 hour | 72 hours | Team + stakeholders |
| **SEV4** | No user impact, internal issue | Next business day | 1 week | Team only |

### Severity Decision Tree
1. Is revenue directly impacted? → SEV1
2. Are >10% of users affected? → SEV1-2
3. Is a critical workflow broken? → SEV2
4. Is there workaround available? → SEV3
5. No user impact? → SEV4

---

## Incident Roles

| Role | Responsibility | Who |
|------|----------------|-----|
| **Incident Commander (IC)** | Coordinates response, makes decisions | On-call lead or escalation |
| **Technical Lead** | Drives investigation and fix | Subject matter expert |
| **Communications Lead** | Updates stakeholders, customers | PM, support, or designated engineer |
| **Scribe** | Documents timeline, actions, decisions | Any available team member |

### Incident Commander Responsibilities
- [ ] Declare incident severity
- [ ] Assign roles
- [ ] Run incident channel/bridge
- [ ] Make time-critical decisions
- [ ] Escalate when needed
- [ ] Declare resolution

---

## Response Process

### Phase 1: Detection (< 5 minutes)
- [ ] Alert received and acknowledged
- [ ] Initial assessment of impact
- [ ] Incident channel created (e.g., #inc-YYYYMMDD-brief-description)
- [ ] Incident Commander identified

### Phase 2: Triage (5-15 minutes)
- [ ] Severity determined
- [ ] Roles assigned
- [ ] Initial hypothesis formed
- [ ] First stakeholder notification sent
- [ ] War room/bridge established if SEV1-2

### Phase 3: Response (ongoing)
- [ ] Systematic investigation (check dashboards, logs, recent changes)
- [ ] Updates posted every 15-30 minutes
- [ ] Mitigation attempted (rollback, failover, feature flag)
- [ ] Customer communication drafted if needed
- [ ] Escalation if no progress after 30 minutes

### Phase 4: Resolution
- [ ] Service restored to normal operation
- [ ] Verification with monitoring and user reports
- [ ] All-clear communication sent
- [ ] Incident channel archived (not deleted)
- [ ] Postmortem scheduled within 48 hours

---

## Communication Templates

### Internal Update
**Template**: [incident-comms-internal.md](../templates/incident-comms-internal.md)

```
[SEVERITY] - [Service] - [Status]
Impact: [Who is affected, what is broken]
Current action: [What we're doing now]
ETA: [When we expect resolution or next update]
```

### Executive Update
**Template**: [incident-comms-exec.md](../templates/incident-comms-exec.md)

Focus on: Business impact, customer communication status, timeline.

---

## Postmortem Process

**Template**: [postmortem.md](../templates/postmortem.md)

### Timeline
- **48 hours**: Draft postmortem written
- **1 week**: Postmortem review meeting held
- **2 weeks**: Action items assigned and tracked
- **30 days**: Action items completed (or exceptions documented)

### Blameless Principles
- Focus on systems, not individuals
- "How did the system allow this?" not "Who caused this?"
- All participants acted rationally with available information
- Goal is learning, not punishment

### Required Sections
1. Summary (5 sentences max)
2. Impact (users, revenue, duration)
3. Timeline (minute-by-minute for SEV1-2)
4. Root cause analysis (5 whys or similar)
5. What went well
6. What could be improved
7. Action items with owners and due dates

---

## On-Call Practices

### On-Call Expectations
- [ ] Acknowledge alerts within 5 minutes
- [ ] Laptop and connectivity available during shift
- [ ] Escalation paths documented and accessible
- [ ] Handoff at shift change includes active issues

### On-Call Health
- Rotation: Minimum 1 week between shifts
- Compensation: Time off or pay for after-hours pages
- Load: If averaging >2 pages/night, fix the alerts or staff up
- Review: Monthly review of on-call burden by team

---

## Checklist

- [ ] Severity definitions documented and communicated
- [ ] On-call rotation established
- [ ] Incident communication templates ready
- [ ] Postmortem process defined
- [ ] Escalation paths documented
- [ ] Incident tooling in place (channel creation, paging)

---

## Output

After implementing this framework:
- Consistent, predictable incident response
- Reduced mean time to resolution (MTTR)
- Organizational learning through postmortems
- Sustainable on-call practices
