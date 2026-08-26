# Project Continuity Workflows

Use only the mode relevant to the request. Do not mutate the repository when the user asked only for an
assessment, explanation, or proposal.

## Bootstrap

1. Inspect repository instructions, top-level files, existing docs, version-control status, recent history,
   source layout, tests, and build tooling.
2. Select the output language using the policy in `SKILL.md`; for a new project, default to Simplified Chinese.
3. Infer project maturity and continuity risks. Ask only when a missing product choice would materially change
   the structure.
4. Choose the smallest profile from `document-system.md` that gives each necessary fact one owner.
5. Reuse established names and conventions. If no convention exists, create a clear entry point and a dynamic
   status artifact before adding deeper documents.
6. Reconstruct facts from evidence; label uncertain conclusions rather than inventing history or rationale.
7. Add repository-local instructions that tell future agents or contributors how to resume and hand off.
8. Validate links, formatting, stated commands, language consistency, and consistency with the current worktree.

Do not manufacture ADRs for decisions whose history cannot be recovered. Record the current rule and mark its
original rationale unknown, then improve it when evidence appears.

## Continue

1. Read repository-level instructions and the documentation entry point.
2. Read current status, the active milestone, and the authoritative design/decision records it references.
3. Inspect version-control status and diff before touching files; existing changes may be newer than status.
4. Inspect relevant code and tests, then run safe, proportionate checks when needed to verify claims.
5. Establish the current outcome, three-dimensional capability state, unresolved decision, next action, and
   worktree condition.
6. Follow the user's current request. It may replace the recorded next action, but does not erase prior decisions
   or authorize unrelated cleanup.

If the handoff is stale, first correct the project memory or explicitly record the discrepancy. Do not restart a
partially completed task merely because its originating conversation is unavailable.

## Handoff

Before updating decision-bearing artifacts, apply the decision-authority and acceptance gate in `SKILL.md`. If it
is not satisfied, leave project memory unchanged and report the matter as still open or pending synchronization.

Update only artifacts affected by the work:

1. Put the normative mechanism or contract in its design owner.
2. Record a durable cross-cutting decision or an explicit replacement when warranted.
3. Update milestone scope only when scope or sequencing changed.
4. Update the dynamic status with separate design, implementation, and verification state.
5. Record unresolved questions with constraints, candidates, current leaning if any, and closure criteria.
6. Record one next concrete action where the work has a clear sequence.
7. Link implementation and verification evidence rather than claiming completion abstractly.
8. Search for stale terminology, conflicting rules, and duplicated authoritative prose.
9. Run format/link checks and risk-appropriate tests. Report commands actually run; do not imply unrun checks.
10. Report uncommitted changes, blockers, and deliberately deferred work.

A routine implementation should not force updates to every document. Use the change-to-owner mapping in
`document-system.md`.

## Audit or migrate

1. Inventory existing artifacts and identify the fact each currently owns.
2. Find duplication, orphaned decisions, ambiguous status words, stale plans, and claims unsupported by code or
   tests.
3. Map existing artifacts to roles rather than renaming them for cosmetic uniformity.
4. Propose the minimum structural changes that close real continuity gaps.
5. Preserve history and user-authored work. Introduce redirects or indexes when moving authoritative content.
6. Reconcile contradictions explicitly. If intent cannot be inferred safely, present the exact conflict and ask
   for the missing decision.
7. Leave a documented reading order and handoff protocol inside the repository.

When splitting, moving, or renaming authoritative documentation:

1. Inventory the source headings, inbound links, relative references, and the fact owner for every section.
2. Move normative content to its new owner; do not leave a second complete authoritative copy behind.
3. Preserve a concise overview or navigation entry when callers still need the former conceptual starting point.
4. Update the entry point, architecture, status, roadmap, decision/ADR indexes, repository instructions, and other
   backlinks affected by the move. Update only artifacts that actually reference or summarize the moved facts.
5. Preserve accepted history and rationale. If content is intentionally summarized or retired, make that boundary
   explicit rather than silently dropping it.
6. Validate both relative file targets and heading anchors, then search for stale terminology and former authority
   claims. Report any redirects or compatibility links deliberately left in place.

## Quality review

Check these observable properties:

- A newcomer has one obvious starting point.
- Current status contains no future component presented as implemented.
- Important decisions are findable together with rationale and tradeoffs.
- Open questions are actionable, not vague topic labels.
- There is at most one project-level “next action” unless independent workstreams are explicitly modeled.
- Dynamic status does not duplicate complete designs or decision history.
- Multiple designs have discoverable authoritative scopes and dependencies; an index or design map, when present,
  does not duplicate implementation/verification status.
- Proposed directions, illustrative APIs, and partial agreement are not mislabeled as accepted decisions.
- New documentation uses the selected language consistently; a new project defaults to Simplified Chinese.
- Links resolve and validation evidence matches the present worktree.
