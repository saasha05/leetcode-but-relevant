# Phase 5 — Binary Search, Heaps & Intervals

**🎯 Purpose**  
Encode performance tuning, prioritization, and scheduling by showing how binary search represents threshold tuning, heaps represent "what runs next," and intervals represent conflicts, capacity, and SLAs.

---

## 📋 Phase Overview

This phase connects algorithmic patterns directly to operational concerns. You'll work through binary search fundamentals (Week 31), parametric search (Week 32), heaps and priority queues (Week 33), interval merging (Week 34), query optimization (Week 35), and scheduling/load balancing (Week 36) — but always with an eye toward how these patterns power production systems.

The weeks build from invariant-driven narrowing (Week 31) through advanced binary search patterns (Week 32), heap operations (Week 33), interval reasoning (Week 34), query planning (Week 35), and distributed workload balancing (Week 36). By the end, you'll be able to design and critique job schedulers, query plans, rate limiters, and deployment/maintenance windows.

The mental model that emerges: **binary search = iterative refinement; heaps = prioritization; intervals = conflict resolution.**

---

## 📅 Weeks in This Phase

- [Week 31 — Binary Search Fundamentals](../weeks/week31-binary-search-fundamentals.md) — Master invariant-driven narrowing for any ordered domain
- [Week 32 — Rotated Arrays & Parametric Search](../weeks/week32-rotated-parametric-search.md) — Binary search in non-linear and monotonic settings
- [Week 33 — Heaps & Priority Queues](../weeks/week33-heaps-priority-queues.md) — Understand heap operations and relationship to scheduling and caching
- [Week 34 — Merging & Intervals](../weeks/week34-intervals-merging.md) — Reason about overlapping intervals for resource contention
- [Week 35 — Query Optimization & Search Strategy](../weeks/week35-query-optimization.md) — Apply search and heap patterns to query planning and ranking
- [Week 36 — Scheduling, Intervals & Load Balancing](../weeks/week36-scheduling-load-balancing.md) — Integrate heap and interval reasoning for schedulers and rate limiters

---

## 🧠 Key Concepts

- **Binary Search Fundamentals** — Invariant-driven narrowing; iterative refinement for threshold tuning and adaptive control
- **Parametric Search** — Binary search on monotonic conditions; find optimal settings efficiently (batch size, latency thresholds)
- **Heaps & Priority Queues** — Min/max ordering; schedulers, ranking engines, caching systems where "next best" matters
- **Interval Merging** — Overlapping intervals; conflict windows, resource contention, time slot management
- **Query Optimization** — Binary search and heaps in query planning; indexing, execution plans, ranking
- **Scheduling & Load Balancing** — Heap + interval logic; throughput vs fairness, distributed workload balancing

---

## 🔗 Real-World Connections

Where these patterns show up in production:

- **Threshold Tuning** — Binary search for operational thresholds (timeout, retry interval, batch size)
- **Job Schedulers** — Heaps for "what runs next"; priority-based task execution
- **Query Plans** — Binary search for indexing; heaps for result ranking and execution ordering
- **Rate Limiters** — Interval logic for conflict windows, capacity management, SLA enforcement
- **Deployment/Maintenance Windows** — Interval merging for non-overlapping maintenance periods
- **Adaptive Control** — Parametric search for convergence in systems, performance tuning

---

## ✅ Interview Readiness Checklist

After completing this phase, you should be able to:

- [ ] Express any "find threshold" problem as a binary search with a stable invariant
- [ ] Write binary search for arbitrary monotonic predicates confidently
- [ ] Map heap logic directly to scheduling and prioritization patterns
- [ ] Detect and reason about overlaps or gaps using interval logic
- [ ] Explain query optimization as a binary search and heap problem combined
- [ ] Reason about scheduling fairness and priority mathematically
- [ ] Design job schedulers, query plans, rate limiters, and deployment/maintenance windows
- [ ] Identify where heap or interval logic implicitly appears in distributed systems

---

## 🏁 Phase Completion Criteria

You can identify a real operational threshold (timeout, retry interval, batch size) and explain how binary search could formalize its tuning. You can model a system you use (job queue, task scheduler) as a heap and explain what determines its "priority." When designing schedulers or rate limiters, you can reason about throughput vs fairness using heap and interval logic.

**Interview readiness:** You should be able to handle medium problems involving binary search, heaps, and intervals while explaining how these patterns power real operational systems (schedulers, query optimizers, rate limiters, load balancers).

---

## 📊 Phase Stats

- **Total Weeks:** 6
- **Total Points:** 130 pts
- **Estimated Time:** ~12 hours (6 weeks × 2 hours/week)

