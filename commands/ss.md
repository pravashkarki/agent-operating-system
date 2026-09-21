---
description: Start a session. Rebuild working state from files and report before acting.
argument-hint: [subproject]
---

# ss: start a session

Rebuild the working state from files, then report. Change nothing during `ss`.

Scope: $ARGUMENTS

With a scope, this is `ss <subproject>`: work only inside that repo or workstream. With none, cover the whole project.

## 1. Find the project file

Read the first of these that exists at the repository root:

1. `AGENTS.md`
2. `CLAUDE.md`, or whichever native file this tool loads
3. `AGENT_PROJECT.md`, when one project spans several repositories

It names `docs-root`, the folder where task and session state live, and it may redefine any step below. Where it does, follow the project file.

If there is no project file, say so and continue from the shared operating model and the repository state.

## 2. Read the state

Always, from `docs-root`:

1. `overview.md`
2. `tasks.md`
3. `session.md`

With a scope, also read the subproject file if one exists, and the vault files mapped to it.

Only when relevant: `decisions.md`, `handoff.md`, `deliverables.md`, and the parts of `research/` and `meetings/` that bear on the current task.

A missing file is a finding, not a failure. Report it and carry on.

## 3. Verify the repository

Run `git status` in the repository, or with a scope in the mapped repository. Note the branch, uncommitted changes, and commits not yet pushed.

Where `session.md` and the repository disagree, the repository is the fact. Report the difference.

## 4. Report, then stop

- The current state, in two or three sentences.
- The active task and its next step.
- Blockers, and anything stale or inconsistent.

Then wait. Do not start work until the owner says what to do.
