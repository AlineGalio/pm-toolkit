# Risk register

**Score = Probability × Impact** (1–5 each), same bands as the assessment: Act now ≥ 16 · Plan 9–15 · Defer 4–8 · Accept ≤ 3.

| ID | Risk | Linked | P | I | Score | Band | Response | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R-01 | Vault access for the three environments is delayed | EX-01 | 4 | 4 | 16 | Act now | Mitigate: escalate request in week 1; start with a staging vault | Program Manager | Open |
| R-02 | Runtime upgrade blocked by libraries with no compatible version | EX-05 | 4 | 4 | 16 | Act now | Mitigate: dependency audit before the PoC; replace or isolate blockers | Tech Lead | Open |
| R-03 | Secret rotation breaks partner integrations | EX-01 | 3 | 5 | 15 | Plan | Mitigate: rotate in maintenance window with partner on call; rollback plan | Back-end Lead | Open |
| R-04 | Premium tests reveal existing defects that need fixes | EX-04 | 4 | 3 | 12 | Plan | Accept and triage: log defects separately, fix by severity | Product Owner | Open |
| R-05 | Feature requests compete with debt work for capacity | All | 4 | 3 | 12 | Plan | Mitigate: reserve 30% of each sprint; agree it in the steering committee | Product Owner | Open |
| R-06 | Retry policies amplify load on the payment gateway | EX-06 | 3 | 4 | 12 | Plan | Mitigate: retry limits, jitter and load test before rollout | Back-end Lead | Open |
| R-07 | Parallel front-end stacks break shared authentication or state | EX-09 | 3 | 4 | 12 | Plan | Mitigate: shared auth layer defined in ADR-0001 follow-up; test in the pilot module | Front-end Lead | Open |
| R-08 | Key engineer leaves or becomes unavailable | All | 3 | 4 | 12 | Plan | Mitigate: pair on critical items; document runbooks | Program Manager | Open |
| R-09 | Sponsor attention drops after the quick security wins | All | 2 | 5 | 10 | Plan | Mitigate: monthly steering committee with measurable results | Program Manager | Open |
| R-10 | History rewrite forces re-clone and loses unmerged work | EX-01 | 3 | 3 | 9 | Plan | Mitigate: freeze branches for one day; announce in advance | Tech Lead | Open |
| R-11 | Estimates are too optimistic on large items | EX-05, EX-09 | 3 | 3 | 9 | Plan | Mitigate: re-estimate after each wave; keep 15% contingency | Program Manager | Open |
| R-12 | Partner maintenance windows are scarce | EX-01, EX-03 | 2 | 4 | 8 | Defer | Accept: book windows in the first two weeks | Integration Lead | Open |
| R-13 | Tracing captures personal data in payloads | EX-08 | 2 | 4 | 8 | Defer | Mitigate: attribute allow-list and masking rules | Security Officer | Open |
