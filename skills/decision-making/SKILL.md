---
name: decision-making
description: Turn messy input (notes, a Slack thread, a rough idea) into a structured leadership decision document with context, options, tradeoffs, a clear recommendation, and reversibility analysis. Use when a leader needs to frame a decision, write a decision doc/RFC, weigh options, get alignment from stakeholders, or document why a choice was made.
---

# Decision-Making

Help an engineering/org leader turn a rough decision into a crisp, shareable document that drives alignment and a clear call.

## Instructions

### Step 1: Gather the raw material
Take whatever the user gives you — bullet notes, a pasted Slack thread, a one-line idea — and extract:
- **What decision is actually being made?** Sharpen it into a single, answerable question. If the input has several tangled decisions, list them and ask which one this doc is about.
- **Why now?** What's forcing the decision (deadline, incident, opportunity, blocker)?
- **Who cares?** Stakeholders, decision-maker (DRI), and who needs to be informed vs. consulted.

If any of the three above is missing and you can't reasonably infer it, ask **targeted** questions (2–3 max) before writing. Don't interrogate — infer what you can and flag assumptions.

### Step 2: Develop the options
- Identify **2–4 realistic options**. Always include the status-quo / do-nothing option if it's viable.
- For each option, give **honest tradeoffs**: pros, cons, cost (effort/time/$), and key risks.
- Avoid strawman options. Each should be defensible enough that a smart person might pick it.

### Step 3: Assess reversibility (one-way vs. two-way door)
Classify the decision:
- **Two-way door (reversible):** cheap to undo. Bias toward speed — recommend deciding fast and iterating.
- **One-way door (hard to reverse):** expensive or impossible to undo. Bias toward rigor — recommend more diligence, a smaller reversible first step, or an explicit off-ramp.

State which it is and what that implies for how much process the decision deserves.

### Step 4: Make a recommendation
- Pick one option and **say why**, tied to the tradeoffs and the goal — don't just summarize.
- Note the **strongest counter-argument** and why you'd still proceed.
- List **open questions** that must be resolved, each with an owner if known.

### Step 5: Produce the document
Write the doc using the structure in [references/template.md](references/template.md). Keep it tight — a leader should grasp the recommendation in the first 30 seconds (lead with a TL;DR). Use plain language, concrete numbers where possible, and tables for option comparison.

After producing the doc, offer to: (a) draft the Slack/email message announcing it, or (b) tighten it to one page.

## Principles
- **Lead with the recommendation**, then justify. Busy readers read top-down.
- **Be honest about uncertainty** — flag assumptions explicitly rather than hiding them.
- **Match rigor to reversibility** — don't write a 5-page doc for a two-way door.
- **Name the DRI.** A decision without an owner is a discussion.
