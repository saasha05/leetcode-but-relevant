
# Week 28 — Longest Increasing Subsequence (LIS)

**🎯 Objective**  
Understand growth-sequence detection and monotonic DP patterns.

---

## 📘 Study Material

- [Longest Increasing Subsequence — LeetCode](https://leetcode.com/problems/longest-increasing-subsequence/)
- [LIS using DP — GeeksforGeeks](https://www.geeksforgeeks.org/longest-increasing-subsequence-dp-3/)
- [DP Patterns for Sequences — Baeldung](https://www.baeldung.com/cs/dp-patterns-sequences)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Longest Increasing Subsequence — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=on2hvxBXJH4

</details>

---

## 💡 Why It Matters (Senior Lens)

LIS models growth, trend, or stability — useful for monitoring metrics, anomaly detection, or product adoption streaks.

---

## 🧠 Work Reflection

Pick a metric that should only increase (revenue, uptime, engagement). How would LIS logic detect regressions?

---

## 🧩 Deliverables

- [ ] **Longest Increasing Subsequence.**  
- [ ] Reflection: "Tracking growth via LIS."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: LIS finds longest subsequence where elements are strictly increasing. Subsequence means you can skip elements, but order must be preserved.
- Hint 2: DP approach: dp[i] = length of LIS ending at index i. For each i, check all previous j where nums[j] < nums[i], take max dp[j] + 1.
- Hint 3: Optimized: use binary search with a "tails" array. tails[i] = smallest ending element of LIS of length i+1.

**Edge Cases:**
- Empty array
- Single element
- All elements decreasing (LIS = 1)
- All elements same (LIS = 1)
- All elements increasing (LIS = n)

**Common Pitfalls:**
- Confusing subsequence with subarray (subsequence can skip elements)
- Not handling "strictly increasing" vs "non-decreasing"
- O(n²) when O(n log n) is possible with binary search
- Off-by-one errors
- Not initializing dp correctly

### Problem-Specific Hints

**Longest Increasing Subsequence:**
- Hint 1: You need longest subsequence (can skip elements) where each element is greater than previous. What's the DP state?
- Hint 2: dp[i] = length of LIS ending at nums[i]. For each i, check all j < i where nums[j] < nums[i], dp[i] = max(dp[j]) + 1.
- Hint 3: Optimized: maintain tails array. For each num, binary search for leftmost position where tails[i] >= num, replace it. Length of tails is LIS length.

</details>

---

## ✅ Done When

You can detect monotonic progressions and reversals in any dataset.

🏁 **20 pts**
