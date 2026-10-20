# Technical Debt Assessment: Method

A lightweight, repeatable framework to find, score and sequence technical debt in an application. The sample report in this folder (`index.html`) applies it to a **fictional** system, the *Broker Portal* of *Example Insurance Co.* All data is invented.

## 1. Process

1. **Scope:** define the application, its layers (front end, API, integrations) and the repositories in scope.
2. **Discover:** combine static analysis, dependency scanning, code review and interviews with the team.
3. **Validate:** confirm every item with the engineers who own the code. Discard false positives.
4. **Score:** assign Risk and Impact (1–5 each).
5. **Estimate:** the team gives effort in hours and the required profile (BE, FE, FS).
6. **Prioritize:** place each item in a quadrant and group items into waves.
7. **Review:** re-score after each wave, because closing one item changes the risk of others.

## 2. Scoring

**Score = Risk × Impact** (range 1–25).

| Dimension | Scale | Question |
| --- | --- | --- |
| Risk | 1–5 | How likely is this debt to cause an incident, breach or failed release? |
| Impact | 1–5 | How bad is the business and operational damage if it happens? |
| Effort | hours | Reported separately. It does **not** change the score. |

Keeping effort out of the score avoids hiding a dangerous item just because it is expensive.

## 3. Quadrants

| Quadrant | Score | Meaning |
| --- | --- | --- |
| **Act now** | ≥ 16 | Start immediately, usually security or critical-path quality |
| **Plan** | 9–15 | Schedule into upcoming waves with a clear owner |
| **Defer** | 4–8 | Bundle into routine maintenance |
| **Accept** | ≤ 3 | Document the decision and review later |

## 4. Categories

Each item gets one category, used to see where the debt concentrates:

- Security & Compliance
- Platform Lifecycle
- Reliability
- Code Health
- Interfaces & Contracts

## 5. Deliverables per application

- Debt report with problem, proposed solution, layer, profile, hours, Risk, Impact, score and quadrant
- Effort summary by quadrant, profile and category
- Recommended sequence in waves
- List of assumptions and open points

## 6. Sample results (fictional)

| Quadrant | Items | Hours | % of hours |
| --- | --- | --- | --- |
| Act now | 4 | 136 | 15.8% |
| Plan | 5 | 648 | 75.3% |
| Defer | 3 | 72 | 8.4% |
| Accept | 1 | 4 | 0.5% |
| **Total** | **13** | **860** | **100%** |

## 7. Good practices

- Start with cheap, high-score items (usually security) to show value fast.
- Write characterization tests before refactoring legacy code.
- Prefer incremental patterns (Strangler Fig, upgrade in waves, canary release) over big-bang rewrites.
- Treat estimates as validated forecasts, not contractual commitments.
- Always list owners and dates as *to be confirmed* until the team agrees.

## 8. Limitations

The scale is a judgment call. Two assessors may differ by one point, so calibrate with the team before scoring. This is a sample for demonstration, not an industry standard.

*Fictional data. No client information.*
