# Agent Subproject Template

## Purpose

This file defines how agents and the owner work within a specific subproject, repo, or workstream inside a larger project or workspace.

Use it when a project has multiple active areas with different responsibilities, permissions, outputs, or safety boundaries.

This file is a scoped adapter.

It should stay narrow and operational.

This file narrows the parent project rules for one subproject. The parent project file remains the authoritative entry point for `ss <subproject>` behavior.

Use this file only when a subproject is large or distinct enough to justify its own operating layer.

Do not create it for an existing subproject just to match the template if the current project file already handles that subproject clearly.

## Non-Skippable Rules

- Do not implement before the written plan is reviewed and approved.
- Do not act outside this subproject's owned scope without discussion.
- Do not push to any repo marked `read-only` or `never-push`.
- Do not override project-level decisions silently.
- Warn and discuss before crossing any meaningful boundary or taking a risky action.

## Required Reads

### Always Read

1. parent project file
2. this subproject file
3. `<docs-root>/overview.md`
4. `<docs-root>/tasks.md`
5. `<docs-root>/session.md`

### Read When Relevant

1. `<docs-root>/decisions.md`
2. `<docs-root>/handoff.md`
3. relevant `<docs-root>/research/`
4. relevant `<docs-root>/meetings/`
5. relevant project contracts or design system docs

Read `<docs-root>/decisions.md` whenever the current task touches architecture, workflow, policy, deployment, scope boundaries, or any known past decision area.

## Source Of Truth Order

1. shared operating model at `core/AGENT_USER_TEMPLATE.md`
2. parent project file
3. this subproject file
4. approved contracts or feature specs
5. approved execution plans
6. current code and verified environment state
7. historical notes

## Session Commands

### `ss <subproject>`

Follow the parent project file for the full `ss <subproject>` procedure.

This file defines the scoped reads and boundaries that apply after the parent project file routes into this subproject.

### `sss`

Always update:

- mapped `tasks.md`
- mapped `session.md`

Update only when meaningful:

- mapped `journal/` or project journal if shared
- mapped `research/`
- mapped `handoff.md`

## Project Definition

- `shared-operating-model`: `core/AGENT_USER_TEMPLATE.md`
- `docs-root`: <absolute path where this subproject's vault session files live>
- `what it is`: <what this subproject is>
- `who it serves`: <internal | team-internal | client-facing | public> <optional clarification>
- `current stage`: <idea | planning | active | maintenance | paused | archived>
- `project type`: <single-repo | multi-repo | subproject-based | mixed-workspace>

## Subproject Identity

- `parent project`: <parent project name>
- `repo-path`: <repo path>
- `vault-path`: <vault path>
- `permission`: <writable | read-only | never-push>
- `subproject-file`: <this file path>

## Owned Scope

- `<owned area 1>`
- `<owned area 2>`
- `<owned area 3>`

## Out Of Scope

- `<out of scope 1>`
- `<out of scope 2>`
- `<out of scope 3>`

## Artifact Routing

Every row must be filled or deleted before this file is considered complete.

| artifact-type | destination | visibility | notes |
|---|---|---|---|
| `private-research` | `<vault research path>` | `private` | `<notes>` |
| `approved-decisions` | `<vault decisions path>` | `private` | `<notes>` |
| `active-tasks` | `<vault tasks path>` | `private` | `<notes>` |
| `code` | `<repo path>` | `team-internal` | `<notes>` |
| `team-review-docs` | `<team location>` | `team-internal` | `<notes>` |

## Parallel Work Boundaries

### Owned Paths

- `<owned path 1>`
- `<owned path 2>`

### Shared Paths Requiring Coordination

- `<shared path 1>`
- `<shared path 2>`

### Rule

- Do not change shared contracts without surfacing it.
- Do not edit another workstream's owned area without coordination.
- Define the interface first, then implement in parallel.

## Working Rules

Add only the rules that matter for this subproject, for example:

- branch strategy
- PR process
- testing requirements
- design system usage
- API contract rules
- deployment constraints
- product philosophy path when relevant

## What Not To Do

- Do not use this file for research or task tracking.
- Do not assume this subproject owns neighboring workstreams.
- Do not infer missing permissions or routing rules.
- Do not create duplicate source-of-truth docs when links are enough.
- Do not leave placeholder paths or table rows unresolved in a file that is being used operationally.

## Final Rule

This file should make these things obvious:

- what this subproject is
- what it owns
- what it does not own
- where its memory lives
- what it may change
- what it must not change
- how scoped work starts and ends

If the subproject is too small for this file to add clarity, it should be handled in the main project file instead.

If this file starts becoming a second vault, it is being used incorrectly.
