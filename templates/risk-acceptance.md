# Risk Acceptance

## Metadata

| Field | Value |
|-------|-------|
| **Risk ID** | RISK-<NUMBER> |
| **Title** | <Brief description of risk> |
| **Status** | Pending / Approved / Expired / Closed |
| **Requested by** | <Name> |
| **Date** | <YYYY-MM-DD> |
| **Expiration** | <YYYY-MM-DD> (max 90 days) |

---

## Risk Description

### What is the risk?
<Clear description of the security or technical risk being accepted>

### How was it identified?
- [ ] Security review
- [ ] Penetration test
- [ ] Vulnerability scan
- [ ] Audit finding
- [ ] Self-identified
- [ ] Other: <specify>

### Affected Systems
- <System 1>
- <System 2>

### Data at Risk
- [ ] PII
- [ ] Financial data
- [ ] Authentication credentials
- [ ] Business confidential
- [ ] None of the above

---

## Risk Assessment

| Factor | Rating | Justification |
|--------|--------|---------------|
| **Likelihood** | Low / Medium / High | <Why this rating> |
| **Impact** | Low / Medium / High | <Why this rating> |
| **Overall Risk** | Low / Medium / High / Critical | Likelihood × Impact |

### Potential Consequences
- <Consequence 1>
- <Consequence 2>
- <Consequence 3>

---

## Business Justification

### Why accept this risk?
<Clear explanation of why remediation is not feasible now>

### Business impact of remediation
- Cost: <$X or effort estimate>
- Timeline: <How long to fix>
- Other impacts: <Business disruption, etc.>

### What changes if we don't accept?
<Deadline missed, feature blocked, etc.>

---

## Compensating Controls

Controls in place to reduce risk while acceptance is active:

| Control | Description | Owner |
|---------|-------------|-------|
| <Control 1> | <What it does> | <Name> |
| <Control 2> | <What it does> | <Name> |
| <Control 3> | <What it does> | <Name> |

---

## Remediation Plan

| Milestone | Description | Target Date | Owner |
|-----------|-------------|-------------|-------|
| <Milestone 1> | <What will be done> | <Date> | <Name> |
| <Milestone 2> | <What will be done> | <Date> | <Name> |
| Final remediation | Risk fully addressed | <Date> | <Name> |

---

## Monitoring

How will we know if risk materializes?

| Indicator | Monitoring Method | Alert Owner |
|-----------|-------------------|-------------|
| <Indicator 1> | <How monitored> | <Name> |
| <Indicator 2> | <How monitored> | <Name> |

---

## Approval

| Role | Name | Decision | Date |
|------|------|----------|------|
| Requestor | <Name> | Requested | <Date> |
| Security | <Name> | Reviewed | <Date> |
| Approver | <Name> | Approved / Denied | <Date> |

### Approval Authority

| Risk Level | Approver |
|------------|----------|
| Critical | CTO or CISO |
| High | VP Engineering or Security Lead |
| Medium | Director or Security Team |
| Low | Engineering Manager |

---

## Review History

| Date | Reviewer | Action | Notes |
|------|----------|--------|-------|
| <Date> | <Name> | Created | Initial submission |
| <Date> | <Name> | Reviewed | <Notes> |
| <Date> | <Name> | Approved | <Notes> |

---

## Closure

### Closure Reason
- [ ] Risk remediated
- [ ] Risk no longer applicable
- [ ] Acceptance expired (must resubmit or remediate)
- [ ] Other: <specify>

### Closure Date
<YYYY-MM-DD>

### Verified By
<Name>
