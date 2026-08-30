# Agent Operating System

A written operating model for working with AI coding agents (Claude Code, Codex, and others) as a small team with one human owner. It is the set of rules I use every day across client and product work; this is the public edition with the personal and client-specific parts removed.

The problem it solves: several agents, several tools, one person. Without a shared contract each session drifts, scope creeps, decisions get re-litigated, and the real record lives in chat history nobody reads. AOS makes the working rules, the memory, and the task state live in files that every tool reads the same way.

## What is in it

- `core/AGENT_USER_TEMPLATE.md` · the operating model itself: plan-first workflow, decision boundaries (what the owner decides, what agents may decide, what agents must never decide alone), one-thing-at-a-time communication, task intake and priority rules, two levels of execution logging, change-impact checks before any change, feature contracts for substantial work, parallel worker packets, session start and session end procedures, and the file layout that keeps project memory outside chat.
- `core/AGENT_EXISTING_PROJECT_ADOPTION.md` · how to adopt the model in a project that already exists without forcing a restructure: adopt the rules first, keep working paths, migrate structure only when structure is the actual problem, back up before structural change.
- `core/AGENT_STRATEGY_DOCS.md` · writing rules for direction-setting documents (briefs, standards, audit reports, decision memos, announcements): direct, decision-first, no filler.
- `templates/AGENT_PROJECT_TEMPLATE.md` · the root bootstrap file a project carries so any agent can start correctly.
- `templates/AGENT_SUBPROJECT_TEMPLATE.md` · the narrower file for a repo or workstream inside a larger project.

Native tool files (`CLAUDE.md`, `AGENTS.md`) are thin adapters that point at these; they are not separate knowledge stores.

## How to adopt it

1. Copy `core/` into a place every tool on your machine can read.
2. Put a filled-in `AGENT_PROJECT_TEMPLATE.md` at the root of a project as `AGENT_PROJECT.md`, and let `CLAUDE.md` / `AGENTS.md` point to it.
3. Decide where durable project memory lives (the model assumes a notes vault plus per-project task, session and decisions files) and name it in the project file.
4. Start every session with the session-start procedure and close every session with the session-end procedure. The point is that the next session, in any tool, can pick up from files rather than from memory.

## Principles in one breath

Plan first. One thing at a time. Prefer reversible over risky. Inspect before you modify. Files over chat. Do not expand scope silently. Do not reopen settled decisions without new evidence. The owner decides direction, scope, releases and trade-offs; agents own analysis, sequencing and routine implementation; anything touching infrastructure, security posture, irreversible data or an agreed decision stops and is surfaced.

## Status

Used daily since April 2026. The private edition carries a dated decisions log; changes to this public edition are made deliberately, not in passing.

Written by [Pravash Karki](https://pravashkarki.com). Licensed under CC BY 4.0: use it, adapt it, credit the source.
