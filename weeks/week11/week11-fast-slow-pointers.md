
# Week 11 — Fast & Slow Pointers

**🎯 Objective**  
Apply the tortoise-hare technique to detect cycles and find midpoints in linked structures.

---

## 📘 Study Material

- [Detect Cycle in Linked List — Baeldung](https://www.baeldung.com/java-detect-linked-list-cycle) — Floyd’s algorithm explanation.
- [Detect Loop in Linked List — GeeksforGeeks](https://www.geeksforgeeks.org/detect-loop-in-a-linked-list/) — Practical and visual explanation.
- [Fast and Slow Pointer Pattern — LeetCode Discuss](https://leetcode.com/discuss/general-discussion/475924/Fast-and-Slow-Pointer-Approach) — Conceptual generalization.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Linked List Cycle — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=gBTe7lFR3vc
- **Middle of the Linked List — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=A2_ldqM4QcQ

</details>

---

## 💡 Why It Matters (Senior Lens)

Detecting loops = detecting recursion errors, livelocks, or workflow cycles in distributed systems.

---

## 🧠 Work Reflection

Find one service where retrigger loops or cyclic dependencies could arise. Suggest a detection or prevention strategy.

---

## 🧩 Deliverables

- [ ] **Linked List Cycle** — [NeetCode](https://neetcode.io/problems/linked-list-cycle)
- [ ] **Middle of the Linked List** — [NeetCode](https://neetcode.io/problems/middle-of-the-linked-list)
- [ ] 100-word note: "Cycle detection in production."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you need to find middle or detect cycles, use two pointers moving at different speeds. Fast pointer moves 2x speed of slow pointer.
- Hint 2: For cycle detection: if there's a cycle, fast pointer will eventually catch slow pointer. If no cycle, fast pointer reaches end.
- Hint 3: For finding middle: when fast pointer reaches end, slow pointer is at middle. This works because fast moves twice as fast.

**Edge Cases:**
- Empty list
- Single node
- List with cycle starting at head
- Even vs odd length lists (for middle finding)
- Cycle of length 1 (self-loop)

**Common Pitfalls:**
- Not checking for null before accessing next (null pointer exception)
- Infinite loop if cycle detection logic is wrong
- Off-by-one errors in middle finding
- Not handling edge case of single node with cycle

### Problem-Specific Hints

**Linked List Cycle:**
- Hint 1: You need to detect if list has a cycle. If you traverse with one pointer, you might loop forever. How can two pointers help?
- Hint 2: Use Floyd's algorithm: slow pointer moves one step, fast moves two steps. If they meet, there's a cycle. If fast reaches null, no cycle.
- Hint 3: The key: if there's a cycle, fast pointer will eventually be in the cycle, and slow will enter later. Fast will catch up because it moves faster.

**Middle of the Linked List:**
- Hint 1: You need the middle node. If you traverse once to count, then traverse again, that's O(n) but two passes. Can you do it in one pass?
- Hint 2: Use two pointers: slow moves one step, fast moves two steps. When fast reaches end, slow is at middle.
- Hint 3: For even length, you might need to handle which middle (first or second). Check if fast.next is null (odd) or fast.next.next is null (even).

</details>

---

## ✅ Done When

You can apply tortoise-hare reasoning to debugging cycles in workflows or DAGs.

🏁 **25 pts**
