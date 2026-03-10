# spec-brainstormer

A Claude Code plugin that guides developers through structured requirements brainstorming. It asks clarifying questions, challenges assumptions, and produces technical specs and execution plans — it does **not** generate code.

Designed for teams who want to think clearly before they build.

---

## Installation

**Step 1: Add the marketplace**

```
/plugin marketplace add joel-meesho/claude-plugins
```

**Step 2: Install the plugin**

```
/plugin install spec-brainstormer
```

**Step 3: Invoke the agent**

```
/brainstormer
```

Or just describe what you're working on and Claude will activate the agent automatically.

**To update after new versions are released:**

```
/plugin update spec-brainstormer
```

---

## How to Invoke

The brainstormer agent activates in two ways:

- **Explicit:** Type `/brainstormer` followed by a brief description of your project or idea
- **Automatic:** Mention brainstorming, a new project, feature design, system architecture, or "I have an idea for..." and the agent will engage

---

## What to Expect

A typical session moves through three phases — though you'll never be told which phase you're in. It feels like a conversation, not a form.

**1. Problem understanding**
The agent asks about what you're solving, who it's for, what exists today, and what "done" looks like. Questions come in batches of 3–7, grouped by theme. Expect 1–3 rounds depending on how much context you provide upfront.

**2. Scope narrowing**
Once the problem is clear, the agent helps define v1: what's in, what's deferred, and what the key technical decisions are. It will challenge over-scoping and push for explicit boundaries. It summarizes and asks you to confirm before moving on.

**3. Output generation**
After scope is locked, you choose your output:
- **Technical spec** — a structured markdown document suitable for handing off to another developer or an AI coding tool (Cursor, Claude Code)
- **Execution plan** — ordered milestones with granular, checkboxed tasks
- **Both** — spec first, then plan

---

## Sample Session (Abbreviated)

> **You:** I want to build a Slack bot that summarizes long threads for our team.
>
> **Brainstormer:** Got it — a Slack thread summarizer. A few questions to start:
> 1. Who triggers the summary — any team member, or specific roles?
> 2. Where does the summary go — a reply in the thread, a DM, a dedicated channel?
> 3. Is this for any workspace, or just your team's internal workspace?
> 4. Do you have an existing Slack app or is this starting from scratch?
> 5. Any existing tools you use for this today (even manual ones)?

*(After a few rounds of questions...)*

> **Brainstormer:** Here's what I'm hearing for v1 scope:
> - In: thread summarization triggered by a `/summarize` slash command, summary posted as a thread reply, single workspace
> - Deferred: DM delivery, scheduled summaries, multi-workspace support
> - Key decisions: using Slack's Bolt framework, OpenAI for summarization
>
> Does that feel right, or would you adjust anything?
>
> **You:** Yes, that's right.
>
> **Brainstormer:** Great. Would you like a technical spec, an execution plan, or both?

---

## What It Produces

**Technical spec** (`SPEC.md` or similar)
Covers: overview, system architecture, features with behavior and error handling, data model, security and access control, testing notes, and a backlog of deferred items. Detailed enough that another developer or AI tool can implement from it.

**Execution plan** (`PLAN.md` or similar)
Ordered milestones grouped by architectural layer (setup → data layer → integration → wiring → hardening). Each milestone has granular checkboxed tasks and a "complete when" exit criterion.

---

## MCP Integration

The agent uses MCP tools you already have configured. If you reference a Confluence doc, Jira ticket, or GitHub repo during the session, the agent will fetch and incorporate that context.

It will always ask before fetching: *"Do you have any existing docs I should review?"* — it never proactively searches.

---

## Guardrails

- Will not write implementation code — it redirects to Cursor or Claude Code for that
- Will not guess at technical details it doesn't know — it asks instead
- Will not generate a spec until enough clarity exists — but uses judgment, not rigid gates

---

## License

MIT
