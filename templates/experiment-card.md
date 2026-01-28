# Experiment Card

## Metadata

| Field | Value |
|-------|-------|
| **Experiment ID** | EXP-<NUMBER> |
| **Title** | <Experiment name> |
| **Proposal** | [LAB-XXX](link) |
| **Owner** | <Name> |
| **Start Date** | <YYYY-MM-DD> |
| **End Date** | <YYYY-MM-DD> |
| **Status** | Not Started / In Progress / Completed / Killed |

---

## Hypothesis

> We believe that [action/solution]
> will result in [outcome]
> for [target user/system].
> We will know this is true when [measurable signal].

---

## Experiment Design

### What We're Testing
<Clear description of what this experiment will prove or disprove>

### Approach
<Technical approach - what we'll build, how we'll test>

### Variables

| Variable | Type | Description |
|----------|------|-------------|
| <Variable 1> | Independent / Dependent | <What it is> |
| <Variable 2> | Independent / Dependent | <What it is> |

### Controls
<What we're holding constant to isolate the variable>

---

## Success Criteria

| Metric | Baseline | Target | Weight |
|--------|----------|--------|--------|
| <Primary metric> | <Current> | <Goal> | Primary |
| <Secondary metric> | <Current> | <Goal> | Secondary |
| <Guardrail metric> | <Current> | <Must not regress> | Guardrail |

### How We'll Measure
<Tools, methods, data sources for measurement>

---

## Kill Criteria

Stop immediately if:
- [ ] <Critical failure condition>
- [ ] <Safety or compliance issue>
- [ ] <Resource overrun condition>

Pause and reassess if:
- [ ] <Significant obstacle encountered>
- [ ] <Intermediate milestone missed>

---

## Resources

| Resource | Allocated | Used | Notes |
|----------|-----------|------|-------|
| Time | <X weeks> | <Y weeks> | |
| Engineers | <X FTE> | | |
| Compute | <$X or hours> | <$Y> | |
| Data | <Dataset> | | |

---

## Timeline

| Milestone | Target Date | Status | Notes |
|-----------|-------------|--------|-------|
| Setup complete | <Date> | Done / In progress / Not started | |
| First results | <Date> | Done / In progress / Not started | |
| Checkpoint review | <Date> | Done / In progress / Not started | |
| Final evaluation | <Date> | Done / In progress / Not started | |

---

## Progress Log

### <YYYY-MM-DD>
<What happened, what was learned, any blockers>

### <YYYY-MM-DD>
<What happened, what was learned, any blockers>

---

## Checkpoints

### Checkpoint 1: <Date>
- [ ] Scheduled
- [ ] Completed

**Questions to answer**:
- Are we on track to meet success criteria?
- Any blockers or concerns?
- Should we continue, pivot, or kill?

**Decision**: Continue / Pivot / Kill

### Checkpoint 2: <Date>
- [ ] Scheduled
- [ ] Completed

**Decision**: Continue / Pivot / Kill

---

## Results (Complete at End)

### Summary
<2-3 sentences summarizing what we learned>

### Metrics Achieved

| Metric | Target | Actual | Met? |
|--------|--------|--------|------|
| <Metric 1> | <Target> | <Actual> | Yes / No |
| <Metric 2> | <Target> | <Actual> | Yes / No |

### Key Learnings
1. <Learning 1>
2. <Learning 2>
3. <Learning 3>

### What Worked
- <Success 1>
- <Success 2>

### What Didn't Work
- <Failure 1>
- <Failure 2>

---

## Recommendation

| Decision | Rationale |
|----------|-----------|
| Productize / Iterate / Kill / Pivot | <Why> |

### Next Steps
- <Action 1>
- <Action 2>

---

## Artifacts

| Artifact | Location |
|----------|----------|
| Code | [Link](<repo-url>) |
| Data | [Link](<data-location>) |
| Model (if applicable) | [Link](<model-location>) |
| Evaluation report | [Link](<eval-report>) |
