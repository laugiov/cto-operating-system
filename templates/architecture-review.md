# Architecture Review

**Response SLA**: Initial feedback within 48 hours. Full review within 5 business days.

## Metadata

| Field | Value |
|-------|-------|
| **Review ID** | AR-<NUMBER> |
| **System/Feature** | <Name> |
| **Author** | <Name> |
| **Date** | <YYYY-MM-DD> |
| **Status** | Draft / In Review / Approved / Needs Revision |

---

## Overview

### What is being built?
<2-3 sentences describing the system or feature>

### Why is it being built?
<Business or technical driver>

### Scope
- [ ] New system
- [ ] Major change to existing system
- [ ] Integration with external system
- [ ] Other: <specify>

---

## Context Diagram

```
<ASCII diagram or link to diagram showing system in context>

Example:
┌─────────┐     ┌─────────────┐     ┌──────────┐
│  Users  │────▶│  New System │────▶│ Database │
└─────────┘     └─────────────┘     └──────────┘
                      │
                      ▼
               ┌─────────────┐
               │ External API│
               └─────────────┘
```

---

## Requirements

### Functional Requirements
1. <Requirement 1>
2. <Requirement 2>
3. <Requirement 3>

### Non-Functional Requirements

| Requirement | Target | Rationale |
|-------------|--------|-----------|
| Availability | <99.X%> | <Why> |
| Latency p99 | <Xms> | <Why> |
| Throughput | <X rps> | <Why> |
| Data retention | <X days/months> | <Why> |

---

## Proposed Architecture

### Components

| Component | Purpose | Technology | Owner |
|-----------|---------|------------|-------|
| <Component 1> | <What it does> | <Tech stack> | <Team> |
| <Component 2> | <What it does> | <Tech stack> | <Team> |

### Data Flow
<Describe how data moves through the system>

### Storage
| Data | Store | Rationale |
|------|-------|-----------|
| <Data type 1> | <Database/cache> | <Why this choice> |
| <Data type 2> | <Database/cache> | <Why this choice> |

---

## Alternatives Considered

| Option | Pros | Cons | Why Not Chosen |
|--------|------|------|----------------|
| <Option 1> | <Pros> | <Cons> | <Reason> |
| <Option 2> | <Pros> | <Cons> | <Reason> |

---

## Review Checklist

### Reliability
- [ ] SLOs defined for this system
- [ ] Failure modes identified
- [ ] Graceful degradation designed
- [ ] Monitoring and alerting planned
- [ ] Runbooks will be created

### Scalability
- [ ] Load estimates documented
- [ ] Bottlenecks identified
- [ ] Scaling strategy defined (horizontal/vertical)
- [ ] Capacity planning done

### Security
- [ ] Threat model completed (or not required because: <reason>)
- [ ] Authentication mechanism defined
- [ ] Authorization model documented
- [ ] Data encryption (at rest and in transit)
- [ ] Audit logging planned
- [ ] Security review scheduled: <date>

---

## Trust Boundaries

Identify where trust changes in the system:

| Boundary | From | To | Controls |
|----------|------|-----|----------|
| <Boundary 1> | <Trusted zone> | <Untrusted zone> | <What validates/protects> |
| <Boundary 2> | <Trusted zone> | <Untrusted zone> | <What validates/protects> |

### Key Questions
- [ ] Where does untrusted input enter the system?
- [ ] Where are privilege boundaries (user → admin, service → service)?
- [ ] Are there multi-tenant boundaries? How is isolation enforced?
- [ ] What happens if a downstream dependency is compromised?

---

## Security Requirements

### Mandatory Gates

| Condition | Requirement |
|-----------|-------------|
| Internet-facing | Threat model required |
| Handles PII or sensitive data | Data classification + encryption required |
| Admin/privileged operations | Audit logging mandatory |
| Authentication changes | Security review required |
| Cross-tenant access | Isolation proof required |

### Security Controls Checklist
- [ ] Secrets management (no hardcoded credentials)
- [ ] Input validation at all entry points
- [ ] Output encoding (prevent injection)
- [ ] Rate limiting on public endpoints
- [ ] Least privilege for service accounts
- [ ] Break-glass procedure documented

---

## Abuse and Misuse Cases

Document at least 3 potential abuse scenarios:

| Scenario | Attack Vector | Impact | Mitigation |
|----------|---------------|--------|------------|
| <Abuse case 1> | <How attacker exploits> | <What damage> | <Prevention> |
| <Abuse case 2> | <How attacker exploits> | <What damage> | <Prevention> |
| <Abuse case 3> | <How attacker exploits> | <What damage> | <Prevention> |

**Common scenarios to consider**:
- Credential stuffing / brute force
- Privilege escalation (horizontal and vertical)
- Data exfiltration
- Denial of service
- Tenant isolation bypass (if multi-tenant)

### Operability
- [ ] Deployment strategy defined
- [ ] Rollback plan documented
- [ ] On-call ownership assigned
- [ ] Dependencies documented

### Data
- [ ] Data model documented
- [ ] Migration strategy (if applicable)
- [ ] Backup and recovery planned
- [ ] Data retention policy defined

---

## Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| <Risk 1> | Low/Med/High | Low/Med/High | <Mitigation> |
| <Risk 2> | Low/Med/High | Low/Med/High | <Mitigation> |

---

## Dependencies

| Dependency | Type | Risk | Plan |
|------------|------|------|------|
| <Dependency 1> | Team / External / Tech | Low/Med/High | <How to manage> |
| <Dependency 2> | Team / External / Tech | Low/Med/High | <How to manage> |

---

## Open Questions

| Question | Owner | Due Date | Resolution |
|----------|-------|----------|------------|
| <Question 1> | <Name> | <Date> | <Pending/Resolved: answer> |
| <Question 2> | <Name> | <Date> | <Pending/Resolved: answer> |

---

## Approval Criteria

### Approval Blocked If

The review **cannot be approved** if any of the following are true:

- [ ] No SLOs defined for user-facing functionality
- [ ] Threat model required but not completed
- [ ] No rollback plan documented
- [ ] Audit logging missing for sensitive operations
- [ ] No on-call ownership assigned
- [ ] Open critical/high security findings
- [ ] Data retention policy undefined for PII

### Conditional Approval

May be approved with conditions if:
- Medium-priority items have documented remediation timeline
- Missing documentation has committed delivery date
- Non-blocking risks are accepted with mitigation plan

---

## Review Sign-off

| Reviewer | Role | Decision | Date |
|----------|------|----------|------|
| <Name> | Architecture | Approved / Conditional / Blocked | <Date> |
| <Name> | Security | Approved / Conditional / Blocked | <Date> |
| <Name> | Platform | Approved / Conditional / Blocked | <Date> |

### Conditions (if conditional approval)
- <Condition 1 with due date>
- <Condition 2 with due date>

### Blocking Issues (if blocked)
- <Issue that must be resolved>
