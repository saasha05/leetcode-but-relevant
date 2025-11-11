# Phase 3 — Trees & Graphs

**🎯 Purpose**  
Unlock graph-thinking as the default lens for systems by replacing "trees/graphs are scary interview topics" with "this is literally my service graph, ACL graph, data lineage graph."

---

## 📋 Phase Overview

This phase transforms how you model systems. You'll work through binary tree traversals, LCA (Lowest Common Ancestor), serialization, grids/islands, graph representation, and topological sort — but always with an eye toward how these patterns model real system relationships.

The weeks progress from fundamental tree traversals (Week 13) through hierarchical reasoning (Week 14), serialization patterns (Week 15), connectivity analysis (Week 16), graph representation (Week 17), and dependency reasoning (Week 18). By the end, you'll be comfortable modeling microservice dependencies, rollout and migration DAGs, config/ownership hierarchies, and failure domains.

The mental model that emerges: **systems are graphs; trees are special cases of graphs; understanding connectivity, cycles, and ordering is staff-level engineering.**

---

## 📅 Weeks in This Phase

- [Week 13 — Binary Tree Traversals & Mental Models](../weeks/week13-binary-tree-traversals.md) — Understand pre/in/post/level-order traversals as foundation for hierarchical reasoning
- [Week 14 — Lowest Common Ancestor & Hierarchies](../weeks/week14-lca-hierarchies.md) — Model ancestor–descendant and ownership relationships
- [Week 15 — Tree Serialization & Schema Thinking](../weeks/week15-serialization-schemas.md) — Encode and decode hierarchical data reliably across systems
- [Week 16 — Grids, DFS/BFS & Connected Components](../weeks/week16-dfs-bfs-islands.md) — Model connectivity and isolation in graph-like data
- [Week 17 — Graph Representation & Cloning](../weeks/week17-graphs-representation.md) — Understand adjacency lists, matrices, and system modeling
- [Week 18 — Topological Sort & DAG Reasoning](../weeks/week18-topological-sort.md) — Reason about dependencies, execution order, and cycle detection

---

## 🧠 Key Concepts

- **Tree Traversals** — Pre/in/post/level-order; evaluation order, dependency resolution, event propagation
- **LCA (Lowest Common Ancestor)** — Configuration inheritance, access control, ownership boundaries
- **Tree Serialization** — Configuration versioning, migration, backward-compatibility in distributed systems
- **Connected Components** — Outage domains, clusters, partitioned tenants; failure zone reasoning
- **Graph Representation** — Adjacency lists vs matrices; service dependencies, feature rollout paths
- **Topological Sort** — Build systems, migration plans, ML pipelines; cycle detection saves weeks of debugging

---

## 🔗 Real-World Connections

Where these patterns show up in production:

- **Microservice Dependencies** — Service graphs, dependency resolution, rollout ordering
- **Rollout and Migration DAGs** — Safe execution order, cycle prevention, dependency management
- **Config/Ownership Hierarchies** — Permission trees, folder structures, component ownership
- **Failure Domains** — Connected components as outage boundaries, isolation reasoning
- **Build Systems** — Dependency graphs, compilation order, incremental builds
- **Data Lineage** — Graph models for tracking data flow, transformations, dependencies

---

## ✅ Interview Readiness Checklist

After completing this phase, you should be able to:

- [ ] Look at a tree process and immediately identify if it's pre-, in-, or post-order by behavior
- [ ] Explain how LCA translates to "closest shared parent" in orgs or data hierarchies
- [ ] Argue why one serialization scheme is more robust or evolvable than another
- [ ] Map any connectivity question into a DFS/BFS traversal problem
- [ ] Model a dependency graph cleanly and explain representation tradeoffs (adjacency list vs matrix)
- [ ] Explain how DAG reasoning applies to real-world job or dependency graphs
- [ ] Detect cycles in complex workflows and prevent release failures
- [ ] Talk about cycles, ordering, and connectivity like a staff engineer

---

## 🏁 Phase Completion Criteria

You can model microservice dependencies, rollout and migration DAGs, config/ownership hierarchies, and failure domains as graphs. You can explain how tree traversals implicitly happen when querying or rendering hierarchical structures. When designing systems, you instinctively ask: "What's the dependency graph?" and "Where could cycles occur?"

**Interview readiness:** You should be able to handle medium problems involving trees and graphs while explaining how these structures model real system relationships (service dependencies, hierarchies, connectivity, ordering).

---

## 📊 Phase Stats

- **Total Weeks:** 6
- **Total Points:** 120 pts
- **Estimated Time:** ~12 hours (6 weeks × 2 hours/week)

