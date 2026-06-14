# Review Rubric

Assess each dimension **against the established requirements baseline**, not against an abstract ideal. A dimension can be "right" by being simple when the requirements are modest.

## Severity scale
- **Blocker** — the design will not meet a stated requirement, or has a correctness/data-loss/security flaw. Must fix before building.
- **Major** — significant risk, cost, or complexity problem; likely to bite in production or during scale-up within the planning horizon.
- **Minor** — real but low-impact issue; worth fixing but not urgent.
- **Nit** — style, naming, doc clarity. Optional.

## Dimensions

1. **Requirements clarity** — Are functional and non-functional requirements stated and measurable? Is scale quantified? Are non-goals explicit?
2. **Functional correctness** — Does the design actually satisfy the functional requirements? Trace the main user flows end-to-end.
3. **Data model** — Entities, relationships, access patterns. Does the storage choice fit the access patterns and consistency needs?
4. **API / interface design** — Clear contracts, versioning, idempotency, pagination, error semantics.
5. **Scalability (right-sized)** — Does it meet the *projected* load with reasonable headroom — without over-building? Flag both premature scaling and genuine bottlenecks.
6. **Reliability & availability** — Single points of failure vs. the availability target. Redundancy, failover, degradation behavior.
7. **Consistency & correctness under concurrency** — Consistency model vs. requirements. Race conditions, idempotency, exactly/at-least-once semantics.
8. **Performance** — Latency budget across the critical path. Caching strategy and invalidation. Hot paths.
9. **Security & privacy** — AuthN/AuthZ, data protection, secrets, tenancy isolation, compliance (PII, audit) as required.
10. **Cost** — Infra and operational cost vs. the value/stage. Is the spend proportionate?
11. **Operational complexity** — Can the team actually run this? Deploy, on-call, runbooks. Complexity vs. team size and maturity.
12. **Failure modes & recovery** — What happens when each dependency fails? Backpressure, retries, timeouts, circuit breakers, data backup/restore, DR.
13. **Observability** — Metrics, logging, tracing, alerting tied to the SLOs.
14. **Tradeoffs & alternatives** — Were the key decisions justified? Were simpler alternatives considered and ruled out for a stated reason?

## Right-sizing lens (apply across all dimensions)
For every recommendation, ask: *does the requirement justify this?* Prefer managed services over custom infra, a single well-run datastore over many, vertical scale + simple replication over distributed systems — until the requirements demand otherwise.
