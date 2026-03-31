
# Week 09 — Queues & BFS Logic

**🎯 Objective**  
Use queues to model FIFO (first-in-first-out) logic and perform level-order traversal in data or systems.

---

## 📘 Study Material

- [Queue Interface in Java — Baeldung](https://www.baeldung.com/java-queue) — Covers `Queue`, `Deque`, and `LinkedList` usage.
- [Queue Data Structure — GeeksforGeeks](https://www.geeksforgeeks.org/queue-data-structure/) — Core queue operations and use cases.
- [Breadth-First Search (BFS) in Java — Baeldung](https://www.baeldung.com/java-bfs) — Tree and graph BFS traversal.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Implement Queue Using Stacks — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=EUNGb8vOhbo
- **Binary Tree Level Order Traversal — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=6ZnyEApgFYg

</details>

---

## 💡 Why It Matters (Senior Lens)

Queues mirror real production systems: job queues, consumer pipelines, and service orchestrators rely on these semantics.

---

## 🧠 Work Reflection

Diagram your async processing system as a BFS graph — services as nodes, message queues as edges.

---

## 🧩 Deliverables

- [ ] **Implement Queue Using Stacks** — [NeetCode](https://neetcode.io/problems/implement-queue-using-stacks)
- [ ] **Binary Tree Level Order Traversal** — [NeetCode](https://neetcode.io/problems/level-order-traversal-of-binary-tree/question)
- [ ] **Rotting Oranges** — [NeetCode](https://neetcode.io/problems/rotting-fruit/question)
- [ ] **Number of Islands** — [NeetCode](https://neetcode.io/problems/number-of-islands/question)
- [ ] Sketch your system's BFS model.

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you need "first in, first out" processing or level-by-level traversal, use a queue. What order do you need to process elements?
- Hint 2: BFS uses a queue to explore nodes level by level. Add neighbors to queue, process in order. This ensures you visit all nodes at level N before level N+1.
- Hint 3: For level-order traversal, you need to know when one level ends and next begins. Track queue size before processing each level.

**Edge Cases:**
- Empty tree or graph
- Single node
- Linear structure (all nodes in one path)
- Very deep trees (considering stack/queue size)

**Common Pitfalls:**
- Forgetting to mark nodes as visited (in graphs, causes infinite loops)
- Not handling null nodes in trees
- Confusing BFS (queue) with DFS (stack/recursion)
- Not tracking level boundaries correctly

### Problem-Specific Hints

**Implement Queue Using Stacks:**
- Hint 1: Queue is FIFO, stack is LIFO. How can you reverse the order? Think about using two stacks.
- Hint 2: Use one stack for enqueue, another for dequeue. When dequeue stack is empty, transfer all elements from enqueue stack (this reverses order).
- Hint 3: Amortized O(1): each element is pushed/popped at most twice (once per stack). Worst-case O(n) for one operation, but average is O(1).

**Binary Tree Level Order Traversal:**
- Hint 1: You need to process nodes level by level. What data structure processes elements in order?
- Hint 2: Use a queue. Add root, then while queue is not empty: process all nodes at current level (queue size), add their children.
- Hint 3: Track level size before processing. For each level, process exactly that many nodes, then add their children to queue for next level.

**Rotting Oranges:**
- Hint 1: Multiple rotten oranges spread simultaneously each minute. This is multi-source BFS — how do you start from multiple points at once?
- Hint 2: Seed the queue with ALL initially rotten oranges at time 0. BFS naturally expands them in parallel level by level, where each level = 1 minute.
- Hint 3: After BFS, scan the grid. If any fresh orange remains, return -1. Otherwise return the number of BFS levels elapsed (minutes).

**Number of Islands:**
- Hint 1: You need to count distinct connected groups of land (`'1'`). How do you mark all cells belonging to one island before moving to the next?
- Hint 2: When you find an unvisited `'1'`, increment count and BFS/DFS to mark all connected `'1'`s as visited (set to `'0'` or use a visited set).
- Hint 3: BFS explores all 4 neighbors. This is the same "flood fill" pattern as Rotting Oranges — recognizing the pattern matters more than the grid details.

</details>

---

## ✅ Done When

You can reason about concurrency and parallel processing using BFS-style layering.

🏁 **25 pts**
