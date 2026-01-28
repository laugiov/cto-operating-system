# CTO Operating System

Decision memos, incident playbooks, SLO templates, and architecture reviews. Use them. Adapt them. Ship.

---

## TL;DR

- **What**: Templates for decisions, incidents, SLOs, security reviews, R&D governance
- **Who**: Engineering leaders (CTO, VP Eng, Head of Security)
- **Inside**: Guides, templates, anonymized examples
- **How**: Copy, adapt, ship
- **Philosophy**: Decisions get memos. SLOs drive priority. Security reviews gate launches.
- **License**: MIT

---

## Evaluate in 10 Minutes

| Time | File | What You'll See |
|------|------|-----------------|
| 2 min | [Decision Memo Template](templates/decision-memo.md) | How decisions get documented |
| 2 min | [Postmortem Template](templates/postmortem.md) | How incidents get reviewed |
| 3 min | [DM-001: Reliability vs Features](examples/decision-memos/DM-001-stabilize-vs-features.md) | A real trade-off with numbers |
| 3 min | [R&D Lab Guide](docs/08-innovation-ai-rnd-lab.md) | How experiments get governed |

Full walkthrough: [10-Minute Guide](docs/00-evaluate-in-10min.md)

---

## Start in 7 Days

1. **Day 1**: Pick one cadence — adopt the [Weekly Exec Review](templates/weekly-exec-review.md) format
2. **Day 2**: Write your first [Decision Memo](templates/decision-memo.md) for a pending technical choice
3. **Day 3**: Define 2-3 SLOs for your most critical service using the [SLO Guide](docs/03-slo-sla-error-budgets.md)
4. **Day 4**: Run one [Architecture Review](templates/architecture-review.md) on an upcoming project
5. **Day 5**: Set up incident communication templates in your Slack/Teams
6. **Day 6**: Draft your first [Quarterly Plan](templates/quarterly-planning.md) skeleton
7. **Day 7**: Review and adjust — keep what works, discard what doesn't

---

## Topics Covered

| Area | What's Included |
|------|-----------------|
| **Decisions** | Memos with options, trade-offs, rollback plans |
| **Reliability** | SLOs, error budgets, postmortems |
| **Security** | Threat models, risk acceptance, exception tracking |
| **R&D/AI** | Experiment cards, kill criteria, model governance |
| **Operations** | Weekly reviews, escalation rules, on-call targets |
| **Org** | Hiring scorecards, onboarding checklists |

---

## Hiring Relevance

| Role | Start Here | Key Sections |
|------|------------|--------------|
| **CTO** | [30-60-90 Plan](docs/01-cto-30-60-90.md) | Operating rhythm, Decision memos, Org design |
| **Head of Engineering** | [Operating Rhythm](docs/02-operating-rhythm.md) | SLOs, Incident management, Quarterly planning |
| **Head of Security Engineering** | [Security-by-Design](docs/07-security-by-design-leadership.md) | Risk acceptance, Security reviews, Governance |
| **Platform Security Architect** | [Architecture Review](templates/architecture-review.md) | Security review template, Exception requests |

---

## Principles

1. **SLOs decide priority** — Error budgets determine what ships. No budget = reliability work first.
2. **Decisions get memos** — Every significant choice: context, options, rationale, owner.
3. **Security gates launches** — Architecture reviews required. Exceptions tracked with expiry dates.
4. **Experiments have kill dates** — Hypothesis, success criteria, time box. No infinite projects.

---

## Non-Goals

- **Not a blog** — No thought leadership essays; only actionable templates and examples
- **Not vendor-specific** — No proprietary tools or cloud-specific implementations
- **Not exhaustive** — Covers common scenarios. Adapt for edge cases.
- **Not prescriptive** — Adapt to your organization's size, culture, and constraints
- **Not a compliance framework** — Complements but doesn't replace SOC2, ISO27001, etc.

---

## Contents

### Guides (`docs/`)

