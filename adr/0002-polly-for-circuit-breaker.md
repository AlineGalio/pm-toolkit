# `adr/0002-polly-for-circuit-breaker.md`

## ADR-0002: Use Polly for timeouts, retries and circuit breaker

- **Status:** Accepted
- **Date:** 2026-10-19
- **Deciders:** Tech Lead, Back-end team (fictional)
- **Related:** EX-06 (No retry or circuit breaker on the payment gateway)

### Context and problem statement
A slow payment gateway exhausts the API thread pool, and the failure spreads to unrelated endpoints. There are no timeouts, retries or circuit breakers on partner calls.

### Decision drivers
- Fail fast and contain failures to one integration
- Standard, maintained library for the .NET stack
- Configuration per integration, not hardcoded
- Metrics that feed the tracing and dashboards planned in EX-08

### Considered options
1. Polly, integrated with the HTTP client factory
2. Hand-written retry and timeout logic per integration
3. Service mesh or gateway-level resilience

### Decision outcome
Chosen option: **1, Polly**. Each integration gets a resilience policy: timeout, retry with exponential backoff and jitter, and a circuit breaker. Pilot on the payment gateway, then extend.

### Consequences
- **Good:** consistent behavior across integrations; fewer cascading failures.
- **Good:** policies are configurable and testable.
- **Bad:** badly tuned retries can amplify load, so limits and breaker thresholds need load testing.
- **Bad:** callers must handle the "circuit open" case with a clear fallback or error.
- **Follow-up:** define default thresholds, emit breaker state as metrics, add alerts.

### Pros and cons of the options
| Option | Pros | Cons |
| --- | --- | --- |
| Polly | Mature, fits the HTTP client factory | New dependency to learn and tune |
| Hand-written | No dependency | Inconsistent, hard to test, easy to get wrong |
| Mesh / gateway | Central control | New infrastructure, slower to deliver |
