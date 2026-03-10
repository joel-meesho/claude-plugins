---
name: execution-planning
description: >
  Generates a structured execution plan with milestones and granular tasks
  based on a brainstorming conversation or existing tech spec. Use when the
  developer wants a buildable breakdown of work. Produces a markdown file with
  ordered milestones and checkboxed tasks. Activate when the developer asks for
  a "plan", "task breakdown", "milestones", "execution plan", or "how to build
  this".
---

# Execution Planning

You are generating an execution plan that breaks the project into ordered
milestones and granular tasks. The plan should be actionable enough that a
developer can pick up the first milestone and start building immediately.

## Pre-Generation Checklist

Before generating, verify you have:
- [ ] A clear v1 scope (from the brainstorming conversation or a tech spec)
- [ ] Key technical decisions made
- [ ] An understanding of the developer's preferred milestone style

If a tech spec was already generated in this conversation, use it as the
primary input. If not, use the brainstorming conversation context.

## Milestone Design

Read the reference template at `references/plan-template.md` for the
recommended structure.

**Milestone organization:** Group milestones by architectural layer or
component, not by feature. This means:
- Milestone 1 might be "Project Setup & Configuration"
- Milestone 2 might be "Data Layer" (all read/write operations)
- Milestone 3 might be "Integration Layer" (all external API calls)
- Later milestones wire things together and add polish

This layered approach means each milestone is independently testable and
builds a foundation for the next.

**Each milestone should include:**
- A clear description of what it covers
- Granular tasks as a checkbox list
- A "complete when" statement that defines the testable exit criteria
- Tasks granular enough that each one is a single, concrete action

**Task granularity:** Each task should be one action. Not "set up the database
and seed it with test data" — instead: "create the database schema" and
"seed the database with test data" as separate tasks.

## Output

Generate the plan as a markdown file. After generation, ask the developer:
- "Does this breakdown feel right? Any milestones you'd reorder or split?"
- "Anything missing that you'd want tracked?"

## Important

- Do NOT include code in the execution plan
- Tasks should describe WHAT to do, not HOW to implement it in code
- Flag dependencies between milestones explicitly
- If milestones can be parallelized, note which ones
- Always include a final "Hardening & Cleanup" milestone for error handling,
  edge cases, and documentation
