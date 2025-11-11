
# Week 10 — Two Pointers

**🎯 Objective**  
Use two-pointer patterns for scanning sorted data, merging intervals, or deduplicating efficiently.

---

## 📘 Study Material

- [Two Pointer Technique — Baeldung (CS)](https://www.baeldung.com/cs/two-pointer-technique) — Examples and tradeoffs.
- [Two Pointer Patterns — LeetCode](https://leetcode.com/explore/learn/card/array-and-string/204/conclusion/1182/) — Interactive tutorial.
- [Two Pointer Approach — GeeksforGeeks](https://www.geeksforgeeks.org/two-pointers-technique/) — Typical problems and edge cases.

<details>
<summary><strong>Video Solutions</strong></summary>

- **3Sum — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=jzZsG8n2R9A
- **Container With Most Water — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=UuiTKBwPgAo

</details>

---

## 💡 Why It Matters (Senior Lens)

Two-pointers convert nested loops into linear scans — crucial for stream deduplication, memory compaction, or anomaly pairing.

---

## 🧠 Work Reflection

Find a process where two nested loops exist (e.g., comparing timestamps). Refactor it conceptually to two pointers.

---

## 🧩 Deliverables

- [ ] **3Sum** — [NeetCode](https://neetcode.io/problems/3sum)
- [ ] **Container With Most Water** — [NeetCode](https://neetcode.io/problems/container-with-most-water)
- [ ] 100-word note: "My two-pointer invariant."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you have sorted data and need to find pairs or triplets, two pointers can eliminate one nested loop. Start from both ends or use one slow, one fast.
- Hint 2: Two pointers work when moving them in a way that maintains an invariant. What condition determines which pointer to move?
- Hint 3: For sorted arrays, if current sum is too small, move left pointer right (increase). If too large, move right pointer left (decrease).

**Edge Cases:**
- Empty arrays or arrays with less than required elements
- All elements are the same
- No valid solution exists
- Duplicates (need to skip to avoid duplicate results)
- Integer overflow when summing

**Common Pitfalls:**
- Not handling duplicates correctly (skipping same values)
- Off-by-one errors in pointer movement
- Forgetting to sort array first (if needed)
- Not maintaining the invariant correctly

### Problem-Specific Hints

**3Sum:**
- Hint 1: You need three numbers summing to zero. Fix one number, then find two numbers that sum to negative of fixed number.
- Hint 2: Sort array first. For each element, use two pointers on remaining array to find pairs summing to target. Skip duplicates.
- Hint 3: For each i, use left=i+1 and right=end. If sum < 0, move left right. If sum > 0, move right left. If sum == 0, add to result and skip duplicates.

**Container With Most Water:**
- Hint 1: Water area = min(height[left], height[right]) × width. You need to maximize this. What happens if you move the pointer with smaller height?
- Hint 2: Start with pointers at both ends. Always move the pointer with smaller height (moving larger one can't increase area). Calculate area at each step.
- Hint 3: The key insight: if height[left] < height[right], moving right pointer left can only decrease area (width decreases, height can't increase). So move left pointer right.

</details>

---

## ✅ Done When

You can express invariants clearly and maintain pointer movement conditions confidently.

🏁 **25 pts**