| File | Description |
|------|-------------|
| [00-evaluate-in-10min.md](docs/00-evaluate-in-10min.md) | Start here |
| [01-cto-30-60-90.md](docs/01-cto-30-60-90.md) | First 100 days as CTO/Head of Engineering |
| [02-operating-rhythm.md](docs/02-operating-rhythm.md) | Weekly, monthly, quarterly cadences |
| [03-slo-sla-error-budgets.md](docs/03-slo-sla-error-budgets.md) | Reliability framework fundamentals |
| [04-incident-management.md](docs/04-incident-management.md) | Incident response from detection to postmortem |
| [05-roadmap-arbitrage-framework.md](docs/05-roadmap-arbitrage-framework.md) | Prioritization when everything is urgent |
| [06-org-design-and-hiring.md](docs/06-org-design-and-hiring.md) | Team structures and hiring practices |
| [07-security-by-design-leadership.md](docs/07-security-by-design-leadership.md) | Embedding security in engineering culture |
| [08-innovation-ai-rnd-lab.md](docs/08-innovation-ai-rnd-lab.md) | Running an internal R&D/AI lab with governance |
| [09-decision-memos-playbook.md](docs/09-decision-memos-playbook.md) | Writing effective architectural decisions |

### Templates (`templates/`)

| File | Description |
|------|-------------|
| [weekly-exec-review.md](templates/weekly-exec-review.md) | Weekly executive status meeting agenda |
| [monthly-tech-governance.md](templates/monthly-tech-governance.md) | Monthly technical governance review |
| [quarterly-planning.md](templates/quarterly-planning.md) | Quarterly OKR and roadmap planning |
| [decision-memo.md](templates/decision-memo.md) | Technical decision documentation |
| [postmortem.md](templates/postmortem.md) | Blameless incident postmortem |
| [incident-comms-internal.md](templates/incident-comms-internal.md) | Internal incident communication |
| [incident-comms-exec.md](templates/incident-comms-exec.md) | Executive incident briefing |
| [slo-catalog.md](templates/slo-catalog.md) | Service Level Objectives registry |
| [risk-acceptance.md](templates/risk-acceptance.md) | Formal risk acceptance documentation |
| [exception-request.md](templates/exception-request.md) | Security/policy exception request |
| [architecture-review.md](templates/architecture-review.md) | Architecture review checklist |
| [security-review.md](templates/security-review.md) | Security design review |
| [hiring-scorecard.md](templates/hiring-scorecard.md) | Structured interview evaluation |
| [onboarding-30-days.md](templates/onboarding-30-days.md) | New hire onboarding checklist |
| [lab-proposal-onepager.md](templates/lab-proposal-onepager.md) | R&D experiment proposal |
| [experiment-card.md](templates/experiment-card.md) | Experiment tracking card |
| [model-eval-report.md](templates/model-eval-report.md) | AI/ML model evaluation report |

### Examples (`examples/`)

| File | Description |
|------|-------------|
| [DM-001-stabilize-vs-features.md](examples/decision-memos/DM-001-stabilize-vs-features.md) | Trade-off: stability investment vs. feature velocity |
| [DM-002-platform-security-investment.md](examples/decision-memos/DM-002-platform-security-investment.md) | Multi-year security platform investment case |
| [DM-003-ai-lab-governance.md](examples/decision-memos/DM-003-ai-lab-governance.md) | Establishing AI lab governance framework |
| [INC-001-incident-comms-internal.md](examples/incidents/INC-001-incident-comms-internal.md) | Internal comms during major incident |
| [INC-001-incident-comms-exec.md](examples/incidents/INC-001-incident-comms-exec.md) | Executive briefing during incident |
| [INC-001-postmortem.md](examples/incidents/INC-001-postmortem.md) | Complete postmortem example |
| [Q-001-quarterly-plan-example.md](examples/planning/Q-001-quarterly-plan-example.md) | Quarterly planning output example |

---

## License

This project is licensed under the [MIT License](LICENSE).
