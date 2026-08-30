# Worked scenario: two agents, one feature, one conflict

**Setup.** Agent A (a coding agent) is implementing an app lock. Agent B (a review agent) is auditing security on the same repo. One owner, reachable but busy.

**1. Claim.** A writes to `session.md`: "working on lib/main.dart (lock gate) and android/MainActivity.kt". B writes: "read-only review of lib/ and android/; no edits".

**2. Finding.** B finds that the lock can never succeed on Android because the activity type is wrong. B does not edit the file (A has claimed it). B records the finding with evidence in `discussion.md` and a task in `tasks.md`: `fix: app lock needs FragmentActivity`, priority `now?`, owner: unassigned.

**3. Handoff.** A reads `discussion.md` at its next checkpoint, accepts the finding, and takes the task. A writes the exact revert step before changing the activity type (a one-line git revert of the coming commit).

**4. Conflict.** B also proposes removing a fallback that A believes is required. Both positions go into `discussion.md` with evidence. Neither edits the other's work. It is an owner decision (it changes safety posture), so it waits, queued in `tasks.md` with what is needed to decide.

**5. Owner returns.** The owner reads the two positions, decides, and the decision is logged with a date. The losing position is not re-argued next session.

**6. Rollback.** A's change breaks the debug build (a configuration-time guard fired for all builds). Verification fails, which is a rollback trigger. A reverts using the recorded step, records what happened, and fixes the guard properly in a second, reviewed commit.

**7. Close.** `sss`: tasks updated with completion notes (what shipped, commit refs, the deviation), the session file updated, the owner shown the current task list.

What made it work: claims before edits, evidence in files rather than chat, a decision that belonged to the owner waiting for the owner, and a revert step written before the risky change.
