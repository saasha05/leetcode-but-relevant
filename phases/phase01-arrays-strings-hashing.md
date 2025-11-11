# Phase 1 — Arrays, Strings & Hashing

**🎯 Purpose**  
Rebuild raw computational intuition by connecting basic data structures and iteration patterns to real-world performance and correctness concerns.

---

## 📋 Phase Overview

This phase transforms "I kinda remember this" into "I can see hidden O(n²) and data layout issues in real code." You'll work through arrays, hash maps, sets, prefix sums, and sliding windows — but always with an eye toward how these patterns show up in production systems.

The weeks build from fundamental complexity analysis (Week 1) through hash-based structures (Weeks 2, 5) to advanced iteration patterns (Weeks 3, 4), culminating in a capstone that integrates everything (Week 6). By the end, you'll be able to reason about hot paths, caching needs, uniqueness guarantees, and streaming windows as first-class engineering concerns.

The mental model that emerges: **data structure choice is a performance and correctness decision, not just a convenience.**

---

## 📅 Weeks in This Phase

- [Week 1 — Arrays & Complexity at Scale](../weeks/week01-arrays-complexity.md) — Build precise mental models of contiguous storage and iteration costs
- [Week 2 — HashMaps & Frequency as Infrastructure](../weeks/week02-hashmaps-frequency.md) — Understand HashMap internals and when to trust O(1)
- [Week 3 — Strings, Sliding Window & Streaming](../weeks/week03-sliding-window.md) — Replace brute-force scans with linear window passes
- [Week 4 — Prefix Sums & Subarrays](../weeks/week04-prefix-sums.md) — Support fast range queries with precomputed aggregates
- [Week 5 — HashSets, Uniqueness & Idempotency](../weeks/week05-hashsets-uniqueness.md) — Enforce uniqueness and idempotent behavior with set semantics
- [Week 6 — Capstone: Data Layout & Hot Paths](../weeks/week06-capstone-data-layout.md) — Integrate all Phase 1 concepts into production reasoning

---

## 🧠 Key Concepts

- **Complexity Analysis** — Annotate nested loops with realistic time/space costs; spot O(n²) before it becomes a production issue
- **Hash Map Internals** — Buckets, load factor, collisions, tree bins; reason about worst-case behavior in caches and routing tables
- **Sliding Window** — Convert nested loops to single-pass algorithms; power rate limiting, rolling metrics, and streaming analytics
- **Prefix Sums** — Precompute range queries; optimize billing, analytics, and reporting workloads
- **Set Semantics** — Uniqueness, membership, idempotency; design "process-once" guarantees in distributed systems

---

## 🔗 Real-World Connections

Where these patterns show up in production:

- **API Latency** — Array iteration and hash map lookups in hot request paths
- **Billing/Metrics Queries** — Prefix sums for range aggregations; hash maps for fast lookups
- **Duplicate Prevention** — Sets for idempotency keys, message deduplication, payment processing
- **Streaming Windows** — Sliding windows for rate limiting, rolling averages, LLM context management
- **Session Stores & Caches** — Hash maps as the foundation for routing tables, feature stores, and session management

---

## ✅ Interview Readiness Checklist

After completing this phase, you should be able to:

- [ ] Annotate any nested loop with time/space complexity in realistic units (input size → cost)
- [ ] Explain when a plain array is appropriate over `ArrayList` in a hot code path
- [ ] Describe HashMap buckets, load factor, collisions, and worst-case complexity
- [ ] Challenge "just add a HashMap" with concrete questions about keys, growth, and GC impact
- [ ] Identify sliding window opportunities in nested-loop substring or subarray problems
- [ ] Design prefix-sum backing structures for efficient range queries
- [ ] Justify set usage for uniqueness and idempotency guarantees
- [ ] Map each Phase 1 problem pattern to a real-world analogue (logs, lookups, streaming, aggregations)

---

## 🏁 Phase Completion Criteria

You can defend each major collection choice in a system you know well. You can map Phase 1 problems directly to production scenarios: API latency, billing queries, duplicate prevention, and streaming windows. When reviewing code, you instinctively ask: "Can we amortize this with a prefix or diff array?" and "Is this secretly O(n²)?"

**Interview readiness:** You should be able to handle easy-to-medium problems involving arrays, strings, and hash-based structures while narrating complexity tradeoffs and real-world applications.

---

## 📊 Phase Stats

- **Total Weeks:** 6
- **Total Points:** 150 pts
- **Estimated Time:** ~12 hours (6 weeks × 2 hours/week)

