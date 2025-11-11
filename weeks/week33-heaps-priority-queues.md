
# Week 33 — Heaps & Priority Queues

**🎯 Objective**  
Understand heap operations, min/max ordering, and their relationship to scheduling and caching.

---

## 📘 Study Material

- [PriorityQueue in Java — Baeldung](https://www.baeldung.com/java-priority-queue)
- [Heap Data Structure — GeeksforGeeks](https://www.geeksforgeeks.org/heap-data-structure/)
- [Kth Largest Element — LeetCode](https://leetcode.com/problems/kth-largest-element-in-an-array/)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Kth Largest Element — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=XEmy13g1Qxc

</details>

---

## 💡 Why It Matters (Senior Lens)

Heaps are the heart of schedulers, ranking engines, and caching systems — anything where “next best” matters.

---

## 🧠 Work Reflection

Model one system you use (job queue, task scheduler) as a heap. What determines its “priority”?

---

## 🧩 Deliverables

- [ ] **Kth Largest Element** — [LeetCode](https://leetcode.com/problems/kth-largest-element-in-an-array/)
- [ ] Write a mini heap class (conceptually) with `insert`, `pop`, `peek`.
- [ ] 100-word note: "Heap as scheduler."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Heaps maintain min or max at root. Min-heap: parent <= children. Max-heap: parent >= children. Perfect for getting top K elements.
- Hint 2: For "Kth largest": use min-heap of size K. Add elements, if heap size > K, remove smallest. Root is Kth largest.
- Hint 3: Heap operations: insert O(log n), get min/max O(1), remove min/max O(log n). Build heap from array: O(n).

**Edge Cases:**
- k = 1 (just find max)
- k = n (just find min)
- k larger than array size
- All elements same
- Very large k

**Common Pitfalls:**
- Using wrong heap type (min vs max)
- Not maintaining heap size correctly
- Confusing heap with sorted array
- Not handling k > n case
- Forgetting heap property after operations

### Problem-Specific Hints

**Kth Largest Element:**
- Hint 1: You need Kth largest. If you use max-heap, you'd need to remove k-1 elements. Can you do better?
- Hint 2: Use min-heap of size K. Add elements. When size > K, remove smallest. After processing all, root is Kth largest.
- Hint 3: Or use quickselect (modified quicksort) for O(n) average case. Or sort and return nums[n-k] for O(n log n).

</details>

---

## ✅ Done When

You can map heap logic directly to scheduling and prioritization patterns.

🏁 **20 pts**
