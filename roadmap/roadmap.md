# Broker Portal remediation program: 6-month roadmap

**Window:** 2026-11-02 to 2027-04-30 · **Source:** Technical Debt Assessment (13 items, 860 h) · *Fictional data*

| ID | Work item | Debt item | Total h | Nov | Dec | Jan | Feb | Mar | Apr | Milestone |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| M1 | Secrets vault and credential rotation | EX-01 | 16 | ■ | | | | | | No secrets in repo (week 3) |
| M2 | Logging library emergency patch | EX-02 | 8 | ■ | | | | | | CVE closed (week 1) |
| M3 | TLS validation fix, single HTTP client factory | EX-03 | 32 | ■ | | | | | | Insecure clients removed (week 3) |
| M4 | Characterization and unit tests, premium calculation | EX-04 | 80 | ■ | ■ | ■ | | | | Coverage gate active |
| M5 | Resilience policies, payment gateway pilot | EX-06 | 56 | | ■ | ■ | | | | Circuit breaker in production |
| M6 | Tracing foundation (OpenTelemetry) | EX-08 | 80 | | | ■ | ■ | | | End-to-end trace in staging |
| M7 | Runtime upgrade: proof of concept, then waves | EX-05 | 240 | | | ■ | ■ | ■ | ■ | PoC approved (Feb); continues after Apr |
| M8 | Monolithic controller extraction | EX-07 | 112 | | | | ■ | ■ | ■ | First service extracted |
| M9 | Front-end shell and first migrated module | EX-09 | 160 | | | | | ■ | ■ | Pilot module live; continues after Apr |
| M10 | Maintenance bundle (OpenAPI, messages, cleanup, lint) | EX-10 to EX-13 | 76 | | | | | ■ | ■ | Four pull requests merged |
| M11 | Wave review and re-scoring | All | n/a | | ■ | | ■ | | ■ | Updated assessment |
| M12 | Steering committee | All | n/a | ■ | ■ | ■ | ■ | ■ | ■ | Monthly decision log |

**Hours check:** 16 + 8 + 32 + 80 + 56 + 80 + 240 + 112 + 160 + 76 = **860 h**.
