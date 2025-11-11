
# Week 13 — Binary Tree Traversals & Mental Models

**🎯 Objective**  
Understand binary tree structure and core traversals (pre/in/post/level-order) as the foundation for hierarchical reasoning.

---

## 📘 Study Material

- [Implementing a Binary Tree in Java — Baeldung](https://www.baeldung.com/java-binary-tree) — Basic structure and traversal examples.
- [Depth First Search in Java — Baeldung](https://www.baeldung.com/java-depth-first-search) — How traversal order changes results.
- [Level-order Traversal — Baeldung](https://www.baeldung.com/cs/level-order-traversal-binary-tree) — BFS traversal pattern for trees.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Invert Binary Tree — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=OnSn2XEQ4MY
- **Maximum Depth of Binary Tree — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=hTM3phVI6YQ

</details>

---

## 💡 Why It Matters (Senior Lens)

Traversal order governs evaluation order, dependency resolution, and event propagation — concepts that reappear in build graphs and rule engines.

---

## 🧠 Work Reflection

Choose a hierarchical structure you’ve worked with (config tree, org structure, file tree). Which traversal implicitly happens when you query or render it?

---

## 🧩 Deliverables

- [ ] **Invert Binary Tree** — [NeetCode](https://neetcode.io/problems/invert-a-binary-tree)
- [ ] **Maximum Depth of Binary Tree** — [LeetCode](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
- [ ] 100-word note: "Traversal orders I've encountered in production."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Tree traversals process nodes in different orders. Pre-order: process before children. In-order: process between children. Post-order: process after children. Level-order: process level by level.
- Hint 2: For tree problems, ask: do I need to process parent before children (pre-order), after children (post-order), or level by level (BFS)?
- Hint 3: Recursive solutions are natural for trees. Each recursive call handles one node and its subtree. Base case: null node.

**Edge Cases:**
- Empty tree (null root)
- Single node tree
- Skewed tree (all nodes on one side)
- Perfect binary tree
- Tree with only left or only right children

**Common Pitfalls:**
- Forgetting to handle null nodes
- Not understanding traversal order differences
- Confusing DFS (recursive/stack) with BFS (queue)
- Off-by-one errors in depth calculation

### Problem-Specific Hints

**Invert Binary Tree:**
- Hint 1: You need to swap left and right children for every node. What traversal order processes each node exactly once?
- Hint 2: Use any traversal (pre/in/post/level-order). At each node, swap left and right children, then recursively process children.
- Hint 3: Pre-order works well: swap children, then recurse on left, then recurse on right. Post-order also works: recurse first, then swap.

**Maximum Depth of Binary Tree:**
- Hint 1: Depth of a node = 1 + max(depth of left subtree, depth of right subtree). What's the base case?
- Hint 2: Base case: if node is null, return 0. Otherwise, return 1 + max(depth(left), depth(right)).
- Hint 3: This is naturally post-order: you need depths of children before computing current depth. Or use BFS to count levels.

</details>

---

## ✅ Done When

You can look at a tree process and immediately identify if it’s pre-, in-, or post-order by behavior.

🏁 **20 pts**
