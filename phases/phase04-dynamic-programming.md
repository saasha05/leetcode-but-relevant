# Phase 4 — Dynamic Programming

**🎯 Purpose**  
Make DP feel like **architecture and optimization**, not puzzles, by showing how subproblems, memoization, and recurrence apply to rollout strategies, scheduling, experiment design, and cost management.

---

## 📋 Phase Overview

This phase reframes dynamic programming from "tricky interview problems" to "caching, planning, diffing, resource allocation, and long-term optimization." You'll work through subproblems and memoization (Week 25), local vs global optimization (Week 26), resource allocation (Week 27), growth sequences (Week 28), path counting (Week 29), and a capstone that synthesizes everything (Week 30).

The weeks build from understanding recurrence and overlapping subproblems (Week 25) through constraint-based optimization (Week 26), cost minimization (Week 27), sequence detection (Week 28), and path reasoning (Week 29), culminating in complex real-world analogues (Week 30). By the end, you'll be able to explain how DP reasoning applies to rollout strategies, scheduling, experiment design, and cost management.

The mental model that emerges: **memoization = caching; DP = planning; optimization problems are subproblem decompositions.**

---

## 📅 Weeks in This Phase

- [Week 25 — Subproblems & Climbing Stairs](../weeks/week25-subproblems-memoization.md) — Understand recurrence, overlapping subproblems, and memoization foundation
- [Week 26 — House Robber & Local Decisions](../weeks/week26-house-robber.md) — Balance local and global optimization with exclusion constraints
- [Week 27 — Coin Change & Resource Allocation](../weeks/week27-coin-change.md) — Minimize or maximize cost given constraints for resource scheduling
- [Week 28 — Longest Increasing Subsequence (LIS)](../weeks/week28-longest-increasing-subsequence.md) — Growth-sequence detection and monotonic DP patterns
- [Week 29 — Unique Paths & Combinatorics vs DP](../weeks/week29-unique-paths.md) — Compare recurrence-based and combinatorial solutions
- [Week 30 — DP Capstone](../weeks/week30-dp-capstone.md) — Synthesize memoization, recurrence, and optimization through complex analogues

---

## 🧠 Key Concepts

- **Subproblems & Memoization** — Recurrence, overlapping subproblems; caching subproblems mirrors cache lookups and reuse
- **Local vs Global Optimization** — Greedy decisions vs DP; ensure global optimality when local choices interact
- **Resource Allocation** — Coin change, knapsack; translate cost tradeoffs or quotas into DP problems
- **Sequence Detection** — LIS patterns; growth, trend, stability for monitoring metrics and anomaly detection
- **Path Counting** — Unique paths; when to use DP vs combinatorial math
- **Complex DP** — Edit distance (diffing), knapsack (prioritization), partition (load balancing)

---

## 🔗 Real-World Connections

Where these patterns show up in production:

- **Rollout Strategies** — Phased deployments, feature flags, gradual migrations as DP optimization
- **Scheduling** — Job scheduling, resource allocation, cost minimization
- **Experiment Design** — A/B test planning, resource allocation, long-term optimization
- **Cost Management** — Budget allocation, quota management, compute optimization
- **Diffing & Planning** — Edit distance for config diffing, change planning, migration strategies
- **Load Balancing** — Partition problems, resource distribution, capacity planning

---

## ✅ Interview Readiness Checklist

After completing this phase, you should be able to:

- [ ] Explain how recursion + memoization mirrors cache lookups and reuse
- [ ] Explain tradeoffs between greedy vs dynamic strategies
- [ ] Translate cost tradeoffs or quotas into DP problems fluently
- [ ] Detect monotonic progressions and reversals in any dataset
- [ ] Select between combinatorial and iterative solutions rationally
- [ ] Articulate how DP principles inform system design and optimization
- [ ] Explain how the same reasoning applies to rollout strategies, scheduling, experiment design, and cost management
- [ ] Map edit distance to config diffing, knapsack to prioritization, partition to load balancing

---

## 🏁 Phase Completion Criteria

You can explain how DP reasoning applies to rollout strategies, scheduling, experiment design, and cost management. You can pick a recurring computation in your system (permissions, scoring, analytics) and sketch what "cache the subproblem" would look like. When designing optimization systems, you instinctively ask: "Can we decompose this into subproblems?" and "What's being memoized?"

**Interview readiness:** You should be able to handle medium-to-hard DP problems while explaining how the same reasoning applies to real-world optimization scenarios (rollout, scheduling, resource allocation, cost management).

---

## 📊 Phase Stats

- **Total Weeks:** 6
- **Total Points:** 150 pts
- **Estimated Time:** ~12 hours (6 weeks × 2 hours/week)

