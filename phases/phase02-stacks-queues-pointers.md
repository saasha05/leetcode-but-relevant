# Phase 2 — Stacks, Queues & Pointers

**🎯 Purpose**  
Build control-flow and execution-model intuition by connecting stack semantics, recursion behavior, and pointer patterns to production message flows, retries, and workflows.

---

## 📋 Phase Overview

This phase turns interview patterns into mental models for real engineering concerns. You'll work through stacks (call execution, recursion), queues (FIFO logic, BFS), and pointer techniques (two pointers, fast/slow pointers) — but always with an eye toward how these patterns model production behavior.

The weeks progress from fundamental stack semantics (Week 7) through advanced stack patterns (Week 8), queue-based traversal (Week 9), and pointer techniques (Weeks 10-11), culminating in a capstone that combines multiple patterns (Week 12). By the end, you'll read stack traces as stories, not noise, and map queue/BFS and pointer patterns to production message flows and data scans.

The mental model that emerges: **control flow patterns are execution models for systems, not just algorithms.**

---

## 📅 Weeks in This Phase

- [Week 7 — Stack Fundamentals & Call Behavior](../weeks/week07-stacks-fundamentals.md) — Understand how stacks model call execution and recursion
- [Week 8 — Monotonic Stack & Predictive State](../weeks/week08-monotonic-stack.md) — Track next/previous greater/smaller elements for predictive systems
- [Week 9 — Queues & BFS Logic](../weeks/week09-queues-bfs.md) — Model FIFO logic and level-order traversal
- [Week 10 — Two Pointers](../weeks/week10-two-pointers.md) — Scan sorted data, merge intervals, deduplicate efficiently
- [Week 11 — Fast & Slow Pointers](../weeks/week11-fast-slow-pointers.md) — Detect cycles and find midpoints with tortoise-hare technique
- [Week 12 — Mini-Capstone: Control Flow Patterns](../weeks/week12-mini-capstone.md) — Combine stack, queue, and pointer patterns

---

## 🧠 Key Concepts

- **Stack Semantics** — Call stacks, recursion depth, undo systems; spot recursion overflow risks early
- **Monotonic Stack** — Predictive state tracking; time-series alerting, skyline computation, range optimization
- **Queue & BFS** — FIFO processing, level-order traversal; job queues, consumer pipelines, service orchestration
- **Two Pointers** — Convert nested loops to linear scans; stream deduplication, memory compaction, anomaly pairing
- **Fast/Slow Pointers** — Cycle detection, midpoint finding; detect recursion errors, livelocks, workflow cycles

---

## 🔗 Real-World Connections

Where these patterns show up in production:

- **Call Stacks** — Recursion depth risks in tree traversal, parsers, data exporters; iterative refactoring opportunities
- **Async Pipelines** — Queue-driven message flows, consumer patterns, retry logic
- **Workflows** — BFS-style service orchestration, dependency resolution, parallel processing
- **Cycle Detection** — Retrigger loops, cyclic dependencies, livelock prevention in distributed systems
- **Predictive Analysis** — Monotonic stacks for rising trends (CPU, error rates) without full rescans

---

## ✅ Interview Readiness Checklist

After completing this phase, you should be able to:

- [ ] Trace recursion as a stack evolution mentally and reason about base-case termination
- [ ] Identify monotonic patterns in data and sketch their algorithmic equivalents
- [ ] Reason about concurrency and parallel processing using BFS-style layering
- [ ] Express two-pointer invariants clearly and maintain pointer movement conditions
- [ ] Apply tortoise-hare reasoning to debugging cycles in workflows or DAGs
- [ ] Spot and explain hybrid algorithmic patterns in real-world engineering
- [ ] Map queue/BFS patterns to production message flows and data scans
- [ ] Read stack traces as stories, identifying recursion depth and iterative alternatives

---

## 🏁 Phase Completion Criteria

You can look at a nested function and immediately identify if it's pre-, in-, or post-order by behavior. You can design scenarios that merge multiple patterns (stack + queue, or slow/fast pointers + recursion) and explain how they improve clarity or performance. When debugging production issues, you can map queue/BFS and pointer patterns to the actual system behavior.

**Interview readiness:** You should be able to handle medium problems involving stacks, queues, and pointer techniques while explaining how these patterns model real system behavior (call stacks, message flows, cycle detection).

---

## 📊 Phase Stats

- **Total Weeks:** 6
- **Total Points:** 150 pts
- **Estimated Time:** ~12 hours (6 weeks × 2 hours/week)

