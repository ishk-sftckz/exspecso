---
name: plan-one-shot
description: Create Antigravity-style implementation plans with strict review gates, line-item IDs, and no code changes until the user explicitly says Execute Plan.
---

# Plan One Shot

Replicate Antigravity plan-mode behavior using three artifacts and strict review gates.

## Hard Rules

1. Before approval: plan only. No code edits, no mutating commands, no commits.
2. Always produce or update these artifacts together:
   - `.exspecso/<plan-name>/task.md`
   - `.exspecso/<plan-name>/implementation_plan.md`
   - `.exspecso/<plan-name>/walkthrough.md` (stub only during planning)
3. Match plan depth to scope.
4. Block execution until user says exactly: `Execute Plan`.
5. Do not skip artifact generation even for short tasks.
6. After approval: execute strictly in `task.md` order and update statuses continuously.
7. For existing projects, preserve architecture, naming, folder layout, and dependency choices unless the user asks for a change.
8. Prefer minimal diff; do not introduce new abstractions/libraries unless justified by at least two concrete reuse points or a clear blocker.

## Output Control Rules

- Scope-fit depth: small tasks -> short plans; large tasks -> comprehensive plans.
- No speculative engineering: avoid unrequested future-proofing.
- No vague placeholders like "update logic"; describe exact changes.
- Keep verification realistic and runnable in the current repository.
- Prefer adapting existing modules over creating new ones.
- Keep tool/process notes out of main workstream bullets unless they directly affect implementation steps.

## Required Plan Structure

`implementation_plan.md` must follow this order:

1. Title
2. One-line objective
3. `## Proposed Changes`
4. Workstreams
5. File blocks using this format:
   - `#### [MODIFY] [path/to/file.ts](file:///absolute/path/to/file.ts)`
   - `#### [CREATE] [path/to/new-file.ts](file:///absolute/path/to/new-file.ts)`
6. `## Verification Plan`

Use `---` between major workstreams.

## Artifact Lifecycle

All artifacts for one plan must live under a single date-prefixed folder:

- `.exspecso/YYYY-MM-DD-<plan-name>/`

`<plan-name>` rules:

1. Lowercase.
2. Keep letters, numbers, and spaces before slug conversion.
3. Convert spaces/underscores to `-`.
4. Remove filler words when possible (`the`, `a`, `an`, `for`, `to`, `of`).
5. Keep first 3-6 meaningful words.
6. Max length 36.
7. Collapse repeated `-` and trim edges.

## Replan Decision Gate

For every new request after plan creation, decide first:

- `Decision: Continue Current Plan`
- `Decision: Create New Plan`

Provide one short reason.

Create a new plan when objective/success criteria change materially, a new subsystem is introduced, architecture shifts significantly, or planned updates would rewrite roughly more than 40% of the current plan.

## task.md Template

```markdown
# <Task Name>

## Planning
- [/] Explore codebase and identify gaps
- [/] Write implementation plan

## Execution
- [ ] <work item>
- [ ] <work item>

## Verification
- [ ] <verification item>
```

Rules:
- During planning, keep Planning items as `[/]`.
- Keep Execution/Verification unchecked until execution starts.
- Keep items concise and action-oriented.

## walkthrough.md Planning Stub

```markdown
# <Feature Name> Walkthrough

## Status
Planning complete. Execution not started.

## Planned Scope
- <summary bullet>

## Verification Plan
- See `implementation_plan.md`.
```

## Execution Tracking

After receiving `Execute Plan`:

- Mark Planning items `[x]`.
- Mark exactly one in-progress item as `[/]`.
- Move `[/]` forward one item at a time.
- Never leave more than one `[/]` item.
- End with all checklist items marked `[x]`.

## Response Contract

- If approval is missing, end with:
  `Plan ready for review. Awaiting plan review comments.`
- If approved, start execution and respond with:
  `Execute Plan received. Starting execution from task.md Execution section.`
