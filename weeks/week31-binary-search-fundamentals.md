
# Week 31 — Binary Search Fundamentals

**🎯 Objective**  
Master invariant-driven narrowing — applying binary search logic to any ordered domain.

---

## 📘 Study Material

- [Binary Search — Baeldung (CS)](https://www.baeldung.com/cs/binary-search) — Clear explanation of algorithm and boundary conditions.
- [Binary Search — LeetCode](https://leetcode.com/problems/binary-search/)
- [Binary Search Variants — GeeksforGeeks](https://www.geeksforgeeks.org/binary-search/) — Edge cases and practical uses.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Binary Search — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=s4DPM8ct1pI

</details>

---

## 💡 Why It Matters (Senior Lens)

Binary search represents **iterative refinement** — the mental model for threshold tuning, adaptive control, and convergence in systems.

---

## 🧠 Work Reflection

Identify a real operational threshold (timeout, retry interval, batch size). How could binary search formalize its tuning?

---

## 🧩 Deliverables

- [ ] **Binary Search** — [LeetCode](https://leetcode.com/problems/binary-search/)
- [ ] 100-word note: "Operational tuning as search-space narrowing."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Binary search works on sorted arrays. The key is maintaining an invariant: left side has one property, right side has another.
- Hint 2: Template: left = 0, right = n-1. While left <= right: mid = (left+right)/2, compare target with nums[mid], adjust left/right.
- Hint 3: Be careful with boundaries: use left <= right vs left < right, and left = mid+1 vs left = mid. This depends on whether you want to find first/last occurrence.

**Edge Cases:**
- Empty array
- Single element
- Target not in array
- Target at first/last position
- Duplicate elements (finding first/last occurrence)

**Common Pitfalls:**
- Infinite loops from incorrect boundary updates
- Off-by-one errors
- Not handling empty array
- Confusing when to use <= vs <
- Not considering integer overflow in mid calculation

### Problem-Specific Hints

**Binary Search:**
- Hint 1: You need to find target in sorted array. Compare target with middle element. If equal, found. If less, search left. If greater, search right.
- Hint 2: Use left = 0, right = n-1. While left <= right: mid = (left+right)/2. If nums[mid] == target, return mid. If nums[mid] < target, left = mid+1. Else right = mid-1.
- Hint 3: Return -1 if not found. The loop ends when left > right, meaning target not in array.

</details>

---

## ✅ Done When

You can express any “find threshold” problem as a binary search with a stable invariant.

🏁 **20 pts**
