<div align="center">

<img src="assets/exspecso-logo.svg" alt="Exspecso logo" width="300" />

### Write the spec. Ship the work.

</div>

---

I use AI agents for most of my development now. And somewhere between "this is incredible" and "why did it just hallucinate an entire module," I started needing something more reliable than a chat window — but lighter than a full enterprise PM setup.

I was using BMad and GSD. Both are genuinely solid. But I kept hitting walls. I wanted custom workflows, my own file naming, agents that remembered project decisions across sessions without me re-explaining everything. So I built Exspecso to fill those gaps.

The name is a riff on Espresso + Spec. That's the whole idea — you get the caffeinated delivery speed, locked inside the structure of an explicit spec.

---

## The core problem

Most agent-driven workflows break in one of two ways.

Give the agent too much freedom and you get context rot, hallucinated state, architectural spaghetti by session three. Bury it in ceremony and you lose the velocity that made agents worth using in the first place.

Exspecso holds that tension on purpose. Specs define the scope. Artifacts hold the truth. The agent executes inside those boundaries. If something isn't written down in a file, it doesn't exist — not in conversation memory, not implied from prior sessions.

That last part matters more than it sounds. Chat context drifts. Files don't.

---

## How it works

Work flows through a simple chain: **spec → plan → implement → verify**.

You define what to build in a spec (requirements, acceptance criteria). The framework turns that into a bounded execution plan. The agent runs the plan, writes tests, updates the trace. Verification computes from artifacts — not from the agent's memory of what it thinks it did.

Two modes:

**Lite** — fast, minimal. Good for solo projects and early exploration. Stays out of your way.

**Standard** — adds a roadmap backbone, phase tracking, and stricter governance. Good for anything multi-feature or team-facing.

Both modes share the same philosophy. The structure grows when the work demands it, not before.

---

## Core philosophy

**Artifacts are the source of truth.** Every decision, progress update, and alignment point lives in a file. Reviews read artifacts, not intentions.

**Progressive complexity.** No empty template forests at day one. The framework adds structure when you actually need it — not to look thorough.

**Spec-driven execution.** No "just code this." Specs define scope boundaries. Plans derive from specs. Tasks derive from plans. Overengineering is treated as a defect.

**Deterministic over clever.** Structured schemas, explicit contracts, bounded correction loops (RALP). When an agent fails, it fails visibly. No hidden heuristics.

**Verification-first.** Work is done when requirements are satisfied, tests pass, and the trace closes — not when the code exists.

---

## Why not just use BMad or GSD?

I still respect both projects. Exspecso is inspired by them.

But I needed things they couldn't give me: custom command naming that matched my workflow, smarter agent behavior specific to my projects, and a cleaner separation between the framework control plane and the actual delivery workspace. BMad can feel heavy; GSD can feel loose. Exspecso sits between them, with a stronger opinion about artifacts and context management.

If you've used either and found yourself working around their limitations — Exspecso is probably worth trying.

---

If you had to compress this into one line:
> Spec-first delivery with progressive structural gravity, enforced through artifact truth and bounded agent autonomy.

Welcome to Exspecso.
