
# Week 17 — Graph Representation & Cloning

**🎯 Objective**  
Understand adjacency lists, matrices, and how to model real systems as graphs.

---

## 📘 Study Material

- [Graphs in Java — Baeldung](https://www.baeldung.com/java-graphs) — Basic representations in Java.
- [Graph Data Structures — Baeldung (CS)](https://www.baeldung.com/cs/graphs) — Tradeoffs between adjacency list/matrix.
- [Clone Graph — LeetCode](https://leetcode.com/problems/clone-graph/)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Clone Graph — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=mQeF6bN8hMk

</details>

---

## 💡 Why It Matters (Senior Lens)

Graphs model everything from service dependencies to feature rollout paths. Correct representation = correct insight.

---

## 🧠 Work Reflection

Sketch one real service dependency map. Which structure (adjacency list, matrix, edges) fits best and why?

---

## 🧩 Deliverables

- [ ] **Clone Graph** — [NeetCode](https://neetcode.io/problems/clone-graph)
- [ ] 150-word note: "Graph structure choices in my system."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Cloning a graph requires creating new nodes and copying edges. Use HashMap to map old nodes to new nodes.
- Hint 2: Traverse the graph (DFS or BFS). For each node, create a copy if not already created, then copy its neighbors.
- Hint 3: The HashMap prevents creating duplicate copies and allows you to connect edges correctly.

**Edge Cases:**
- Empty graph (null node)
- Single node graph
- Graph with cycles
- Disconnected components
- Graph with self-loops

**Common Pitfalls:**
- Creating duplicate nodes for same original node
- Not copying edges correctly
- Infinite loop if not tracking visited nodes
- Forgetting to handle null input
- Not initializing HashMap correctly

### Problem-Specific Hints

**Clone Graph:**
- Hint 1: You need to create a deep copy. Each node needs a new copy, and edges must connect the new nodes. How do you track which new node corresponds to which old node?
- Hint 2: Use HashMap: oldNode → newNode. DFS/BFS: if node not in map, create copy and add to map. Then copy all neighbors recursively.
- Hint 3: Start with given node. If null, return null. Use DFS: if node in map, return mapped node. Otherwise create copy, add to map, recursively clone all neighbors, add to copy's neighbors list.

</details>

---

## ✅ Done When

You can model a dependency graph cleanly and explain representation tradeoffs.

🏁 **20 pts**
