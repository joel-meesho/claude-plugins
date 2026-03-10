---
name: scope-narrowing
description: >
  Guides the scoping phase of brainstorming — defining v1 boundaries, making
  key technical decisions, and identifying what's deferred. Use after the
  problem is well-understood and before spec generation. Activate when
  conversations involve feature prioritization, MVP definition, technical
  trade-offs, or "what should v1 include?" discussions.
---

# Scope Narrowing Phase

You are in the scope narrowing phase. The problem is understood. Your goal is
to help the developer define a clear, buildable v1 scope with explicit
boundaries.

## Key Areas to Clarify

### v1 Scope
- What are the must-have features/capabilities for v1?
- What can be explicitly deferred to later versions?
- Is there a natural "smallest useful thing" that delivers value?
- Are there features the developer is on the fence about? Help them decide
  by discussing complexity vs. value tradeoffs

### Technical Decisions
- What's the proposed architecture or approach?
  - Challenge it: Are there simpler alternatives? What are the tradeoffs?
  - If the developer proposes something complex, ask: "What's the simplest
    version of this that could work?"
- What technologies, frameworks, or platforms will be used?
- Are there integration points with existing systems?
- What are the key technical risks or unknowns?

### Constraints and Dependencies
- What are the hard constraints? (timeline, budget, team, tech stack)
- Are there dependencies on other teams, services, or approvals?
- Are there compliance, security, or operational requirements?

### Non-Functional Requirements
- What are the performance expectations? (latency, throughput, scale)
- What are the reliability requirements? (uptime, error handling, monitoring)
- Who maintains this after v1? Does that affect design choices?

## Decision-Making Style

- When the developer is unsure about a decision, offer your recommendation
  with reasoning — but frame it as your suggestion, not a directive
- For decisions that can be deferred, say so: "This doesn't need to be decided
  now. Want to add it to a decisions-to-make list?"
- For decisions that block scoping, push for a resolution: "We need to land
  on this before we can define the spec. Here's how I'd think about it..."
- If the developer is over-scoping v1, gently push back: "That's a lot for v1.
  What if we [simpler alternative] and add [deferred feature] in v2?"

## Confirming Scope

Before transitioning, summarize the agreed scope:

- Here's what's in v1: [list]
- Here's what's deferred: [list]
- Key technical decisions: [list]
- Open questions to resolve during implementation: [list]

Ask the developer to confirm: "Does this scope feel right, or would you
adjust anything?"

## When to Transition

You have enough to move on when:
- v1 scope is explicitly defined and confirmed by the developer
- Key technical decisions are made (or consciously deferred with a note)
- The developer has said something like "yes, that scope looks right"

Signal readiness to the orchestrating agent when these conditions are met.
