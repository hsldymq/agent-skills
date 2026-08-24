# Repository Memory System

The names below describe roles, not mandatory filenames. Preserve an existing coherent vocabulary.

## Artifact roles

| Role | Owns | Must not become |
|---|---|---|
| Project instructions | Resume/handoff protocol and repository-specific working constraints | A duplicate architecture manual |
| Entry point | Reading order and map to authoritative artifacts | A second status report |
| Vision | Product purpose, long-term outcomes, non-goals, stable principles | A current task list |
| Roadmap | Milestone dependencies, scope, non-scope, exit evidence | A date promise or detailed design |
| Architecture | Cross-cutting components, boundaries, ownership, lifecycle, invariants | A live discussion queue |
| Decision record | Durable choice, alternatives, rationale, consequences, reconsideration | A changelog entry for every edit |
| Design/specification | A bounded capability's contract, flows, states, failure semantics, validation | A claim that code already exists |
| Status/handoff | Current snapshot, open questions, evidence, worktree condition, next action | The full historical record |
| Code/tests | Implemented behavior and executable evidence | Proof of undocumented product intent |

An issue tracker, project board, release system, or generated specification may own one of these roles. Link it
clearly and account for offline/access constraints; do not create a competing repository copy without need.

## Scale profiles

### Minimal experiment

- Repository instructions or a concise contributor note;
- one status/handoff document containing goal, facts, decisions, uncertainties, evidence, and next action.

### Maintained application or library

- entry point;
- status/handoff;
- roadmap or milestone section;
- bounded designs;
- decision log or ADR directory for durable choices.

### Long-lived architecture or multi-team system

- all maintained-project roles;
- explicit vision and living architecture;
- indexed ADRs;
- traceability to issues, implementation, tests, benchmarks, fault exercises, and releases as appropriate.

Add a role when its facts change at a different cadence, need a different audience, or repeatedly conflict with
another artifact. Do not add it merely because the template exists.

## Independent capability status

Track at least three axes for material capabilities:

### Design

`Open` → `Discussing` → `Accepted` → optionally `Superseded`

### Implementation

`Not Started` → `In Progress` → `Implemented` → optionally `Removed`

### Verification

Use levels meaningful to the project, for example:

`Not Applicable`, `Not Verified`, `Unit Tested`, `Integration Tested`, `Race Tested`, `Fault Tested`,
`Workload Validated`, `Production Validated`.

Do not compress these axes into “done”. A capability may be Accepted / Not Started / Not Applicable, or
Accepted / Implemented / Unit Tested while still lacking production evidence.

## Decision threshold

Prefer a durable decision record when a choice crosses component boundaries, affects multiple milestones,
changes a public guarantee, has expensive reversal, or involves meaningful alternatives. Keep local names and
low-cost implementation choices in the relevant design or code unless their rationale matters beyond the edit.

A useful record contains:

- problem and context;
- known constraints and assumptions;
- considered alternatives;
- chosen direction and rationale;
- positive effects, costs, and risks;
- validation required;
- triggers for reconsideration;
- replacement relationship when superseded.

## Change-to-owner mapping

| Change | Typical owners to update |
|---|---|
| Product purpose or non-goal | Vision; possibly roadmap/status |
| Milestone scope or order | Roadmap and status |
| Cross-component responsibility or invariant | Architecture, decision record, status |
| Capability contract or failure semantics | Design and status |
| Durable tradeoff changes | New/replacement decision record, index, affected design/status |
| Implementation lands | Status and links from the relevant design when useful |
| New verification evidence | Status and the design's validation evidence |
| Work stops or changes direction | Status/handoff |

Summaries may appear elsewhere, but link to the owner and avoid maintaining two full normative copies.
