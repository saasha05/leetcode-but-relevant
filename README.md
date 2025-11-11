# LeetCode But Relevant

> A 42-week curriculum that connects algorithmic thinking to real-world engineering for senior and lead engineers.

---

## What This Is

This is not another LeetCode grind. It's a structured curriculum designed for **practicing engineers** who need to refresh their algorithmic intuition and pass serious technical interviews, without losing sight of how these concepts actually matter in production systems.

**Time commitment:** ~2 hours per week for 42 weeks.

**Target audience:** Mid to senior engineers who are strong in real-world engineering but rusty on interview-style problems.

---

## Why It's Useful

Most LeetCode prep treats algorithms as abstract puzzles. This curriculum treats them as **mental models for system design, performance optimization, and architectural decision-making**.

Every week connects patterns to real engineering scenarios:
- Hash maps → caching strategies and session stores
- Stacks → call stacks, recursion depth, and undo systems
- Graphs → service dependencies, migration DAGs, and failure domains
- Dynamic programming → rollout strategies and resource allocation
- Binary search → threshold tuning and adaptive control

You'll build interview readiness while strengthening your ability to reason about production systems.

---

## Curriculum Overview

The curriculum is organized into **6 phases**, each building specific engineering intuition:

| Phase | Weeks | Focus | Interview Readiness |
|-------|-------|-------|---------------------|
| [Phase 1: Arrays, Strings & Hashing](phases/phase01-arrays-strings-hashing.md) | 1–6 | Computational intuition, complexity analysis, hash-based structures | Can reason about hot paths, caching, and data layout issues |
| [Phase 2: Stacks, Queues & Pointers](phases/phase02-stacks-queues-pointers.md) | 7–12 | Control flow, execution models, recursion patterns | Reads stack traces as stories; maps patterns to message flows |
| [Phase 3: Trees & Graphs](phases/phase03-trees-graphs.md) | 13–18 | Graph-thinking as default lens for systems | Can model service dependencies, DAGs, and hierarchies |
| [Phase 4: Dynamic Programming](phases/phase04-dynamic-programming.md) | 25–30 | Architecture and optimization through memoization | Can explain DP reasoning in rollout, scheduling, and cost management |
| [Phase 5: Binary Search, Heaps & Intervals](phases/phase05-binary-search-heaps-intervals.md) | 31–36 | Performance tuning, prioritization, scheduling | Can design job schedulers, query plans, and rate limiters |
| [Phase 6: Integration & Mock Interviews](phases/phase06-integration-mock-interviews.md) | 37–42 | Synthesis and interview simulation | Ready for full interview panels with tradeoff narration |

---

## How to Use This

1. **Start with a phase.** Each phase file provides context, links to weeks, and interview-readiness checklists.
2. **Follow the weeks.** Each week has study materials, deliverables, and reflection prompts.
3. **Track your progress.** Points are for self-accountability, not grading (~1000 total across the curriculum).

---

## Philosophy

- **Respects your time:** No hand-holding tutorials or walls of code.
- **Assumes competence:** Written for peers, not students.
- **Connects to reality:** Every concept tied to production systems.
- **Focuses on judgment:** Not just solving problems, but reasoning about tradeoffs.

---

## Structure

- **`weeks/`** — Individual week files with objectives, materials, and deliverables
- **`phases/`** — Phase-level overviews with interview-readiness checklists
- **`templates/`** — Templates for creating new weeks or phases
- **`AGENTS.md`** — Internal guide for maintainers and AI agents

---

## Getting Started

1. Read the [Phases Overview](phases/README.md)
2. Read the [Phase 1 overview](phases/phase01-arrays-strings-hashing.md)
3. Start with [Week 1](weeks/week01-arrays-complexity.md)
4. Complete deliverables and reflections each week
5. Use phase checklists to gauge readiness before moving forward

---

*This curriculum is designed for engineers who want to pass interviews without becoming LeetCode grinders. Every pattern connects back to real systems you've built or will build.*
