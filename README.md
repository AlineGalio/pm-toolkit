# pm-toolkit

A portfolio of project and program management artifacts, built around one **fictional** case: the *Broker Portal* of *Example Insurance Co.* All data is invented. Nothing comes from a real client.

## The case

A 6-month program (Nov 2026 to Apr 2027) that remediates 13 technical debt items (860 h) in a three-layer web application. Every artifact uses the same IDs (EX-01 to EX-13) and the same Risk × Impact scale, so they read as one story.

## Contents

| Folder | What it contains | Format |
| --- | --- | --- |
| [`assessment/`](assessment/) | Technical debt assessment: method and sample report (13 items, scoring, quadrants, waves) | Markdown + HTML |
| [`user-stories/`](user-stories/) | Blank template and a filled example (US-001, secrets vault) with Given/When/Then criteria | Markdown |
| [`team-agreements/`](team-agreements/) | Definition of Ready and Definition of Done checklists | Markdown |
| [`adr/`](adr/) | ADR-0001 Strangler Fig instead of full rewrite; ADR-0002 Polly for circuit breaker | Markdown |
| [`roadmap/`](roadmap/) | 6-month roadmap with milestones, linked to the assessment | Markdown |
| [`risks/`](risks/) | Risk register (13 risks, Probability × Impact) | Markdown |
| [`raid/`](raid/) | RAID log: assumptions, issues, dependencies | Markdown |
| [`dashboard/`](dashboard/) | Agile delivery dashboard: velocity, burndown, lead time, bugs, incidents | HTML + XLSX |
| [`playbook/`](playbook/) | Legacy migration playbook and 10-slide deck | Markdown + PDF |

## Suggested reading order

1. [`assessment/`](assessment/): where the 13 items and scores come from.
2. [`adr/`](adr/), [`user-stories/`](user-stories/), [`team-agreements/`](team-agreements/): how decisions and work are defined.
3. [`roadmap/`](roadmap/), [`risks/`](risks/), [`raid/`](raid/): how the work is planned and controlled.
4. [`dashboard/`](dashboard/): how progress is measured.
5. [`playbook/`](playbook/): the general method behind it.

## Repository layout

```text
pm-toolkit/
├── README.md
├── assessment/        README.md, index.html
├── user-stories/      TEMPLATE.md, US-001-move-secrets-to-vault.md
├── team-agreements/   definition-of-ready.md, definition-of-done.md
├── adr/               0001-strangler-fig-instead-of-full-rewrite.md
│                      0002-polly-for-circuit-breaker.md
├── roadmap/           roadmap.md
├── risks/             risk-register.md
├── raid/              raid-log.md
├── dashboard/         index.html, agile-dashboard-data.xlsx
└── playbook/          README.md, legacy-migration-playbook.pdf
```

## Live demos

- Assessment report: `https://alinegalio.github.io/pm-toolkit/assessment/`
- Assessment README: `https://alinegalio.github.io/pm-toolkit/assessment/README`
- Agile dashboard: `https://alinegalio.github.io/pm-toolkit/dashboard/`
- Excel Agile numbers: `https://alinegalio.github.io/pm-toolkit/dashboard/agile-dashboard-data.xlsx`
- User Stories - template: `https://alinegalio.github.io/pm-toolkit/user-stories/TEMPLATE`
- User Stories - example: `https://alinegalio.github.io/pm-toolkit/user-stories/US-001-move-secrets-to-vault`
- ADR - example 1:`https://alinegalio.github.io/pm-toolkit/adr/0001-strangler-fig-instead-of-full-rewrite`
- ADR - example 1:`https://alinegalio.github.io/pm-toolkit/adr/0002-polly-for-circuit-breaker`
- DoD: `https://alinegalio.github.io/pm-toolkit/team-agreements/definition-of-done`
- DoR: `https://alinegalio.github.io/pm-toolkit/team-agreements/definition-of-ready`
- Roadmap: `https://alinegalio.github.io/pm-toolkit/roadmap/roadmap`
- Risks: `https://alinegalio.github.io/pm-toolkit/risks/risk-register`
- RAID: `https://alinegalio.github.io/pm-toolkit/raid/raid-log`
- Playbook README: `https://alinegalio.github.io/pm-toolkit/playbook/README.md`
- Playbook PDF: `https://alinegalio.github.io/pm-toolkit/playbook/legacy-migration-playbook.pdf`

## Principles

- **Fictional data only.** No client names, models or material.
- **Public knowledge only.** Methods are generic and adapted, not copied.
- **Traceable.** Debt item → story → risk → roadmap milestone → dashboard metric.
- **Owners and dates are roles and placeholders**, marked *to be confirmed* until a team agrees.

## License

No Licensing required.
