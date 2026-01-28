# Postmortem: Payment Service Outage

> Anonymized example.

## Metadata

| Field | Value |
|-------|-------|
| **Incident ID** | INC-001 |
| **Date** | 2024-03-15 |
| **Severity** | SEV1 |
| **Duration** | 55 minutes |
| **Author** | Sarah Chen |
| **Status** | Final |

---

## Summary

On March 15, 2024, a configuration error in deployment version 2.4.1 reduced the payment service's database connection pool from 50 to 5 connections. Under normal load (~200 requests/second), the service immediately exhausted connections and returned errors for all payment requests. The issue was detected by monitoring within 2 minutes, but it took 32 minutes to identify the root cause due to initial focus on database health rather than application configuration. Service was restored via rollback.

---

## Impact

| Metric | Value |
|--------|-------|
| **Users affected** | 2,100 unique users |
| **Duration** | 14:15 - 14:55 UTC (40 minutes of user impact) |
| **Failed transactions** | 3,200 |
| **Revenue impact** | $48,000 estimated (abandoned carts) |
| **Data loss** | None |
| **SLO impact** | 2.3% of monthly error budget consumed |

### User Experience
Users attempting checkout saw "Unable to process payment. Please try again." Cart contents were preserved. Retry after resolution succeeded.

---

## Timeline

All times UTC.

| Time | Event |
|------|-------|
| 14:10 | Deployment of version 2.4.1 initiated by CI/CD |
| 14:12 | Deployment completed, canary (5% traffic) healthy |
| 14:13 | Canary promoted to 100% traffic |
| 14:15 | First 503 errors appear in monitoring |
| 14:17 | PagerDuty alert fires for payment_error_rate > 5% |
| 14:19 | On-call engineer (Mike) acknowledges alert |
| 14:21 | Mike checks database - appears healthy |
| 14:23 | Sarah joins, declares SEV1, opens incident channel |
| 14:25 | Alex joins to investigate recent deployment |
| 14:28 | Team confirms issue started after deployment |
| 14:30 | Rollback proposed but team wants to understand root cause first |
| 14:35 | Database team confirms no issues on their end |
| 14:40 | Alex notices connection pool config change in diff |
| 14:42 | Connection pool confirmed as root cause |
| 14:44 | Decision to rollback immediately |
| 14:47 | Rollback initiated |
| 14:52 | Rollback completed, success rate recovering |
| 15:05 | Success rate at 99%, latency normalizing |
| 15:18 | Stable for 15 minutes, incident closed |

---

## Root Cause Analysis

### What Happened
Version 2.4.1 included a change to the payment service configuration file that set `db_pool_size: 5` instead of the previous `db_pool_size: 50`. Under the service's normal load of ~200 requests/second with average query time of 50ms, 5 connections can handle approximately 100 requests/second. The remaining requests queued, timed out, and returned 503 errors.

### Why It Happened (5 Whys)

1. **Why did the service fail?**
   Database connection pool exhausted under normal load.

2. **Why was the connection pool too small?**
   Configuration was changed from 50 to 5 in version 2.4.1.

3. **Why was the configuration changed?**
   Developer was testing locally with a smaller pool and accidentally committed the change.

4. **Why wasn't this caught in code review?**
   The config change was in a large PR (847 lines). Reviewers focused on the main feature code and didn't notice the config file change.

5. **Why didn't staging catch this?**
   Staging traffic is ~10 requests/second, which 5 connections can handle. The issue only manifests at production traffic levels.

### Contributing Factors
- Large PR size made review less effective
- Config files not flagged for extra review attention
- Staging environment doesn't represent production load
- No automated validation of critical config values

---

## What Went Well

- **Detection was fast**: Monitoring alerted within 2 minutes of first errors
- **Team assembled quickly**: SEV1 response had 3 engineers within 10 minutes
- **Rollback was clean**: Version 2.4.0 was stable and rollback was straightforward
- **Customer communication was timely**: Status page updated within 15 minutes
- **No data loss**: Failed transactions could be retried successfully

---

## What Could Be Improved

- **Root cause identification took too long**: 25 minutes from incident start to root cause
- **Initial debugging focused on wrong area**: Assumed database issue, not config issue
- **Rollback delayed**: Team wanted to understand before rolling back, costing ~15 minutes
- **Staging doesn't catch load-related issues**: Known gap that we haven't addressed
- **Config changes not highlighted**: Easy to miss in large PRs

---

## Action Items

| ID | Action | Owner | Priority | Due Date | Status |
|----|--------|-------|----------|----------|--------|
| 1 | Add CI check for critical config values (connection pool, timeouts) | Alex | P1 | 2024-03-22 | Open |
| 2 | Require explicit approval for config file changes in PRs | Mike | P1 | 2024-03-25 | Open |
| 3 | Add runbook: "Check recent deployments first" for service errors | Sarah | P2 | 2024-03-29 | Open |
| 4 | Implement load testing in staging pipeline | Platform | P2 | 2024-04-15 | Open |
| 5 | Update rollback policy: roll back first if deployment-correlated | Sarah | P2 | 2024-03-22 | Open |
| 6 | Add config diff to deployment notifications | Platform | P3 | 2024-04-30 | Open |

---

## Lessons Learned

1. **Rollback first, debug second**: When an issue correlates with a deployment, rollback should be the default action. Debugging can happen after service is restored.

2. **Config is code, but riskier**: Configuration changes can have outsized impact. They deserve extra review attention and automated validation.

3. **Staging must approximate production**: Load-dependent bugs will escape if staging traffic is 100x lower than production.

4. **Large PRs hide problems**: The config change was in an 847-line PR. Smaller, focused PRs would have made this visible.

---

## Appendix

### Related Incidents
- None directly related

### Supporting Data
- [Monitoring dashboard during incident](#)
- [Deployment log for 2.4.1](#)
- [PR #1847 containing the config change](#)
- [Incident Slack channel archive](#)

---

## Blameless Reminder

This postmortem focuses on systems, not individuals. The developer who committed the config change was working in good faith. Our systems should have caught this before production. The action items focus on improving those systems.
