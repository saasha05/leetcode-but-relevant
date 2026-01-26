
# Week 14 — Lowest Common Ancestor & Hierarchies

**🎯 Objective**  
Model ancestor–descendant and ownership relationships with LCA (Lowest Common Ancestor) logic.

---

## 📘 Study Material

- [LCA of Two Nodes in a Tree — Baeldung](https://www.baeldung.com/cs/tree-lowest-common-ancestor) — Concept and code illustration.
- [LCA in Binary Tree — GeeksforGeeks](https://www.geeksforgeeks.org/lowest-common-ancestor-binary-tree-set-1/) — Step-by-step examples for trees and BSTs.

<details>
<summary><strong>Video Solutions</strong></summary>

- **LCA of a BST — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=gs2LMfuOR9k
- **LCA of a Binary Tree — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=py3R23aAPCA

</details>

---

## 💡 Why It Matters (Senior Lens)

LCA underlies configuration inheritance, access control, and ownership boundaries. Understanding it helps prevent logic leaks in nested hierarchies.

---

## 🧠 Work Reflection

Pick a hierarchy (permissions, folders, components). How could LCA be used to compute the “shared context” between two elements?

---

## 🧩 Deliverables

- [ ] **LCA of a BST** — [LeetCode](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)
- [ ] **LCA of a Binary Tree** — [LeetCode](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/)
- [ ] 150-word reflection: "Shared ownership via LCA."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: LCA is the deepest node that is an ancestor of both nodes. In a BST, you can use the ordering property. In a general tree, you need to search both subtrees.
- Hint 2: For BST: if both nodes are less than current, go left. If both greater, go right. Otherwise, current is LCA.
- Hint 3: For general tree: search left and right subtrees. If both return non-null, current is LCA. If one returns non-null, return that. If both null, return null.

**Edge Cases:**
- One node is ancestor of the other (LCA is the ancestor)
- Both nodes are the same
- Nodes don't exist in tree
- Empty tree
- Nodes in different subtrees

**Common Pitfalls:**
- Not handling case where one node is ancestor of the other
- Forgetting BST property (left < root < right)
- Returning wrong node when only one subtree has a match
- Not checking if nodes exist in tree

### Problem-Specific Hints

**LCA of a BST:**
- Hint 1: Use BST property: all left descendants < root < all right descendants. Where can both nodes be relative to current node?
- Hint 2: If both p and q are less than root, LCA is in left subtree. If both greater, LCA is in right subtree. Otherwise, root is LCA.
- Hint 3: Traverse from root. If p.val < root.val and q.val < root.val, go left. If p.val > root.val and q.val > root.val, go right. Otherwise return root.

**LCA of a Binary Tree:**
- Hint 1: Without BST property, you need to search both subtrees. What information do you need from each subtree?
- Hint 2: For each node, search left and right subtrees. If both subtrees return a node, current is LCA. If only one returns a node, pass it up.
- Hint 3: Base case: if node is null or equals p or q, return node. Recursively search left and right. If both non-null, current is LCA. Otherwise return the non-null one.

</details>

---

## ✅ Done When

You can explain how LCA translates to “closest shared parent” in orgs or data hierarchies.

🏁 **20 pts**
