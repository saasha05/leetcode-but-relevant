
# Week 16 — Grids, DFS/BFS & Connected Components

**🎯 Objective**  
Model connectivity and isolation in graph-like data (grids, clusters, networks).

---

## 📘 Study Material

- [Number of Islands — LeetCode](https://leetcode.com/problems/number-of-islands/)
- [Find Number of Islands (DFS) — GeeksforGeeks](https://www.geeksforgeeks.org/find-the-number-of-islands-using-dfs/)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Number of Islands — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=pV2kpPD66nE

</details>

---

## 💡 Why It Matters (Senior Lens)

Connected components = outage domains, clusters, partitioned tenants. Thinking in components helps in distributed system reasoning.

---

## 🧠 Work Reflection

Visualize your system’s failure zones or logical partitions as a grid — which are “islands” and which are connected?

---

## 🧩 Deliverables

- [ ] Solve **Number of Islands** with both DFS and BFS.
- [ ] 100-word note: "Islands I've seen in infrastructure."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Connected components = islands. Each '1' cell that's connected to other '1's forms one island. Use DFS or BFS to mark all connected cells.
- Hint 2: For each unvisited '1', start DFS/BFS to mark all connected '1's as visited. Count how many times you start a new traversal.
- Hint 3: Mark visited cells by changing '1' to '0' (in-place) or using a visited set. This prevents revisiting.

**Edge Cases:**
- Empty grid
- Grid with all '0's (no islands)
- Grid with all '1's (one big island)
- Single cell grid
- Islands touching grid boundaries

**Common Pitfalls:**
- Not marking cells as visited (infinite loop)
- Checking out-of-bounds incorrectly
- Forgetting diagonal connections (if problem allows)
- Off-by-one errors in grid indices
- Not handling empty grid

### Problem-Specific Hints

**Number of Islands:**
- Hint 1: You need to count connected components of '1's. How do you find all cells connected to a starting '1'?
- Hint 2: Iterate through grid. When you find an unvisited '1', increment count and use DFS/BFS to mark all connected '1's as visited.
- Hint 3: DFS: recursively visit all 4-directional neighbors that are '1'. Mark current as visited (change to '0'). BFS: use queue, add unvisited '1' neighbors.

</details>

---

## ✅ Done When

You can map any connectivity question into a DFS/BFS traversal problem.

🏁 **20 pts**
