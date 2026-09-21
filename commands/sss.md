---
description: End a session. Record state in files so the next session resumes without this conversation.
---

# sss: end a session

Leave the project so the next session, in any tool, resumes from files and not from this conversation.

State should already have been committed as it changed. `sss` is the check that nothing meaningful is left uncommitted or unrecorded.

## 1. Update the records

Always, in `docs-root`:

- `tasks.md`: every task touched this session shows its real status, and the next task is visible.
- `session.md`: what is true now, what is open, and the exact point to restart from.

Only when something meaningful changed:

- `discussion.md`
- `journal/`
- `research/`
- `handoff.md`
- `deliverables.md`
- `README.md`, when setup, usage, structure, or entry points changed

## 2. Commit

Commit the record updates and any remaining work, following the project's commit rules.

## 3. Check

Run `git status`. If anything is uncommitted, or the records are out of date, say plainly that the work is still in progress and name the next cleanup action. Do not report the session as closed.

## 4. Show the owner

Show the current task list, or the part of it that changed, with the next active task first.
