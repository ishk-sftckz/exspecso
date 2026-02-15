# plan-one-shot

`plan-one-shot` is Antigravity-style planning and execution.

## Install

Install from this repo via the `skills` CLI:

```bash
npx skills add ishk-sftckz/exspecso --skill plan-one-shot
```

Common options:

```bash
# install globally (user-level)
npx skills add ishk-sftckz/exspecso -g --skill plan-one-shot

# install without prompts (select all agents)
npx skills add ishk-sftckz/exspecso -y -a '*' --skill plan-one-shot
```

## What It Enforces

- planning artifacts first (`task.md`, `implementation_plan.md`, `walkthrough.md`)
- strict review gate before execution
- explicit trigger phrase: `Execute Plan`
- ordered execution with continuous task status updates

## How to use

1. Ask your agent to create a plan for your task(do not ask it to start coding yet, mention plan one shot skill in your prompt).
2. Review the plan artifacts it generates.
3. When you approve the plan, reply with exactly: `Execute Plan`.

Where artifacts go:

- `.exspecso/YYYY-MM-DD-<plan-name>/task.md`
- `.exspecso/YYYY-MM-DD-<plan-name>/implementation_plan.md`
- `.exspecso/YYYY-MM-DD-<plan-name>/walkthrough.md`

## Best For

- features that need clear implementation plans
- multi-step refactors where scope control matters
- everyone who wants predictable plan review before coding
