
# Week 32 — Rotated Arrays & Parametric Search

**🎯 Objective**  
Learn binary search in non-linear and monotonic settings — rotated arrays, feasibility functions, and optimization.

---

## 📘 Study Material

- [Search in Rotated Sorted Array — LeetCode](https://leetcode.com/problems/search-in-rotated-sorted-array/)
- [Parametric Search — GeeksforGeeks](https://www.geeksforgeeks.org/parametric-search/)
- [Binary Search Beyond Arrays — Baeldung](https://www.baeldung.com/cs/binary-search-non-array)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Search in Rotated Sorted Array — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=U8XENwh8Oy8

</details>

---

## 💡 Why It Matters (Senior Lens)

Parametric search applies binary search to *monotonic conditions*, e.g. “is this batch size still stable?” or “is this latency acceptable?”

---

## 🧠 Work Reflection

Pick one performance metric that worsens monotonically. How would you find the optimal setting efficiently?

---

## 🧩 Deliverables

- [ ] **Search in Rotated Sorted Array** — [LeetCode](https://leetcode.com/problems/search-in-rotated-sorted-array/)
- [ ] Generic template implementing `isFeasible(mid)` logic.
- [ ] 100-word reflection: "Parametric search in my system."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Rotated array: one half is always sorted. Determine which half is sorted, then check if target is in that half.
- Hint 2: Parametric search: binary search on answer space, not array. Define isFeasible(mid) function that's monotonic.
- Hint 3: For rotated arrays: if nums[left] <= nums[mid], left half is sorted. Check if target is in [left, mid]. Otherwise right half is sorted.

**Edge Cases:**
- Array not rotated (fully sorted)
- Single element
- Target not in array
- Duplicate elements
- Target at pivot point

**Common Pitfalls:**
- Not correctly identifying which half is sorted
- Off-by-one errors in range checks
- Not handling duplicates correctly
- Confusing rotated array logic
- Not considering all cases

### Problem-Specific Hints

**Search in Rotated Sorted Array:**
- Hint 1: Array is rotated but sorted. One half is always sorted. How do you determine which half contains target?
- Hint 2: Check if left half is sorted (nums[left] <= nums[mid]). If target is in [nums[left], nums[mid]], search left. Otherwise search right.
- Hint 3: If left half not sorted, right half is sorted. If target is in [nums[mid], nums[right]], search right. Otherwise search left.

</details>

---

## ✅ Done When

You can write binary search for arbitrary monotonic predicates confidently.

🏁 **20 pts**
