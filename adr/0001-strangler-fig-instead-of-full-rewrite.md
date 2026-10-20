# ADR-0001: Use the Strangler Fig pattern instead of a full rewrite

- **Status:** Accepted
- **Date:** 2026-10-19
- **Deciders:** Tech Lead, Product Owner, Architecture (fictional)
- **Related:** EX-09 (Outdated front-end framework)

### Context and problem statement
The Broker Portal front end uses a first-generation framework that blocks library upgrades. Brokers use the portal daily, and the premium flow cannot stop. We must modernize without freezing feature delivery.

### Decision drivers
- No long freeze on new features
- Low risk of regression in business-critical screens
- Value delivered early and measurably
- Team can learn the new stack while delivering

### Considered options
1. Full rewrite, then switch over (big bang)
2. Strangler Fig: a modern shell hosts legacy modules while each is rewritten
3. Keep the framework and patch dependencies

### Decision outcome
Chosen option: **2, Strangler Fig**. A modern shell routes each page to either the legacy or the new module. Modules migrate one at a time, starting with a low-risk screen.

### Consequences
- **Good:** releases continue during migration; each module can be rolled back by routing; early feedback.
- **Good:** risk is spread over many small releases.
- **Bad:** two stacks run in parallel for months, with a higher build and test cost.
- **Bad:** shared state and authentication must work across both stacks.
- **Follow-up:** define module order, a routing rule and a retirement date for each legacy module.

### Pros and cons of the options

| Option | Pros | Cons |
| --- | --- | --- |
| Full rewrite | Clean result, single stack | Long freeze, late feedback, high cutover risk |
| Strangler Fig | Incremental, reversible | Parallel stacks, integration work |
| Patch only | Cheapest now | Debt keeps growing, upgrades stay blocked |
