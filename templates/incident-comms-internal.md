# Internal Incident Communication

**Update cadence**: SEV1 every 15 min, SEV2 every 30 min, SEV3 every 60 min.

## Template

Use this format for updates in Slack/Teams incident channels.

---

### Initial Declaration

```
[SEV<X>] <SERVICE> - <BRIEF DESCRIPTION>

Status: Investigating
Impact: <Who/what is affected>
IC: <Name>
Channel: #inc-<YYYYMMDD>-<brief-name>

We are aware of the issue and investigating. Updates every <15/30> minutes.
```

---

### Status Update

```
[SEV<X>] <SERVICE> - UPDATE <NUMBER>

Status: Investigating / Identified / Mitigating / Resolved
Time in incident: <X hours Y minutes>

Current situation:
<1-2 sentences on current state>

What we know:
- <Finding 1>
- <Finding 2>

Current actions:
- <Action 1> - <Owner>
- <Action 2> - <Owner>

Next update: <Time> or when status changes
```

---

### Mitigation Applied

```
[SEV<X>] <SERVICE> - MITIGATION APPLIED

Status: Monitoring
Time in incident: <X hours Y minutes>

Mitigation: <What was done>

We are monitoring for stability. Service should be recovering.

Remaining work:
- <Verification steps>
- <Cleanup tasks>

Next update: <Time>
```

---

### Resolution

```
[SEV<X>] <SERVICE> - RESOLVED

Status: Resolved
Total duration: <X hours Y minutes>
Impact: <Summary of user impact>

Resolution: <What fixed the issue>

Timeline:
- <HH:MM> - Issue started
- <HH:MM> - Detected
- <HH:MM> - Mitigated
- <HH:MM> - Resolved

Next steps:
- Postmortem scheduled for <Date>
- Postmortem doc: <Link>

Thank you to everyone who helped respond.
```

---

## Guidelines

### Timing
- First update: Within 15 minutes of declaration
- During investigation: Every 15-30 minutes
- After mitigation: Every 30-60 minutes
- Always update when status changes

### Tone
- Factual, not emotional
- Clear on what is known vs. suspected
- Honest about uncertainty
- No blame

### What to Include
- Current status
- User impact
- Actions being taken
- Who is working on it
- When next update will come

### What to Avoid
- Speculation about root cause (until verified)
- Promises about resolution time (until confident)
- Technical jargon (for broad audiences)
- Blame or finger-pointing
