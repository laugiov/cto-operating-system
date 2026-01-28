# SLO Catalog

## Overview

This document catalogs all Service Level Objectives for production services.

**Last updated**: <YYYY-MM-DD>
**Owner**: <Team or Name>

### Default Thresholds

| Tier | Availability | Latency p99 | Error Budget (30d) |
|------|--------------|-------------|-------------------|
| 1 | 99.95% | 200ms | 22 min |
| 2 | 99.9% | 500ms | 43 min |
| 3 | 99% | 2000ms | 7.2 hours |

---

## SLO Registry

### <SERVICE NAME 1>

| Field | Value |
|-------|-------|
| **Service** | <Service name> |
| **Tier** | 1 / 2 / 3 |
| **Owner** | <Team> |
| **Dashboard** | [Link](<dashboard-url>) |

#### SLOs

| SLI | Target | Window | Current | Status |
|-----|--------|--------|---------|--------|
| Availability (success rate) | <99.9%> | 30-day rolling | <X%> | On track / At risk / Breached |
| Latency p50 | <100ms> | 30-day rolling | <Xms> | On track / At risk / Breached |
| Latency p99 | <500ms> | 30-day rolling | <Xms> | On track / At risk / Breached |

#### Error Budget

| Metric | Value |
|--------|-------|
| Budget (30 days) | <X minutes> |
| Consumed | <Y minutes> (<Z%>) |
| Remaining | <W minutes> |
| Status | Healthy / Caution / Critical / Exhausted |

---

### <SERVICE NAME 2>

| Field | Value |
|-------|-------|
| **Service** | <Service name> |
| **Tier** | 1 / 2 / 3 |
| **Owner** | <Team> |
| **Dashboard** | [Link](<dashboard-url>) |

#### SLOs

| SLI | Target | Window | Current | Status |
|-----|--------|--------|---------|--------|
| Availability | <X%> | 30-day rolling | <Y%> | On track / At risk / Breached |
| Latency p99 | <Xms> | 30-day rolling | <Yms> | On track / At risk / Breached |
| Throughput | <X rps> | 30-day rolling | <Y rps> | On track / At risk / Breached |

#### Error Budget

| Metric | Value |
|--------|-------|
| Budget (30 days) | <X minutes> |
| Consumed | <Y minutes> (<Z%>) |
| Remaining | <W minutes> |
| Status | Healthy / Caution / Critical / Exhausted |

---

## Tier Definitions

| Tier | Description | Typical SLO | On-call |
|------|-------------|-------------|---------|
| **1** | Revenue-critical, user-facing | 99.95%+ | 24/7 |
| **2** | Important, significant impact if down | 99.9% | Business hours + on-call |
| **3** | Internal tools, limited impact | 99% | Best effort |

---

## Error Budget Policy

| Budget Status | Definition | Required Action |
|---------------|------------|-----------------|
| **Healthy** | >50% remaining | Normal operations |
| **Caution** | 25-50% remaining | Increase review rigor, limit risky changes |
| **Critical** | <25% remaining | Feature freeze consideration, reliability focus |
| **Exhausted** | 0% remaining | Feature freeze, all hands on reliability |

---

## Review Schedule

| Review | Frequency | Attendees |
|--------|-----------|-----------|
| SLO check | Weekly | Service owners |
| Budget review | Monthly | Tech governance |
| Target review | Quarterly | Leadership + service owners |

---

## Adding a New SLO

1. Define SLIs based on user experience
2. Analyze baseline performance (4+ weeks)
3. Propose target based on baseline and requirements
4. Get stakeholder sign-off
5. Implement monitoring and alerting
6. Add to this catalog
7. Review after 30 days and adjust if needed
