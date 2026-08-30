# Existing Project Adoption

## Purpose

This document defines how to apply the shared operating model to projects that already exist.

It is for adoption, not idealized greenfield setup.

The default goal is to preserve a working project shape and adopt the new philosophy, rules, and safety boundaries with the least disruptive change necessary.

## Core Rule

For an existing project:

- philosophy first
- structure second

Do not replace a working project structure just to match the new templates.

Adopt the new model at the rule level first.

Only restructure when the current setup creates a real operational problem that cannot be solved cleanly inside the existing layout.

Before making structural changes to an existing project, discuss the change with the owner and get explicit approval.

## What To Inspect First

Before changing anything, inspect:

- current canonical files
- current task flow
- current session or restart flow
- current handoff method
- current decision tracking
- current research location
- current meeting-note location
- current shared-output path
- current repo and agent instruction files

The first job is to understand the existing operating model, not replace it.

## Adoption Order

1. create a full backup or snapshot before structural changes
2. identify the current canonical files by role
3. identify philosophy and rule gaps
4. apply the new rules to the existing files first
5. add only the minimum missing files needed for safe operation
6. restructure only when justified by a real gap
7. archive stale files only after coverage is verified

## Philosophy-Level Gaps To Check

Check whether the existing project is missing any of these:

- plan-first workflow
- approval gates
- non-skippable safety boundaries
- source-of-truth order
- session start and shutdown clarity
- task ownership and delegation rules
- handoff expectations
- artifact routing
- product philosophy reference when the project includes product, UX, or design work
- private vs shared output boundary
- explicit permission boundaries
- warning-before-risk rule

If a gap can be solved by updating the existing files, do that first.

## Canonical File Rule

If the project already has a canonical file for a role, prefer updating it in place.

Examples:

- existing `task.md` or `tasks.md`
- existing `session.md`
- existing `notes.md`
- existing `research.md`
- existing `agent-handoff.md`
- existing `AGENT_PROJECT.md`
- existing `CLAUDE.md`

Do not create a second competing file unless the existing file cannot be adapted cleanly.

## Minimal-Intrusion Adoption

Good existing-project adoption usually looks like:

- keep existing file paths
- tighten roles inside those files
- add missing rules
- add missing source-of-truth order
- add missing task format or handoff contract
- add one local adapter file if needed
- leave location changes for later only if clearly justified

This is the default path.

## When Structural Change Is Justified

Structural change is justified only when the existing project shape causes real problems such as:

- no clear canonical file for an important role
- dangerous duplication of active truth
- no usable session restart path
- no safe place for private research
- no clean boundary between private and shared outputs
- unclear multi-repo or multi-subproject routing
- repeated confusion or breakage caused by the current structure

If those problems are not present, preserve the existing shape.

Even when a structural change appears justified, discuss it with the owner before making it.

## If Structural Migration Is Needed

Only then use the full migration path:

1. create a full backup or snapshot of the existing project state before structural changes begin
2. inspect the current active files first
3. migrate all still-relevant content into the new structure
4. verify that each piece of content now lives in the correct destination
5. make the new files complete enough to become the active source of truth
6. only then archive the old files

If old files are archived during migration, the archive must keep a clear record of:

- what backup or snapshot existed before the migration
- what was moved
- when it was moved
- why it was moved
- where the new canonical files now live

Do not archive first and hope the new structure is complete later.

For an existing project, migration is not finished until the new workflow can resume work without needing the old active files as the primary source.

## Stale File Reconciliation

Any stale file outside the active plan must be handled explicitly:

1. inspect whether it still contains useful information
2. if it does, move that information into the correct canonical files first
3. if that reveals a gap in the main plan, session, decision, handoff, or other canonical files, discuss the gap and fix it there
4. only after coverage is verified should the stale file be archived

Do not leave stale files sitting outside the active workflow without a decision.

## Cross-Agent Alignment Rule

If the existing project already has another agent model, align with it instead of fighting it.

Examples:

- `CLAUDE.md`
- `AGENTS.md`
- Cursor or Copilot instruction files
- project-local custom agent notes

Correct behavior:

- inspect the current model
- preserve what already works
- cherry-pick the new philosophy and rules into the existing model and file structure
- only replace or relocate files when the old shape is actively causing confusion or risk

## Final Rule

For existing projects, success is not “matching the template.”

Success is:

- the project is safer
- the workflow is clearer
- the source of truth is cleaner
- the existing working shape is preserved where practical
- the amount of disruption is proportional to the real problem
