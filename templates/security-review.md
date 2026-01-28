# Security Review

**Response SLA**: Initial feedback within 72 hours. Full review within 7 business days.

## Metadata

| Field | Value |
|-------|-------|
| **Review ID** | SR-<NUMBER> |
| **System/Feature** | <Name> |
| **Author** | <Name> |
| **Security Reviewer** | <Name> |
| **Date** | <YYYY-MM-DD> |
| **Status** | Draft / In Review / Approved / Blocked |

---

## Review Trigger

Why is this review required?
- [ ] New external-facing service
- [ ] Authentication/authorization changes
- [ ] Sensitive data handling
- [ ] Third-party integration
- [ ] Infrastructure change
- [ ] Requested by team
- [ ] Other: <specify>

---

## System Overview

### Description
<Brief description of what the system does>

### Architecture Diagram
<Link to diagram or embed ASCII diagram>

### Data Classification

| Data Type | Classification | Storage | Encryption |
|-----------|---------------|---------|------------|
| <Data 1> | Public / Internal / Confidential / Restricted | <Where> | Yes / No |
| <Data 2> | Public / Internal / Confidential / Restricted | <Where> | Yes / No |

---

## Threat Model (STRIDE)

### Spoofing
| Threat | Applicable? | Mitigation |
|--------|-------------|------------|
| Impersonate user | Yes / No | <Control> |
| Impersonate service | Yes / No | <Control> |

### Tampering
| Threat | Applicable? | Mitigation |
|--------|-------------|------------|
| Modify data in transit | Yes / No | <Control> |
| Modify data at rest | Yes / No | <Control> |

### Repudiation
| Threat | Applicable? | Mitigation |
|--------|-------------|------------|
| Deny action occurred | Yes / No | <Control> |

### Information Disclosure
| Threat | Applicable? | Mitigation |
|--------|-------------|------------|
| Data leak in logs | Yes / No | <Control> |
| Unauthorized data access | Yes / No | <Control> |
| Data exposed in errors | Yes / No | <Control> |

### Denial of Service
| Threat | Applicable? | Mitigation |
|--------|-------------|------------|
| Resource exhaustion | Yes / No | <Control> |
| Application-level DoS | Yes / No | <Control> |

### Elevation of Privilege
| Threat | Applicable? | Mitigation |
|--------|-------------|------------|
| Horizontal privilege escalation | Yes / No | <Control> |
| Vertical privilege escalation | Yes / No | <Control> |

---

## Security Controls Checklist

### Authentication
- [ ] Authentication method appropriate for use case
- [ ] Credential storage follows standards (hashing, salting)
- [ ] Session management secure (timeout, invalidation)
- [ ] MFA considered for sensitive operations

### Authorization
- [ ] Principle of least privilege applied
- [ ] Authorization checked on every request
- [ ] Role-based access control documented
- [ ] No authorization bypass possible

### Input Validation
- [ ] All inputs validated
- [ ] Parameterized queries (no SQL injection)
- [ ] Output encoding (no XSS)
- [ ] File upload restrictions (if applicable)

### Data Protection
- [ ] Encryption in transit (TLS 1.2+)
- [ ] Encryption at rest (where required)
- [ ] PII handling compliant with policy
- [ ] Data retention policy followed

### Logging and Monitoring
- [ ] Security events logged
- [ ] No sensitive data in logs
- [ ] Alerts for suspicious activity
- [ ] Audit trail for sensitive operations

### Dependencies
- [ ] Third-party libraries reviewed
- [ ] Known vulnerabilities addressed
- [ ] License compliance checked

---

## Findings

### Critical (Must fix before launch)

| ID | Finding | Risk | Recommendation |
|----|---------|------|----------------|
| C1 | <Finding> | <Risk description> | <Fix> |

### High (Must fix before launch or accept risk)

| ID | Finding | Risk | Recommendation |
|----|---------|------|----------------|
| H1 | <Finding> | <Risk description> | <Fix> |

### Medium (Fix within 30 days)

| ID | Finding | Risk | Recommendation |
|----|---------|------|----------------|
| M1 | <Finding> | <Risk description> | <Fix> |

### Low (Fix within 90 days or accept)

| ID | Finding | Risk | Recommendation |
|----|---------|------|----------------|
| L1 | <Finding> | <Risk description> | <Fix> |

### Informational

| ID | Observation | Recommendation |
|----|-------------|----------------|
| I1 | <Observation> | <Suggestion> |

---

## Remediation Tracking

| Finding ID | Status | Owner | Due Date | Notes |
|------------|--------|-------|----------|-------|
| <ID> | Open / In progress / Resolved / Accepted | <Name> | <Date> | <Notes> |

---

## Decision

| Decision | Date | Approver |
|----------|------|----------|
| Approved / Approved with conditions / Blocked | <Date> | <Name> |

### Conditions (if applicable)
- <Condition 1>
- <Condition 2>

---

## Follow-up

- [ ] Remediation verified
- [ ] Post-launch review scheduled: <Date>
- [ ] Added to regular security scan scope
