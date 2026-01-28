# Quarterly Plan Example

> Anonymized example.

## Metadata

| Field | Value |
|-------|-------|
| **Quarter** | Q2 2024 |
| **Planning Date** | 2024-03-25 |
| **Attendees** | Engineering Leadership, Product, Design |
| **Facilitator** | VP Engineering |

---

## Previous Quarter Review (Q1 2024)

### OKR Scorecard

| Objective | Key Result | Target | Actual | Score |
|-----------|------------|--------|--------|-------|
| **Improve checkout conversion** | Reduce checkout abandonment | 25% → 20% | 21% | 0.8 |
| | Checkout load time p99 | 3s → 2s | 2.1s | 0.9 |
| | A/B test new flow | 3 tests | 3 tests | 1.0 |
| **Platform reliability** | SLO compliance | 99.9% | 99.2% | 0.3 |
| | Reduce on-call pages | 4/night → 2/night | 4.2/night | 0.0 |
| | Zero SEV1 incidents | 0 | 3 | 0.0 |
| **Team growth** | Hire 4 engineers | 4 | 3 | 0.75 |
| | Onboarding NPS | 8+ | 8.2 | 1.0 |

**Overall score**: 0.59 (below 0.7 target)

### Lessons Learned
- Feature velocity came at the cost of reliability
- Understaffing contributed to both reliability issues and burnout
- On-call burden unsustainable at current levels

---

## Company Context

### Top Company Priorities for Q2
1. **Partnership launch** - Enterprise partnership going live in Q3 requires feature parity
2. **Platform stability** - Board has flagged reliability concerns
3. **Expansion** - International expansion prep for Q4

### Constraints
- Headcount: 34 engineers (3 new hires joining in April)
- Budget: $50K discretionary (tools, training)
- Key dates: Partnership demo May 15, Feature freeze June 15

---

## Capacity Planning

### Available Capacity

| Team | Engineers | Sprint Days | Capacity (points) |
|------|-----------|-------------|-------------------|
| Checkout | 8 | 52 | 416 |
| Platform | 6 | 52 | 312 |
| Growth | 5 | 52 | 260 |
| Data | 4 | 52 | 208 |
| Security | 3 | 52 | 156 |
| **Total** | 26 | - | 1,352 |

*Note: 8 engineers in management/lead roles not counted in capacity*

### Allocation by Category

| Category | % | Points | Rationale |
|----------|---|--------|-----------|
| Features | 50% | 676 | Reduced from 70% to address reliability |
| Reliability | 25% | 338 | Increased from 15% per error budget policy |
| Platform | 15% | 203 | Continued investment |
| Debt | 10% | 135 | Minimum maintenance |

---

## Q2 OKRs

### Objective 1: Restore Platform Reliability

*Owner: Platform Team*

| Key Result | Baseline | Target | Owner |
|------------|----------|--------|-------|
| SLO compliance (30-day) | 99.2% | 99.9% | Platform |
| On-call pages per night | 4.2 | 2.0 | Platform |
| SEV1/SEV2 incidents | 3/quarter | ≤1 | All teams |
| Error budget remaining | 0% | >50% | Platform |

**Initiatives**:
- Connection pool optimization across services - 50 points
- Alert tuning and runbook improvements - 40 points
- Automated canary analysis - 80 points
- Database query optimization - 60 points

### Objective 2: Deliver Partnership Features

*Owner: Checkout + Growth Teams*

| Key Result | Baseline | Target | Owner |
|------------|----------|--------|-------|
| Partner feature parity | 0/8 features | 8/8 features | Checkout |
| Partner demo successful | N/A | May 15 | Checkout |
| Integration test coverage | 0% | 90% | Growth |

**Initiatives**:
- Bulk order processing - 120 points
- Custom invoicing - 80 points
- SSO integration - 60 points
- API rate limiting - 40 points
- Partner dashboard - 100 points
- Webhook reliability - 50 points

### Objective 3: Strengthen Security Posture

*Owner: Security Team*

| Key Result | Baseline | Target | Owner |
|------------|----------|--------|-------|
| Critical vulnerabilities | 5 open | 0 open | Security |
| SOC2 audit readiness | 60% | 100% | Security |
| Secrets in code | ~50 | 0 | Security |
| Security review coverage | 30% | 80% | Security |

**Initiatives**:
- Vault implementation - 80 points
- CI/CD security scanning - 40 points
- SOC2 evidence collection - 60 points

---

## Dependencies

| Dependency | From | To | Risk | Mitigation |
|------------|------|-----|------|------------|
| SSO integration requires IdP setup | Checkout | Partner IT | High | Early engagement, fallback to SAML |
| Vault requires infra changes | Security | Platform | Medium | Joint planning session scheduled |
| Partner API specs | Checkout | Partner | Medium | Draft specs available, weekly syncs |

---

## Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| April hires onboard slower than expected | Medium | Medium | Assign dedicated buddies, reduce Q2 expectations |
| Partnership scope creep | High | High | Strict change control, CTO escalation path |
| Reliability work uncovers more issues | Medium | Medium | Buffer capacity, prioritization framework ready |
| Key engineer departure | Low | High | Documentation push, cross-training |

---

## Not Doing This Quarter

| Item | Reason | When Revisit |
|------|--------|--------------|
| Mobile app v2 | Reliability takes priority | Q3 |
| International payment methods | Partnership features first | Q4 |
| ML-based recommendations | Not aligned with Q2 priorities | Q3 |
| Design system overhaul | Not blocking any priority | Q3-Q4 |

---

## Success Criteria

At the end of Q2, we will consider the quarter successful if:

1. **Reliability restored**: SLO ≥99.9% for final 30 days of quarter
2. **Partnership on track**: Successful demo May 15, feature complete June 15
3. **Security baseline**: SOC2 ready, zero critical vulnerabilities
4. **Team healthy**: On-call burden ≤2 pages/night, no attrition due to burnout

---

## Communication Plan

| Audience | What | When | Owner |
|----------|------|------|-------|
| Engineering all-hands | Q2 plan overview | March 28 | VP Eng |
| Product team | Roadmap alignment | March 27 | Product + Eng |
| Board | Reliability improvement plan | April board meeting | CTO |
| Partner | Feature timeline | March 30 | CPO |

---

## Review Schedule

| Review | Date | Focus |
|--------|------|-------|
| Month 1 check-in | April 26 | Partnership progress, reliability trend |
| Mid-quarter | May 17 | Post-demo review, adjust if needed |
| Month 2 check-in | May 31 | Feature freeze readiness |
| Quarter close | June 28 | OKR scoring, Q3 planning input |

---

## Approvals

| Role | Name | Approved |
|------|------|----------|
| VP Engineering | [Name] | Yes |
| CPO | [Name] | Yes |
| CTO | [Name] | Yes |
