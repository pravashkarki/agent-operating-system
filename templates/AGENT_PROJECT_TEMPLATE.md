# Agent Project Template

## Purpose

This file defines how agents and the owner work within this specific project or workspace.

It is a project-level adapter for the shared operating model.

Use it directly for:

- new projects
- projects that already fit this shape
- existing projects only when a fuller structural migration is justified

For existing projects that already have a workable operating shape, use `core/AGENT_EXISTING_PROJECT_ADOPTION.md` first and preserve the current structure where practical.

It should stay thin, practical, and operational.

It should not become the place where research, brainstorming, or duplicate task tracking accumulates.

This is the root bootstrap file for the repo. A new session should inspect this file before interpreting project shorthand such as `ss` or taking meaningful project action.

Project-local session command definitions in this file override the abstract command behavior in the shared operating model for this project.

## Non-Skippable Rules

- Do not implement before the written plan is reviewed and approved.
- Do not bypass the approved deployment method.
- Do not edit servers directly unless that path is explicitly approved for this project.
- Do not change firewall, DNS, proxy, router, or other infrastructure rules without explicit written approval.
- Do not push to any repo marked `read-only` or `never-push`.
- Do not override an agreed decision silently.
- Warn and discuss before crossing any meaningful boundary or taking a risky action.

## Required Reads

### Always Read

1. this file
2. `<docs-root>/overview.md`
3. `<docs-root>/tasks.md`
4. `<docs-root>/session.md`

### Read When Relevant

1. `<docs-root>/decisions.md`
2. `<docs-root>/handoff.md`
3. `<docs-root>/deliverables.md`
4. relevant `<docs-root>/research/`
5. relevant `<docs-root>/meetings/`
6. relevant subproject file
7. relevant project-specific docs

Read `<docs-root>/decisions.md` whenever the current task touches architecture, workflow, policy, deployment, scope boundaries, or any known past decision area.

## Source Of Truth Order

1. shared operating model at `core/AGENT_USER_TEMPLATE.md`
2. this project file
3. relevant subproject file
4. approved product philosophy
5. approved product specs and contracts
6. approved execution plans and task systems
7. current code and verified environment state
8. historical notes

## Session Commands

### `ss`

1. Read this file.
2. Read `<docs-root>/overview.md`, `<docs-root>/tasks.md`, and `<docs-root>/session.md`.
3. Read additional relevant files only when needed.
4. Check git status in relevant repo areas.
5. Summarize the current state, blockers, and next step.

### `ss <subproject>`

1. Read this file.
2. Read the subproject file if one exists.
3. Read the mapped subproject vault files.
4. Check git status in the mapped repo.
5. Summarize the scoped state, blockers, and next step.

### `sss`

Always update:

- `tasks.md`
- `session.md`

Update only when meaningful:

- `discussion.md`
- `journal/`
- `research/`
- `handoff.md`
- `deliverables.md`
- `README.md` when repo-facing orientation, setup, usage, structure, or entry points materially changed

Default close-out behavior:

- update the relevant task state before ending the session
- make the next active or remaining task visible
- show the owner the current task list or the relevant updated task section by default
- if the worktree is still dirty or the project records are stale, say the work is still in progress and identify the next cleanup action

## Project Definition

- `shared-operating-model`: `core/AGENT_USER_TEMPLATE.md`
- `docs-root`: <absolute path where this project's vault session files live>
- `what it is`: <what this project is>
- `who it serves`: <internal | team-internal | client-facing | public> <optional clarification>
- `current stage`: <idea | planning | active | maintenance | paused | archived>
- `project type`: <single-repo | multi-repo | subproject-based | mixed-workspace>
- `product-philosophy`: <path, defaults to `<path-to-your-product-philosophy.md>`, or `none`>

## Repo Permissions

Use this section for simple single-repo projects.

- `<repo-or-root-path>`: <writable | read-only | never-push>

If this is a multi-repo or multi-subproject project, use the Subproject Mapping table instead.

## Subproject Mapping

Use this section only when the project has multiple active repos or subprojects.

| name | purpose | repo-path | vault-path | permission | subproject-file |
|---|---|---|---|---|---|
| `<name>` | `<purpose>` | `<repo-path>` | `<vault-path>` | `<writable/read-only/never-push>` | `<path-or-none>` |

Create a subproject file only when the subproject has distinct rules, permissions, ownership, workflow, source-of-truth needs, deployment path, or parallel work boundaries that are too large to keep clearly inside the main project file.

## Artifact Routing

Every row must be filled or deleted before this file is considered complete.

| artifact-type | destination | visibility | notes |
|---|---|---|---|
| `private-research` | `<vault research path>` | `private` | `<notes>` |
| `approved-decisions` | `<vault decisions path>` | `private` | `<notes>` |
| `active-tasks` | `<vault tasks path>` | `private` | `<notes>` |
| `meeting-notes` | `<vault meetings path>` | `private` | `<notes>` |
| `shared-proposals` | `<shared location>` | `shared` | `<notes>` |
| `team-review-docs` | `<team location>` | `team-internal` | `<notes>` |
| `implementation-tasks` | `<tracker>` | `team-internal` | `<notes>` |
| `code` | `<repo path>` | `team-internal` | `<notes>` |

## Vault Structure

Use this root structure:

- `overview.md`
- `tasks.md`
- `session.md`
- `handoff.md`
- `decisions.md`
- `journal/`
- `research/`
- `meetings/`
- `archive/`

Optional:

- `deliverables.md`
- subproject folders when needed

All of the above live under `<docs-root>/`.

## Project-Specific Rules

Add only the rules that are actually needed here, for example:

- deployment method
- forbidden deployment methods
- testing expectations
- branch strategy
- contract requirements
- design system requirements
- client or team boundaries
- path-level permission overrides when a single repo has mixed write boundaries

## Git Workflow

Define the git workflow for this project when git is part of normal execution.

Recommended fields:

- branch strategy
- branch naming
- whether direct push is allowed
- protected branches
- PR requirements
- review expectations
- CI gates
- merge strategy
- deploy-triggering branches

If the project has no meaningful git workflow yet, state that explicitly instead of leaving agents to guess.

## README

Define how this project's `README.md` should be treated.

Recommended rule:

- `README.md` is the repo-facing orientation file
- it should explain what the project is, how to get started, and where the canonical operating docs live
- it should be updated when repo-facing setup, structure, usage, or entry points materially change
- it should not become a second task board, session log, or research store

## What Not To Do

- Do not put research, task tracking, or evolving notes in this file.
- Do not duplicate source-of-truth docs when linking is enough.
- Do not create subproject files just because a folder exists.
- Do not let agents infer permissions, vault paths, or routing rules.
- Do not leave placeholder paths or table rows unresolved in a file that is being used operationally.

## Final Rule

This file should make these things obvious:

- what the project is
- where memory lives
- what the boundaries are
- what is safe
- what is forbidden
- how work starts
- how work ends
- how outputs are routed

If this file starts becoming a second vault, it is being used incorrectly.
