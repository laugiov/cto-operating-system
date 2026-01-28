# Postmortem: <INCIDENT TITLE>

**SLA**: Draft within 48h of resolution. Final within 5 business days.

## Metadata

| Field | Value |
|-------|-------|
| **Incident ID** | INC-<NUMBER> |
| **Date** | <YYYY-MM-DD> |
| **Severity** | SEV1 / SEV2 / SEV3 |
| **Duration** | <X hours Y minutes> |
| **MTTR Target** | SEV1: 4h, SEV2: 24h, SEV3: 72h |
| **Author** | <NAME> |
| **Status** | Draft / In Review / Final |

---

## Summary

<5 sentences maximum. What happened, what was the impact, how was it resolved.>

---

## Impact

| Metric | Value |
|--------|-------|
| **Users affected** | <Number or percentage> |
| **Duration** | <Start time> to <End time> (<Total duration>) |
| **Revenue impact** | <$X or "None measurable"> |
| **Data loss** | <Yes/No, details if yes> |
| **SLO impact** | <X% error budget consumed> |

### User Experience
<What did users see? Error messages, degraded performance, complete outage?>

---

## Timeline

All times in UTC (or specify timezone).

| Time | Event |
|------|-------|
| <HH:MM> | <First sign of issue - how detected> |
| <HH:MM> | <Alert fired / customer report> |
| <HH:MM> | <Incident declared, IC assigned> |
| <HH:MM> | <Key investigation step> |
| <HH:MM> | <Root cause identified> |
| <HH:MM> | <Mitigation applied> |
| <HH:MM> | <Service restored> |
| <HH:MM> | <All-clear declared> |

---

## Root Cause Analysis

### What Happened
<Technical description of the failure. Be specific.>

### Why It Happened
<Use 5 Whys or similar technique>

1. **Why?** <First level>
2. **Why?** <Second level>
3. **Why?** <Third level>
4. **Why?** <Fourth level>
5. **Why?** <Root cause>

### Contributing Factors
- <Factor 1: e.g., missing monitoring>
- <Factor 2: e.g., recent change>
- <Factor 3: e.g., documentation gap>

---

## What Went Well

- <Thing that worked as expected>
- <Quick detection or response>
- <Effective team coordination>
- <Runbook that helped>

---

## What Could Be Improved

- <Detection gap>
- <Response delay>
- <Communication issue>
- <Missing runbook or documentation>

---

## Action Items

| ID | Action | Owner | Priority | Due Date | Status |
|----|--------|-------|----------|----------|--------|
| 1 | <Specific action to prevent recurrence> | <Name> | P1/P2/P3 | <Date> | Open |
| 2 | <Improve detection> | <Name> | P1/P2/P3 | <Date> | Open |
| 3 | <Update runbook> | <Name> | P1/P2/P3 | <Date> | Open |
| 4 | <Add monitoring> | <Name> | P1/P2/P3 | <Date> | Open |

### Action Item Criteria
- **P1**: Must complete within 7 days
- **P2**: Must complete within 30 days
- **P3**: Complete within 90 days or add to backlog

---

## Lessons Learned

<What should the organization remember from this incident?>

1. <Lesson 1>
2. <Lesson 2>
3. <Lesson 3>

---

## Appendix

### Related Incidents
- <Link to similar past incidents>

### Supporting Data
- <Link to dashboard during incident>
- <Link to logs>
- <Link to incident channel archive>

---

## Blameless Reminder

This postmortem focuses on systems, not individuals. Everyone involved acted rationally with the information available at the time. The goal is organizational learning, not assigning blame.
