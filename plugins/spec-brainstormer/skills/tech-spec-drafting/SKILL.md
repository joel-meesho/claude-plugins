---
name: tech-spec-drafting
description: >
  Generates a structured technical specification document based on the
  brainstorming conversation. Use after problem understanding and scope
  narrowing are complete. Produces a markdown file with architecture,
  requirements, and technical details. Activate when the developer asks
  for a "spec", "technical document", "PRD", or "requirements doc".
---

# Tech Spec Drafting

You are generating a technical specification document based on the
brainstorming conversation so far. The spec should be comprehensive enough
that another developer (or an AI coding tool like Cursor) could use it to
implement the solution without additional brainstorming.

## Pre-Generation Checklist

Before generating, verify you have clarity on:
- [ ] Problem statement and context
- [ ] Target users and their needs
- [ ] v1 scope (what's in, what's deferred)
- [ ] Key technical decisions and their rationale
- [ ] Integration points and dependencies
- [ ] Error handling expectations
- [ ] Security and access control requirements

If any of these are missing, ask the developer to fill the gaps before
generating. Do NOT fill gaps with assumptions.

## Spec Structure

Read the reference template at `references/spec-template.md` for the
recommended structure. The template is a guide, not a rigid format — adapt
sections based on what's relevant to the project.

The spec should include:
- **Overview:** What this is and why it exists (2–3 sentences)
- **Architecture:** System design, components, data flow
- **Configuration / Setup:** What needs to be set up, credentials, environments
- **Features:** Each feature with behavior, inputs, outputs, and error handling
- **Data Model / Schema:** If applicable
- **Security and Access Control:** Who can do what
- **Error Handling:** General approach and specific scenarios
- **Testing Notes:** How to verify the implementation works
- **Backlog:** Deferred features and future considerations

## Writing Style

- Be specific and concrete — avoid vague language like "should handle errors
  appropriately" (say what the error handling should do)
- Include example messages, payloads, or formats where they add clarity
- Use tables for structured information (schemas, config, API endpoints)
- Keep the tone professional but not stiff — this is a working document
- Technical details should be at a high enough level to guide implementation
  without prescribing exact code (e.g., mention Slack API endpoints to use,
  but don't write the HTTP call)

## Output

Generate the spec as a markdown file. After generation, ask the developer:
- "Does this capture everything? Anything to adjust?"
- "Would you also like an execution plan with milestones and tasks?"

## Important

- Do NOT include implementation code in the spec
- Do NOT make up technical details you're unsure about — flag unknowns
- Include specifics that keep the implementation on-track (e.g., API scopes,
  config properties, schema definitions) to prevent scope creep during building
