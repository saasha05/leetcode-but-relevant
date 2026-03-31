
# Week 12 — Mini-Capstone: Control Flow Patterns

**🎯 Objective**  
Combine stack, queue, and pointer patterns to understand complex flow-control structures.

---

## 📘 Study Material

- [Command Pattern — Refactoring.Guru](https://refactoring.guru/design-patterns/command) — Shows stack/undo logic in design patterns.
- [Concurrency in Java — Baeldung](https://www.baeldung.com/java-concurrency) — Queue-driven concurrency overview.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Decode String — NeetCode YouTube**
  Video walkthrough: https://www.youtube.com/watch?v=qB0zZpBJlh8
- **Remove Nth Node From End — NeetCode YouTube**
  Video walkthrough: https://www.youtube.com/watch?v=XVuQxVej6y8
- **Reorder List — NeetCode YouTube**
  Video walkthrough: https://www.youtube.com/watch?v=S5bfdUTrKLM
- **Course Schedule — NeetCode YouTube**
  Video walkthrough: https://www.youtube.com/watch?v=EgI5nU9etnU

</details>

---

## 💡 Why It Matters (Senior Lens)

This week cements your understanding of control flow across recursion, iteration, and async logic — the foundation for scalable backend design.

---

## 🧠 Work Reflection

Design a scenario that merges two patterns (stack + queue, or slow/fast pointers + recursion). Explain how it improves clarity or performance.

---

## 🧩 Deliverables

- [ ] **Decode String** — [NeetCode](https://neetcode.io/problems/decode-string/question)
      *Stack (wk07) + nested counter tracking — stacks carry both the partial string and the repeat count through recursive depth.*
- [ ] **Remove Nth Node From End of List** — [NeetCode](https://neetcode.io/problems/remove-node-from-end-of-linked-list/question)
      *Gap two-pointer (wk10) on a linked list (wk11) — advance one pointer N steps ahead, then move both until the lead hits the end.*
- [ ] **Reorder List** — [NeetCode](https://neetcode.io/problems/reorder-linked-list/question)
      *Fast/slow to find midpoint (wk11) + reverse second half (wk10 pointer) + merge two halves.*
- [ ] **Course Schedule** — [NeetCode](https://neetcode.io/problems/course-schedule/question)
      *BFS topological sort (wk09) + cycle detection (wk11) — if a cycle exists in the prerequisite graph, not all courses can be completed.*
- [ ] 200-word essay: "Pattern blending in production systems."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: This capstone integrates Phase 2 patterns. Real problems often combine stacks, queues, and pointers. Identify which pattern applies to which part.
- Hint 2: Think about control flow: stacks for nested/recursive logic, queues for level-order processing, pointers for efficient scanning.
- Hint 3: When stuck, break the problem into subproblems. Which pattern solves each subproblem? How do they combine?

**Edge Cases:**
- Review edge cases from Phase 2 weeks
- Consider how patterns interact (e.g., stack + queue, pointers + recursion)
- Production scenarios: what if patterns conflict or have different performance characteristics?

**Common Pitfalls:**
- Trying to force one pattern when multiple are needed
- Not understanding how patterns complement each other
- Overcomplicating when a single pattern would suffice

### Problem-Specific Hints

**Decode String:**
- Hint 1: Brackets can be nested. What two pieces of state do you need to save when you open a bracket?
- Hint 2: Use a stack of (currentString, repeatCount) pairs. When you see `[`, push current state and reset. When you see `]`, pop and repeat the inner string.
- Hint 3: Build the current string character by character. The stack depth mirrors the nesting depth — recognise this as the call-stack pattern from wk07.

**Remove Nth Node From End of List:**
- Hint 1: You need to remove the Nth node from the end without knowing the length. Can you find it in one pass?
- Hint 2: Use two pointers with a gap of N. Advance the lead pointer N steps first, then move both until lead reaches the end. Slow pointer is now at the target.
- Hint 3: Use a dummy head node before the list — it handles the edge case of removing the first node without special-casing.

**Reorder List:**
- Hint 1: The target order is: first, last, second, second-to-last, … How do you get the back half in reverse order efficiently?
- Hint 2: Three steps: (1) find midpoint with fast/slow pointers, (2) reverse the second half in-place, (3) merge the two halves by alternating nodes.
- Hint 3: Cutting the list at mid requires setting mid.next = null. Don't skip this — otherwise the merge loop won't terminate.

**Course Schedule:**
- Hint 1: Model courses as nodes and prerequisites as directed edges. Can all courses be completed? That's asking: does the graph have a cycle?
- Hint 2: Use BFS topological sort (Kahn's algorithm): build an in-degree map, seed the queue with all zero-in-degree nodes, process and decrement neighbors.
- Hint 3: If the number of processed nodes equals the total number of courses, no cycle exists. Otherwise there's a cycle and some courses can't be taken.

</details>

---

## ✅ Done When

You can spot and explain hybrid algorithmic patterns in real-world engineering.

🏁 **25 pts**
