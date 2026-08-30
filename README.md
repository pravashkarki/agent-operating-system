# Agent Operating System

## In two minutes

- **What:** a written operating model for working with AI coding agents (Claude Code, Codex, and others) as a small team with one human owner. Rules, decision boundaries, session procedures, and a file layout that keeps project memory outside chat.
- **Why:** several agents, several tools, one person. Without a shared contract every session drifts, scope creeps, settled decisions get reopened, and the real record lives in chat history nobody reads.
- **First step:** copy `templates/AGENT_PROJECT_TEMPLATE.md` into a project as `AGENT_PROJECT.md`, fill in the paths, create `tasks.md` and `session.md` where it points, and start your next session with `ss`.

This is the public edition of a system used daily since April 2026; personal and client-specific details are removed.

## What is in it

- `core/AGENT_USER_TEMPLATE.md` · the operating model: plan-first workflow (with a defined lighter mode), decision boundaries (what the owner decides, what agents may decide, what agents must never decide alone), one-thing-at-a-time communication, task intake and priority, two levels of execution logging, change-impact checks, feature contracts, parallel worker packets and agent-to-agent conflict rules, cost budgets, untrusted input, outages, owner absence, rollback, onboarding and retiring rules, code security, and the session commands.
- `core/AGENT_EXISTING_PROJECT_ADOPTION.md` · adopting the model in a project that already exists: rules first, keep working paths, restructure only when structure is the actual problem, back up before structural change.
- `core/AGENT_STRATEGY_DOCS.md` · writing rules for direction-setting documents: briefs, standards, audit reports, decision memos, announcements.
- `templates/AGENT_PROJECT_TEMPLATE.md` · the root bootstrap file a project carries so any agent can start correctly.
- `templates/AGENT_SUBPROJECT_TEMPLATE.md` · the narrower file for a repo or workstream inside a larger project.
- `examples/` · one filled-in project file and one worked two-agent scenario (handoff, conflict, rollback).

Native tool files (`CLAUDE.md`, `AGENTS.md`) are thin adapters that point at these; they are not separate knowledge stores. A minimal adapter is three lines:

```
# CLAUDE.md
Read AGENT_PROJECT.md first and follow it. It defines the session commands, the source-of-truth order, and where task and session state live.
```

## The session commands

- `ss` starts a session: read the project file, the current task list and session state, verify repo state, and report before touching anything.
- `ss <subproject>` does the same scoped to one repo or workstream.
- `sss` ends a session: update task state and the session file first, then the durable notes that changed, then show the owner the current task list.

Both are defined in the operating model and can be renamed per project; the point is that the next session, in any tool, resumes from files rather than from memory.

## How to adopt it

1. Put `core/` somewhere every tool on your machine reads: a copy in the repo, a shared local folder, or a symlink.
2. Add `AGENT_PROJECT.md` to the project root (from the template) and let `CLAUDE.md` / `AGENTS.md` point at it.
3. Create the durable state files it names. "Vault" means any durable, shared file location: a notes vault, a `docs/` folder in the repo, or a tracker, as long as it is written to and read from every session. Set `docs-root` to that path.
4. Run `ss` at the start and `sss` at the end of every session.

Start small: one project file, `tasks.md`, `session.md`. Grow into the fuller structure when the project's complexity asks for it.

## Principles in one breath

Plan first. One thing at a time. Prefer reversible over risky. Inspect before you modify. Files over chat. Do not expand scope silently. Do not reopen settled decisions without new evidence. The owner decides direction, scope, releases and trade-offs; agents own analysis, sequencing and routine implementation; anything touching infrastructure, security posture, irreversible data, or an agreed decision stops and is surfaced.

## Status and limits

Used daily since April 2026 by one owner with two to four agents across client and product work (web, mobile, infrastructure). It has not been tested with large teams or with agents that act without a human in the loop. The private edition carries a dated decisions log; changes here are made deliberately, not in passing.

Written by [Pravash Karki](https://pravashkarki.com). Licensed under CC BY 4.0: use it, adapt it, credit the source.
