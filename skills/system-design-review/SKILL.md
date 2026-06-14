---
name: system-design-review
description: Review a system design document and produce a structured, right-sized critique. Reads the design, infers the real requirements and scale, researches the technologies and claims involved, then reviews the design against what it actually needs to do — not against hyperscale ideals. Use when asked to review/critique a system design doc, design RFC, architecture proposal, or HLD/LLD, or to sanity-check a proposed architecture.
---

# System Design Review

Review a system design document the way a strong, pragmatic staff engineer would: understand what's being built, calibrate to the **actual** requirements, verify the technical claims, and give a critique that is specific, fair, and right-sized.

The single most important rule: **review the design against what it must do, not against what you'd build for Google.** If we're building for a B2B SaaS like Highspot, do not recommend Facebook-scale architecture. Over-engineering is a defect, not a virtue.

## Instructions

### Step 1: Understand the document
Read the whole document first. Extract and write down:
- **Problem & goals** — what is being built and why. Note explicit **non-goals**.
- **Functional requirements** — what the system must do.
- **Non-functional requirements** — scale (QPS/throughput, data volume & growth, read/write ratio), latency SLOs, availability target, consistency/durability needs.
- **Constraints** — team size, timeline, budget, existing stack, compliance.
- **Proposed design** — components, data stores, APIs, data flow, and the key decisions/tradeoffs the author made.

If the doc lacks the requirements or scale context needed to judge it, that is your **first finding** — you cannot right-size a review without it. State the assumptions you'll review against, or ask 2–3 targeted questions before proceeding.

### Step 2: Establish the "required scale" baseline
Before critiquing, decide what "good enough" actually is for *this* system:
- Estimate the real targets from the business context: expected users/QPS, data size & growth, peak vs. average load, latency and availability SLOs.
- Anchor on the product's **stage and type**. Enterprise B2B SaaS, internal tools, and consumer social networks have wildly different needs. A system serving thousands–low-millions of users does not need planet-scale infrastructure.
- Write the baseline down explicitly. Every recommendation later is measured against this, not against an abstract ideal.

### Step 3: Research the topics
- List the technologies, patterns, and specific claims in the doc that should be verified (database capabilities, queue semantics, caching, consensus, vendor SLAs, scaling limits, cost).
- Research the ones you are not certain about — real capabilities, limits, failure modes, operational cost, and common pitfalls. Prefer authoritative/primary sources (official docs, well-known engineering write-ups).
- Do **not** assert vendor-specific numbers or limits from memory — verify them. Separate verified facts from your own judgment in the review.

### Step 4: Review across dimensions
Work through the dimensions in [references/review-rubric.md](references/review-rubric.md). For each, assess **fit to the requirement**, not conformance to an abstract ideal. Note both strengths and gaps.

### Step 5: Right-sizing pass (the headline check)
Explicitly scan for mis-sizing in **both** directions:
- **Over-engineering** — patterns that exceed the stated requirements: premature sharding, multi-region for a single-region product, microservices for a tiny team, custom infra where a managed service suffices, exotic datastores for modest load.
- **Under-engineering** — places the design will not meet its stated requirements (a single point of failure against a 99.9% target, no backpressure on an unbounded queue, etc.).

For each, state: the **requirement** → what the **design does** → the **right-sized alternative**. The goal is the simplest design that meets the requirements with reasonable headroom.

### Step 6: Produce the review
Write the review using [references/output-template.md](references/output-template.md). Lead with a one-line **verdict** and a short summary, then findings grouped by **severity** (Blocker / Major / Minor / Nit), the right-sizing assessment, prioritized recommendations, and open questions. Every issue must include a concrete, actionable suggestion.

After delivering, offer to: (a) draft inline comments for the doc, or (b) propose a revised architecture sketch addressing the blockers.

## Principles
- **Right-size to requirements.** Calibrate to actual scale, stage, team, and timeline. The Highspot-not-Facebook rule applies to every recommendation.
- **Simplest design that meets the requirements wins.** Complexity must be justified by a real requirement.
- **Verify, don't assert.** Research technical claims; separate facts from opinion.
- **Be specific and actionable.** No vague "consider scalability" — name the issue, the impact, and the fix.
- **Severity reflects impact on meeting the requirements**, not how interesting the problem is.
- **Acknowledge strengths**, not just problems. A review is calibration, not a teardown.
