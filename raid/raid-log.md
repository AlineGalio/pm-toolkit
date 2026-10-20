# `raid/raid-log.md`

## RAID log: Assumptions, Issues, Dependencies

Risks live in the [risk register](../risks/risk-register.md). Owners are roles. *Fictional data.*

### Assumptions

| ID | Assumption | If false | Owner | Validate by | Status |
| --- | --- | --- | --- | --- | --- |
| A-01 | Five engineers and one QA are available at 80% | Re-plan waves; extend timeline | Program Manager | 2026-10-30 | Open |
| A-02 | Platform team delivers the vault by week 2 | EX-01 slips; see R-01 | Program Manager | 2026-11-06 | Open |
| A-03 | Partners accept one rotation window per environment | Rotation split into smaller steps | Integration Lead | 2026-11-06 | Open |
| A-04 | Production releases happen every two weeks | Waves lengthen | Release Manager | 2026-10-30 | Confirmed |
| A-05 | Estimates are accurate within ±25% | Scope or date change | Tech Lead | After each wave | Open |
| A-06 | Premium rules are frozen while tests are written | Tests chase moving logic | Product Owner | 2026-11-13 | Open |
| A-07 | Architecture approves a current LTS runtime as target | EX-05 blocked | Architecture | 2026-12-04 | Open |
| A-08 | Pilot front-end module has no new features planned | Pilot delayed | Product Owner | 2027-02-26 | Open |
| A-09 | Corporate trust store is reachable from the API | EX-03 needs a workaround | Security Officer | 2026-11-06 | Open |
| A-10 | Monitoring stack accepts OpenTelemetry data | EX-08 needs a new collector | Platform Lead | 2026-12-11 | Open |

### Issues

| ID | Issue | Impact | Linked | Owner | Raised | Due | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| I-01 | Vault access request not yet approved | Blocks EX-01 start | EX-01 | Program Manager | 2026-10-19 | 2026-11-06 | Open |
| I-02 | Staging TLS configuration differs from production | Tests may not reflect production | EX-03 | DevOps Engineer | 2026-10-19 | 2026-11-13 | Open |
| I-03 | No anonymized data set for premium edge cases | Slows test writing | EX-04 | QA Lead | 2026-10-19 | 2026-11-20 | Open |
| I-04 | Pipeline has no dependency scan | CVE found late, not at build | EX-02 | DevOps Engineer | 2026-10-19 | 2026-11-13 | In progress |
| I-05 | Two long-lived branches conflict with history rewrite | Rework or lost commits | EX-01 | Tech Lead | 2026-10-19 | 2026-11-13 | Open |
| I-06 | Current runtime blocks the OpenTelemetry package version | Delays EX-08 | EX-08 | Back-end Lead | 2026-10-19 | 2027-01-15 | Open |
| I-07 | Partner sandbox is offline on weekends | Limits resilience testing | EX-06 | Integration Lead | 2026-10-19 | 2026-12-04 | Open |
| I-08 | Premium rule documentation is outdated | Characterization tests need reverse engineering | EX-04 | Business Analyst | 2026-10-19 | 2026-11-27 | Open |
| I-09 | No owner for UI message content | EX-11 cannot start | EX-11 | Product Owner | 2026-10-19 | 2027-02-26 | Open |
| I-10 | No baseline of velocity and incidents before the program | Hard to show improvement | All | Program Manager | 2026-10-19 | 2026-11-13 | In progress |

### Dependencies

| ID | Dependency | Provider | Needed by | Linked | Status |
| --- | --- | --- | --- | --- | --- |
| D-01 | Vault in dev, staging and production | Platform team | 2026-11-13 | EX-01 | Requested |
| D-02 | Rotation windows with each partner | Partner teams | 2026-11-20 | EX-01 | Not requested |
| D-03 | Corporate trust store certificates | Security team | 2026-11-13 | EX-03 | Requested |
| D-04 | Architecture decision on the target runtime | Architecture board | 2026-12-04 | EX-05 | Not requested |
| D-05 | OpenTelemetry collector in staging and production | Observability team | 2027-01-15 | EX-08 | Not requested |
| D-06 | Staging refresh with anonymized data | Data team | 2026-11-20 | EX-04 | Requested |
| D-07 | Payment gateway sandbox credentials | Payment vendor | 2026-12-04 | EX-06 | Requested |
| D-08 | Design system components for the front-end shell | UX team | 2027-02-26 | EX-09 | Not requested |
| D-09 | Release calendar and change approvals | Change management | 2026-11-06 | All | Confirmed |
| D-10 | Product Owner time for acceptance in each review | Product team | Every sprint | All | Confirmed |
