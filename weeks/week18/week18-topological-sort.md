
# Week 18 — Topological Sort & DAG Reasoning

**🎯 Objective**  
Reason about dependencies, order of execution, and cycle detection in directed acyclic graphs (DAGs).

---

## 📘 Study Material

- [Topological Sort in a DAG — Baeldung](https://www.baeldung.com/cs/dag-topological-sort)
- [Topological Sorting — GeeksforGeeks](https://www.geeksforgeeks.org/topological-sorting/)
- [Course Schedule — LeetCode](https://leetcode.com/problems/course-schedule/)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Course Schedule — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=EgI5nU9etnU

</details>

---

## 💡 Why It Matters (Senior Lens)

Every build system, migration plan, and ML pipeline is a DAG. Detecting cycles saves weeks of debugging and release failures.

---

## 🧠 Work Reflection

Draw a small dependency graph (jobs, services, pipelines). Show how topological sort defines a safe order.

---

## 🧩 Deliverables

- [ ] **Course Schedule** — [LeetCode](https://leetcode.com/problems/course-schedule/)
- [ ] 150-word essay: "Cycle prevention in complex workflows."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Topological sort finds a valid ordering of nodes in a DAG. If cycle exists, no valid ordering. Use DFS with state tracking or Kahn's algorithm (BFS).
- Hint 2: DFS approach: mark nodes as visiting/visited. If you encounter a visiting node, cycle detected. Kahn's: start with nodes having no incoming edges, remove them, repeat.
- Hint 3: For cycle detection: if you can't process all nodes (Kahn's) or encounter visiting node (DFS), cycle exists.

**Edge Cases:**
- Empty graph
- Single node
- No dependencies (all courses independent)
- All courses depend on each other (cycle)
- Disconnected components

**Common Pitfalls:**
- Not detecting cycles correctly
- Confusing DFS and BFS approaches
- Not handling disconnected components
- Off-by-one errors in counting processed nodes
- Forgetting to check if all nodes were processed

### Problem-Specific Hints

**Course Schedule:**
- Hint 1: You need to check if all courses can be taken (no cycles). Each prerequisite is a directed edge. Can you find a valid ordering?
- Hint 2: Build adjacency list. Use DFS: mark nodes as 0 (unvisited), 1 (visiting), 2 (visited). If you encounter a 1, cycle exists.
- Hint 3: Or use Kahn's algorithm: count incoming edges for each node. Start with nodes having 0 incoming edges. Remove them, decrement neighbors' counts. If you can't process all nodes, cycle exists.

</details>

---

## ✅ Done When

You can explain how DAG reasoning applies to real-world job or dependency graphs.

🏁 **20 pts**
