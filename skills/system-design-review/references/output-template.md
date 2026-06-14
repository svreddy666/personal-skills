# System Design Review: [Document / System Name]

**Reviewer:** [name] · **Date:** [YYYY-MM-DD]
**Verdict:** Approve · Approve with changes · Needs major revision · Reject
**One-liner:** [single sentence — the headline takeaway]

## Requirements baseline (what I reviewed against)
- **Scale:** [QPS / data volume / growth / read:write]
- **Latency / availability SLOs:** [...]
- **Consistency / durability:** [...]
- **Constraints:** [team size, timeline, budget, stack, compliance]
- **Assumptions made:** [anything inferred because the doc didn't state it]

## Summary
2–4 sentences: what the design does well, the main risks, and whether it's appropriately sized for the requirements.

## Strengths
- [What's solid and should be kept.]

## Findings

### 🔴 Blockers
- **[Title]** — [issue]. **Impact:** [which requirement it violates]. **Suggestion:** [concrete fix].

### 🟠 Major
- **[Title]** — [issue]. **Impact:** [...]. **Suggestion:** [...].

### 🟡 Minor
- **[Title]** — [issue]. **Suggestion:** [...].

### ⚪ Nits
- [Doc/clarity items.]

## Right-sizing assessment
| Area | Requirement | What the design does | Verdict | Right-sized suggestion |
|------|-------------|----------------------|---------|------------------------|
| [e.g. Sharding] | [~50k rows/day] | [pre-sharded across 16 nodes] | Over-engineered | [single Postgres + read replica] |
| [e.g. Availability] | [99.9%] | [single instance] | Under-engineered | [add replica + failover] |

## Verified claims & research notes
- [Claim from the doc] → [what research confirmed/contradicted, with source].

## Prioritized recommendations
1. [Most important change.]
2. [...]

## Open questions
- [ ] [Question that must be answered to finalize the review.]
