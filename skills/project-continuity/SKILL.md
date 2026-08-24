---
name: project-continuity
description: Establish, continue, audit, or hand off long-running software projects using repository-backed decisions, designs, status, implementation evidence, and verification. Use when work must remain coherent across sessions, models, or contributors; do not invoke for an isolated code change that has no project-governance or continuity need.
---

# Project Continuity

Treat the repository—not conversation history—as the durable project memory. Preserve enough context that a capable new contributor can recover the current goal, accepted decisions, implementation reality, verification evidence, unresolved questions, and next action without the original discussion.

## Choose the mode

- **Bootstrap**: create the smallest useful continuity system for a new or undocumented project.
- **Continue**: recover project state before resuming design or implementation.
- **Handoff**: persist material decisions, implementation facts, evidence, and the next action after work.
- **Audit or migrate**: reconcile an existing documentation system without blindly replacing it.

Read [references/workflow.md](references/workflow.md) for the selected mode. Read
[references/document-system.md](references/document-system.md) when choosing or reconciling repository
artifacts. Read [references/templates.md](references/templates.md) only when creating or substantially
restructuring those artifacts.

## Output language

- Default all newly created project documentation, repository-local instructions, status text, decision records, and user-facing handoffs to Simplified Chinese.
- An explicit language request from the user overrides every default.
- In an existing project with a clear, consistently used primary documentation language, preserve that language unless the user requests a change. Do not translate an established documentation set merely because Chinese is the default for new projects.
- If a project is new or its language is mixed or unclear, use Simplified Chinese. Ask about language only when the choice would cause a substantial migration or the user has supplied conflicting requirements.
- Treat headings and prose in the reference templates as semantic examples. Render them in the selected project language rather than copying their source language mechanically.
- Preserve code identifiers, API names, commands, filenames, protocol terms, and established technical vocabulary where translation would reduce precision. Do not create bilingual documents unless requested or already required by the project.
- Keep the language and terminology consistent across artifacts created or updated in the same project.

## Invariants

- Preserve the user's requested scope. A continuity audit does not authorize code changes, broad document rewrites, commits, issue updates, or external messages.
- Do not persist a discussion outcome as an accepted decision unless the user both explicitly confirms the concrete conclusion and explicitly requests the documentation update. Partial agreement, a current leaning, follow-up questions, or approval of one explanation satisfies neither requirement. If either condition is missing, keep the matter open or discussing and report any pending documentation sync without modifying project memory.
- Inspect existing repository instructions, documentation, version-control state, code, and tests before proposing a structure. Extend a coherent system instead of imposing this skill's preferred names.
- Scale the system to the project. Do not create ceremonial documents that will not own a distinct fact.
- Keep one authoritative home for each fact; summaries link to it instead of duplicating its full content.
- Track design, implementation, and verification independently. Accepted design is not implemented behavior; implemented behavior is not verified behavior.
- Record durable decisions with their context, constraints, alternatives, rationale, consequences, evidence, and reconsideration triggers. Preserve superseded history.
- Treat code and tests as evidence of implementation, not as automatic proof that the intended contract is correct or complete.
- When documentation and repository reality conflict, surface the conflict and resolve the stale source deliberately. Never silently choose whichever is convenient.
- A handoff names one concrete next action when possible and distinguishes blockers from merely open questions.

## Completion test

Before declaring continuity work complete, verify that a new contributor can answer:

1. What outcome and milestone are current?
2. What has been decided, and why?
3. What is actually implemented?
4. What has actually been verified, and how?
5. What remains open or blocked?
6. What is the next concrete action?
7. What uncommitted or conflicting repository state must be preserved?

Run format, link, and relevant project checks in proportion to the changes, then report both evidence and remaining uncertainty.
