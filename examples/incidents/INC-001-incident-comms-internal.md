# Internal Incident Communications - INC-001

> Anonymized example.

## Payment Processing Outage

---

### Initial Declaration (14:23 UTC)

```
[SEV1] PAYMENT SERVICE - Complete outage

Status: Investigating
Impact: All checkout transactions failing. ~2,000 users affected since 14:15.
IC: Sarah Chen
Channel: #inc-20240315-payments

We are aware of the issue and investigating. Updates every 15 minutes.
```

---

### Update 1 (14:38 UTC)

```
[SEV1] PAYMENT SERVICE - UPDATE 1

Status: Investigating
Time in incident: 23 minutes

Current situation:
Payment service returning 503 errors on all endpoints. Database connections healthy.
Service was restarted at 14:20, no improvement.

What we know:
- Deployment at 14:10 (version 2.4.1) preceded the issue
- Rollback in progress
- No database issues detected
- External payment provider (Stripe) reports no issues

Current actions:
- Rollback to 2.4.0 - @mike (ETA 14:45)
- Reviewing 2.4.1 changes - @alex
- Monitoring dashboards - @sarah

Next update: 14:53 or when status changes
```

---

### Update 2 (14:47 UTC)

```
[SEV1] PAYMENT SERVICE - UPDATE 2

Status: Identified
Time in incident: 32 minutes

Root cause identified:
Version 2.4.1 introduced a configuration change that reduced connection pool
size from 50 to 5. Under normal load, service exhausts connections and fails.

Rollback completing now.

Current actions:
- Rollback completing - @mike
- Preparing customer communication - @priya

Next update: 15:00 or when rollback complete
```

---

### Update 3 - Mitigation (14:52 UTC)

```
[SEV1] PAYMENT SERVICE - MITIGATION APPLIED

Status: Monitoring
Time in incident: 37 minutes

Mitigation: Rolled back to version 2.4.0

Payment service responding normally. Success rate recovering.

Current metrics:
- Success rate: 94% and climbing (was 0%)
- Latency p99: 450ms (normal: 300ms, elevated due to recovery)
- Error rate: 6% and falling

We are monitoring for stability. Service should fully recover in ~10 minutes
as caches warm.

Next update: 15:15 or when fully recovered
```

---

### Update 4 - Resolved (15:18 UTC)

```
[SEV1] PAYMENT SERVICE - RESOLVED

Status: Resolved
Total duration: 55 minutes (14:23 - 15:18)
Impact: ~3,200 failed transactions over 40 minutes

Resolution: Rolled back to version 2.4.0

Current metrics (stable for 15 minutes):
- Success rate: 99.8%
- Latency p99: 280ms
- Error rate: 0.2%

Timeline:
- 14:10 - Version 2.4.1 deployed
- 14:15 - First errors detected by monitoring
- 14:23 - Incident declared
- 14:47 - Root cause identified (connection pool config)
- 14:52 - Rollback completed
- 15:18 - Confirmed stable, incident resolved

Next steps:
- Customer communication going out now
- Postmortem scheduled for Monday 10:00 UTC
- Postmortem doc: [link]

Thank you to @mike, @alex, @priya for quick response.
IC signing off. Channel will be archived in 24 hours.
```

---

## Lessons for Future Incidents

This incident demonstrates:
1. **Regular updates**: Updates every 15 minutes kept stakeholders informed
2. **Clear status progression**: Investigating → Identified → Monitoring → Resolved
3. **Ownership clarity**: Each action had an owner
4. **Metrics included**: Quantified impact and recovery
5. **Timeline preserved**: Full timeline in resolution message
