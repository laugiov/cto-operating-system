# Security-by-Design Leadership

How to embed security into engineering culture - not as a gate, but as a default.

**Use this when:**

- Building security practices for a growing organization
- Shifting security left in the development lifecycle
- Establishing security governance without bureaucracy
- Training engineering teams on security responsibilities

---

## Core Principle

Security is not a team. Security is a property of the system that everyone owns.

The security team enables, educates, and audits. Engineering teams build secure systems.

---

## Security Integration Points

| Phase | Security Activity | Who |
|-------|-------------------|-----|
| **Design** | Threat modeling, security review | Engineering + Security |
| **Build** | Secure coding, dependency scanning | Engineering |
| **Review** | Security-focused code review | Engineering + Security |
| **Test** | Security testing, pen testing | Engineering + Security |
| **Deploy** | Configuration review, secrets management | Platform + Security |
| **Operate** | Monitoring, incident response | SRE + Security |

---

## Threat Modeling

### When to Threat Model
- New service or major feature
- Integration with external systems
- Changes to authentication/authorization
- Handling of sensitive data

### STRIDE Framework

| Threat | Question | Mitigation Example |
|--------|----------|-------------------|
| **S**poofing | Can someone pretend to be another user? | Strong authentication |
| **T**ampering | Can data be modified in transit/storage? | Integrity checks, signatures |
| **R**epudiation | Can actions be denied later? | Audit logging |
| **I**nformation disclosure | Can sensitive data leak? | Encryption, access controls |
| **D**enial of service | Can the service be overwhelmed? | Rate limiting, scaling |
| **E**levation of privilege | Can users gain unauthorized access? | Least privilege, authorization |

### Threat Model Output
Document in architecture review or security review template:
- Assets (what are we protecting?)
- Threats (what could go wrong?)
- Mitigations (how do we prevent it?)
- Residual risk (what's accepted?)

---

## Security Reviews

**Template**: [security-review.md](../templates/security-review.md)

### When Required
- [ ] New external-facing service
- [ ] Authentication/authorization changes
- [ ] Sensitive data handling
- [ ] Third-party integrations
- [ ] Infrastructure changes

### Review Process
1. Engineering submits design doc or architecture review
2. Security team reviews within SLA (5 business days)
3. Findings categorized (critical, high, medium, low)
4. Critical/high must be addressed before launch
5. Medium/low tracked in backlog with timeline

### Review SLAs

| Finding Severity | Resolution Timeline |
|------------------|---------------------|
| Critical | Before launch, no exceptions |
| High | Before launch or explicit risk acceptance |
| Medium | Within 30 days of launch |
| Low | Within 90 days or accepted |

---

## Risk Acceptance

**Template**: [risk-acceptance.md](../templates/risk-acceptance.md)

### When to Use
- Security finding cannot be addressed before deadline
- Mitigation cost exceeds risk value
- Temporary exception needed

### Risk Acceptance Requirements
- [ ] Risk clearly described
- [ ] Business justification documented
- [ ] Compensating controls identified
- [ ] Expiration date set (max 90 days)
- [ ] Owner assigned
- [ ] Approval at appropriate level (Director+ for High)

### Approval Authority

| Risk Level | Approver |
|------------|----------|
| Critical | CTO or CISO |
| High | VP Engineering or Security Lead |
| Medium | Director or Security Team |
| Low | Engineering Manager |

---

## Exception Requests

**Template**: [exception-request.md](../templates/exception-request.md)

Exceptions to security policies (not the same as risk acceptance).

### Common Exception Types
- Deprecated library extension
- Non-standard authentication method
- Data retention policy exception
- Network access exception

### Exception Requirements
- [ ] Policy being excepted clearly stated
- [ ] Reason exception is needed
- [ ] Duration (max 6 months)
- [ ] Review date scheduled
- [ ] Compensating controls

---

## Security Metrics

### What to Measure

| Metric | Target | Why |
|--------|--------|-----|
| Time to remediate critical vulns | < 7 days | Speed of response |
| Open high/critical findings | < 5 | Risk posture |
| Security review coverage | 100% of required | Process compliance |
| Mean time to detect (MTTD) | Decreasing | Detection capability |
| Security training completion | 100% | Awareness |

### What Not to Measure
- Number of vulnerabilities found (incentivizes hiding, not fixing)
- Security team headcount ratio (security is everyone's job)

---

## Security Culture

### Engineering Responsibilities
- Complete security training annually
- Follow secure coding guidelines
- Raise security concerns early
- Participate in incident response when needed

### Security Team Responsibilities
- Enable, don't block
- Provide clear guidance and tooling
- Review within SLA
- Educate, don't shame

### Leadership Responsibilities
- Allocate time for security work (15-20% of reliability budget)
- Make security a promotion criterion
- Celebrate security improvements
- Attend security reviews for critical systems

---

## Checklist

- [ ] Threat modeling required for new services
- [ ] Security review process defined with SLAs
- [ ] Risk acceptance process documented
- [ ] Exception request process documented
- [ ] Security metrics tracked and reviewed
- [ ] Security training program established
- [ ] Incident response includes security team

---

## Output

After implementing this framework:
- Security integrated into development lifecycle
- Clear process for security reviews and exceptions
- Risk-based decision making (not security theater)
- Engineering teams own security outcomes
