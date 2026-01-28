# SLOs, SLAs, and Error Budgets

How to define reliability targets and use them to make prioritization decisions.

**Use this when:**
- Defining reliability targets for a new service
- Negotiating SLAs with customers or stakeholders
- Making build vs. fix prioritization decisions
- Justifying reliability investment to leadership

---

## Definitions

| Term | Definition | Audience |
|------|------------|----------|
| **SLI** (Service Level Indicator) | Metric that measures service behavior (e.g., latency p99, error rate) | Engineering |
| **SLO** (Service Level Objective) | Target value for an SLI (e.g., p99 latency < 200ms) | Engineering + Product |
| **SLA** (Service Level Agreement) | Contractual commitment with consequences (e.g., refunds) | Customers |
| **Error Budget** | Allowed unreliability (100% - SLO target) | Engineering |

### Relationship
```
SLI (measurement) → SLO (internal target) → SLA (external commitment)
```

**Rule**: SLO must be stricter than SLA. If SLA is 99.9%, SLO should be 99.95%.

---

## Choosing SLIs

### Common SLI Categories

| Category | Example SLIs | Measurement |
|----------|--------------|-------------|
| **Availability** | Successful requests / total requests | Error rate, HTTP 5xx |
| **Latency** | Response time percentiles | p50, p95, p99 |
| **Throughput** | Requests handled per second | RPS, TPS |
| **Correctness** | Valid outputs / total outputs | Data accuracy rate |
| **Freshness** | Age of data | Replication lag |

### SLI Selection Criteria
- [ ] Measures user-facing behavior (not internal metrics)
- [ ] Can be measured reliably and consistently
- [ ] Team can influence the metric
- [ ] Meaningful to stakeholders

---

## Setting SLO Targets

### Process
1. **Baseline**: Measure current performance (4+ weeks of data)
2. **User research**: What do users actually need?
3. **Business context**: What can we afford to deliver?
4. **Propose target**: Based on baseline + requirements
5. **Review**: Get buy-in from stakeholders
6. **Iterate**: Adjust based on experience

### Target Guidelines

| Service Criticality | Typical Availability SLO |
|--------------------|-------------------------|
| Tier 1 (revenue-critical) | 99.95% - 99.99% |
| Tier 2 (important) | 99.9% - 99.95% |
| Tier 3 (internal tools) | 99% - 99.9% |

### Downtime Reality Check

| SLO | Downtime/month | Downtime/year |
|-----|----------------|---------------|
| 99.99% | 4.3 min | 52 min |
| 99.95% | 22 min | 4.4 hours |
| 99.9% | 43 min | 8.8 hours |
| 99% | 7.2 hours | 3.6 days |

Don't over-promise. 99.99% means you get one 4-minute incident per month.

---

## Error Budgets

### Calculation
```
Error Budget = 100% - SLO Target

Example: 99.9% SLO = 0.1% error budget
         = 43.2 minutes/month of allowed downtime
         = 8.76 hours/year
```

### Using Error Budgets

| Budget Status | Action |
|---------------|--------|
| Budget healthy (> 50% remaining) | Ship features, take risks |
| Budget caution (25-50% remaining) | Slow down, increase review rigor |
| Budget critical (< 25% remaining) | Freeze features, focus on reliability |
| Budget exhausted | Stop all feature work until reliability improves |

### Error Budget Policy

Document in advance what happens when budget is exhausted:
1. Feature freeze for affected service
2. All hands on reliability improvements
3. Postmortem required for any further incidents
4. Leadership review before resuming features

---

## SLO Review Process

### Monthly Review
- [ ] Compare actual vs. target for each SLO
- [ ] Calculate remaining error budget
- [ ] Review incidents that consumed budget
- [ ] Decide on feature vs. reliability balance
- [ ] Adjust SLOs if consistently over/under target

### Quarterly Review
- [ ] Assess if SLOs still reflect user needs
- [ ] Review SLI measurement accuracy
- [ ] Update targets based on business changes
- [ ] Plan reliability investments

---

## SLO Catalog Template

Use [slo-catalog.md](../templates/slo-catalog.md) to document your SLOs.

| Field | Description |
|-------|-------------|
| Service | Service name |
| SLI | What is measured |
| SLO Target | Target value |
| Measurement Window | 30-day rolling, calendar month, etc. |
| Owner | Team responsible |
| Dashboard | Link to monitoring |

---

## Checklist

- [ ] SLIs defined for all Tier 1 services
- [ ] SLO targets set and documented
- [ ] Error budget policy written and communicated
- [ ] Monthly SLO review on calendar
- [ ] Dashboard showing budget consumption

---

## Output

After implementing this framework:
- Objective prioritization criteria for reliability vs. features
- Clear communication with stakeholders about reliability expectations
- Data-driven decisions about where to invest engineering effort
- Reduced conflict about "how reliable is reliable enough"
