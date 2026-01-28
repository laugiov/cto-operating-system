# Model Evaluation Report

## Metadata

| Field | Value |
|-------|-------|
| **Report ID** | EVAL-<NUMBER> |
| **Model Name** | <Model identifier> |
| **Version** | <Version number> |
| **Experiment** | [EXP-XXX](link) |
| **Author** | <Name> |
| **Date** | <YYYY-MM-DD> |
| **Status** | Draft / Final |

---

## Executive Summary

<3-4 sentences: What was evaluated, key findings, recommendation>

| Verdict | Rationale |
|---------|-----------|
| Ready for production / Needs improvement / Not viable | <Brief reason> |

---

## Model Overview

### Purpose
<What does this model do?>

### Architecture
| Field | Value |
|-------|-------|
| Model type | <Classification, regression, generative, etc.> |
| Base model (if fine-tuned) | <Base model name> |
| Parameters | <Number of parameters> |
| Framework | <PyTorch, TensorFlow, etc.> |

### Training Data

| Field | Value |
|-------|-------|
| Dataset | <Dataset name or description> |
| Size | <Number of examples> |
| Time range | <If applicable> |
| Data source | <Origin of data> |
| PII present | Yes / No |
| License | <License type> |

---

## Evaluation Methodology

### Test Dataset

| Field | Value |
|-------|-------|
| Dataset | <Name> |
| Size | <Number of examples> |
| Split | <How it relates to training data> |
| Representative | <Is it representative of production?> |

### Metrics Evaluated

| Metric | Why This Metric |
|--------|-----------------|
| <Metric 1> | <Rationale> |
| <Metric 2> | <Rationale> |
| <Metric 3> | <Rationale> |

### Evaluation Process
<How evaluation was conducted>

---

## Performance Results

### Primary Metrics

| Metric | Target | Result | Status |
|--------|--------|--------|--------|
| <Accuracy/F1/etc.> | <Target> | <Result> | Pass / Fail |
| <Latency p50> | <Target> | <Result> | Pass / Fail |
| <Latency p99> | <Target> | <Result> | Pass / Fail |
| <Throughput> | <Target> | <Result> | Pass / Fail |

### Performance by Segment

| Segment | Metric | Result | Notes |
|---------|--------|--------|-------|
| <Segment 1> | <Metric> | <Result> | <Observations> |
| <Segment 2> | <Metric> | <Result> | <Observations> |

### Comparison to Baseline

| Model | Metric 1 | Metric 2 | Metric 3 |
|-------|----------|----------|----------|
| Baseline | <Value> | <Value> | <Value> |
| This model | <Value> | <Value> | <Value> |
| Delta | <+/-X%> | <+/-X%> | <+/-X%> |

---

## Cost Analysis

| Metric | Value |
|--------|-------|
| Inference cost per request | <$X.XX> |
| Training cost | <$X,XXX> |
| Monthly estimated cost at scale | <$X,XXX for Y requests> |

### Cost Comparison

| Option | Cost/Request | Monthly Total |
|--------|--------------|---------------|
| This model | <$X.XX> | <$X,XXX> |
| Alternative 1 | <$X.XX> | <$X,XXX> |
| Current solution | <$X.XX> | <$X,XXX> |

---

## Safety and Fairness

### Bias Evaluation

| Dimension | Finding | Severity |
|-----------|---------|----------|
| <Demographic 1> | <Result> | None / Low / Medium / High |
| <Demographic 2> | <Result> | None / Low / Medium / High |

### Safety Testing

| Test | Result | Notes |
|------|--------|-------|
| Harmful content generation | Pass / Fail | <Details> |
| Prompt injection resistance | Pass / Fail | <Details> |
| PII leakage | Pass / Fail | <Details> |
| Out-of-scope behavior | Pass / Fail | <Details> |

### Red Team Findings

| Finding | Severity | Mitigation |
|---------|----------|------------|
| <Finding 1> | Low / Medium / High / Critical | <Action taken> |

---

## Failure Analysis

### Common Failure Modes

| Failure Mode | Frequency | Impact | Example |
|--------------|-----------|--------|---------|
| <Mode 1> | <X%> | Low / Medium / High | <Example> |
| <Mode 2> | <X%> | Low / Medium / High | <Example> |

### Edge Cases

| Edge Case | Behavior | Acceptable? |
|-----------|----------|-------------|
| <Case 1> | <What happens> | Yes / No |
| <Case 2> | <What happens> | Yes / No |

---

## Production Readiness

### Checklist

- [ ] Meets accuracy targets
- [ ] Meets latency targets
- [ ] Meets cost targets
- [ ] Bias evaluation complete
- [ ] Safety testing complete
- [ ] Monitoring defined
- [ ] Rollback plan documented
- [ ] On-call ownership assigned

### Gaps Identified

| Gap | Severity | Remediation |
|-----|----------|-------------|
| <Gap 1> | Low / Medium / High | <Plan> |

---

## Recommendation

### Verdict
| Decision | Confidence |
|----------|------------|
| Deploy to production / Iterate further / Do not proceed | High / Medium / Low |

### Rationale
<Why this recommendation>

### Conditions for Deployment
- <Condition 1>
- <Condition 2>

### Next Steps
1. <Action 1>
2. <Action 2>

---

## Appendix

### Detailed Results
<Link to full results data>

### Model Card
<Link to model card if separate>

### Artifacts

| Artifact | Location |
|----------|----------|
| Model weights | <Path> |
| Evaluation data | <Path> |
| Evaluation code | <Path> |
| Training logs | <Path> |
