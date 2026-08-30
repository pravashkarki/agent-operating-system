# Agent Strategy Documents

## Purpose

This file defines the shared operating rules for strategy documents created by the owner and agents working under this operating system.

It applies to internal and team-facing documents that set direction, explain decisions, or prescribe execution. Examples include card briefs, standards documents, audit reports, content or deliverable briefs, decision memos, team announcements, and client communication drafts.

It does not govern public writing such as blog posts, LinkedIn posts, articles, newsletters, or other writing meant for a broad outside audience.

Project-level `AGENT_PROJECT.md` files may add stricter local rules, examples, and templates, but they must not weaken the rules in this file.

## When To Read This

Read this file whenever the task involves drafting or revising:

- a brief that tells people what to do
- a standard or process document
- an audit report
- a content or deliverable brief
- a decision memo
- a team announcement
- a client communication draft written for the owner to review and send

## Core Writing Rules

### Direct

The first sentence should do work. Do not spend the opening warming up.

Avoid openings such as:

- "I have been thinking about"
- "In today's fast-paced world"
- "Let me walk you through"

### Precise

Say what is meant. Do not hedge clear claims into vagueness.

Avoid phrases such as:

- "may possibly"
- "might perhaps"
- "it could potentially be considered"

### Grounded

Material claims must come from something verifiable. If a claim cannot be grounded, do not present it as fact.

### Prescriptive

Internal strategy documents should tell the reader what to do, what to avoid, and how to tell whether the work is done. They are instructions, not reflective essays.

### Specific

Use exact numbers, exact files, exact tools, exact paths, and exact workflow names when the audience can act on them. Specificity is useful in internal documents.

### Concise

If a paragraph can be removed without losing information, remove it. Thorough is good. Padded is not.

### Never

- em dashes
- AI filler such as "in conclusion", "it is worth noting", "when it comes to", "delve", "tapestry", "landscape of", "plethora", "seamlessly"
- marketing cliches such as "game-changer", "paradigm shift", "unforgettable"
- narrative padding such as "Let me explain", "As you can see", "Now that we have covered that"

## Grounding Rule

Every material claim in a strategy document must trace back to a primary source.

Primary sources include:

- audit or measurement output
- database or query results
- API responses
- direct inspection of a live system, page, artifact, or workflow
- local code, config, or repository inspection
- explicit team or client input recorded in a message, note, or meeting record
- prior approved documents with named sources

Not primary sources:

- remembered facts that were not re-checked
- generic best practices with no named source
- unsupported inference
- uncited benchmarks
- confident wording applied to a guess

When something cannot be grounded, label it as one of:

- assumption worth verifying
- question for the team
- hypothesis

Do not let an unverified sentence become "truth" just because it was written confidently.

## Content Structure

### One Central Idea

Each document should have one central purpose. If a draft is trying to do three jobs, split it.

### Opening

The first two or three sentences should establish:

- what this document is about
- who it is for
- what decision or action it supports

### Body

Follow the logic of the subject, not a decorative template. Each section should add something the previous section did not provide.

### Closing

End on something operationally useful:

- next action
- definition of done
- decision point
- related reference

Do not end by re-summarizing what the document just said unless the summary changes what the reader should do.

### Headers

Use headers only when they help navigation.

### Lists

Use lists only when the content is genuinely list-shaped.

### Examples

Use concrete examples whenever a rule would otherwise stay abstract.

## Audience Modes

### Strategist-Only

Audience:

- the owner (the human in the loop)
- agents working directly with the owner

Allowed:

- internal shorthand
- local file paths
- internal tooling references
- private infrastructure context
- rough or in-progress wording

Not allowed:

- raw secrets
- tokens
- passwords
- private keys
- recovery codes

### Team-Facing

Audience:

- internal team members who need to act on the document

Rules:

- do not reference local paths or private tools the team cannot access
- do not reveal strategist-only workflow details unless they are operationally required for the team
- use links and locations the team can actually open
- write direction-setting content in the owner's voice unless the project defines another approved voice
- keep prescriptive rules actionable with the team's real tools and permissions

### Client-Facing

Audience:

- client contacts

Rules:

- highest review bar
- explicit the owner approval before sending or posting
- no bot voice unless explicitly approved for that client workflow
- no internal reasoning, internal debate, or agency-only notes
- no unsupported numbers or claims

## Review And Approval Workflow

Default path:

1. agent drafts
2. the owner reviews
3. the owner edits or approves
4. only then does the document go to its destination

Usually safe without fresh per-action approval once the content itself is already approved:

- creating a card or todo from the approved brief
- moving a card through an already agreed workflow
- uploading an already approved document to the team's document surface
- reordering already approved work items based on explicit priority direction

Always needs explicit approval:

- posting client-facing content
- sending client emails or messages
- posting team-facing direction that includes judgment, critique, or new strategic rationale
- publishing a decision the team has not yet seen
- any action that would be embarrassing, costly, or confusing to reverse

## Reusable Document Shapes

Project-level files may define stricter local templates. Use these as the shared baseline.

### Card Brief

```text
[Title]

Why: [why this work exists]

Deliverable: [what done looks like]

Dependencies: [what must exist first]

Steps: [only the steps unique to this card]

Cross-reference: [related docs or upstream work]
```

### Standards Document

```text
[Title]

For: [who should use this]

Purpose: [what this standard governs]

[Sections covering the rules, checks, and exceptions]

Examples: [only where examples make the rule easier to follow]

When this is wrong: [how people raise corrections]
```

### Audit Report

```text
[Title]

Date: [YYYY-MM-DD]
Scope: [what was audited]
Method: [how it was checked]

Findings:
- [finding]
- [finding]

Each finding should make clear:
- what was observed
- where the data came from
- whether it is verified, inferred, or assumed
- what action follows, if known

Recommended actions: [specific next actions]
```

### Content Or Deliverable Brief

```text
[Title]

Goal: [what this piece needs to achieve]
Audience: [who it is for]
Inputs: [sources and references]
Constraints: [format, scope, rules, exclusions]
Required elements: [what must appear]
Definition of done: [how to tell it is complete]
```

### Decision Memo

```text
[Title]

Date: [YYYY-MM-DD]
Context: [why a decision was needed]
Options considered: [short list]
Decision: [chosen path]
Rationale: [why this path won]
Owner: [who executes]
Review date: [if it should be revisited]
```

### Team Announcement

```text
[Title]

[What is changing]

[Why it is changing]

[What each affected role needs to do]

[Where feedback should go]
```

## How This Fits Into AOS

This file is part of the shared AOS writing layer for strategy-document work.

The expected integration model is:

- the AOS repo references it in `AGENT_PROJECT.md`
- project repos reference it when a task involves briefs, audits, memos, standards, or team-facing strategy documents
- project-level files add local examples or stricter rules only when needed

## When This Document Is Wrong

Do not silently work around it.

If a rule here repeatedly conflicts with reality, flag it directly with the owner and update the canonical doc deliberately. The point of this file is to reduce drift, not create hidden exceptions.
