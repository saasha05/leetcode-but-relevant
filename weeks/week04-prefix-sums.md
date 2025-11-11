
# Week 04 — Prefix Sums & Subarrays

**🎯 Objective**  
Use prefix sums and differences to support fast range queries and repeated aggregates.

---

## 📘 Study Material

- **Understanding Prefix Sums — GeeksforGeeks**  
  Gist: Explains prefix sums with examples and complexity.  
  Read: https://www.geeksforgeeks.org/prefix-sum-array-implementation-applications-variations/
- **Prefix Sum Technique — Take U Forward**  
  Gist: Practical competitive-programming style breakdown of prefix usage.  
  Read: https://takeuforward.org/data-structure/prefix-sum-technique/

<details>
<summary><strong>Video Solutions</strong></summary>

- **Subarray Sum Equals K — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=fFVZt-6sgsg
- **Product of Array Except Self — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=bNvIQI2wAjk

</details>

---

## 💡 Why It Matters (Senior Lens)

[Inference] Billing, analytics, and reporting frequently re-use overlapping ranges. Prefix-style thinking separates one-time work from query-time work.

---

## 🧠 Work Reflection

Choose one metric (e.g., daily active users, requests, spend). Describe a prefix-sum backing structure that answers “total between A and B” efficiently.

---

## 🧩 Deliverables

- [ ] **Subarray Sum Equals K**  
      NeetCode: https://neetcode.io/problems/subarray-sum-equals-k  
      LeetCode: https://leetcode.com/problems/subarray-sum-equals-k/  
- [ ] **Product of Array Except Self**  
      NeetCode: https://neetcode.io/problems/product-of-array-except-self  
      LeetCode: https://leetcode.com/problems/product-of-array-except-self/  
- [ ] ~100-word note: "Where prefix thinking fits my system."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you need to compute range sums repeatedly, precompute prefix sums. This turns O(n) range queries into O(1) lookups.
- Hint 2: Prefix sum array: `prefix[i] = sum of elements from 0 to i-1`. Range sum from i to j is `prefix[j+1] - prefix[i]`.
- Hint 3: For "subarray sum equals K" problems, think: if `sum[i:j] = K`, then `prefix[j] - prefix[i] = K`, so `prefix[i] = prefix[j] - K`. Use HashMap to track prefix sums.

**Edge Cases:**
- Empty arrays
- Arrays with all zeros
- Negative numbers (prefix sums can decrease)
- K = 0 (need to handle carefully)
- Single element arrays

**Common Pitfalls:**
- Off-by-one errors in prefix array indexing
- Forgetting to initialize prefix[0] = 0
- Not handling negative prefix sums correctly
- Confusing prefix sum with running sum

### Problem-Specific Hints

**Subarray Sum Equals K:**
- Hint 1: You need to find subarrays with sum K. If you have prefix sums, what relationship must hold between two prefix sums for their difference to equal K?
- Hint 2: For each position, check if `prefix[current] - K` exists in previous prefix sums. Use HashMap to store prefix sum → count.
- Hint 3: Initialize HashMap with {0: 1} to handle subarrays starting at index 0. For each element, add current prefix sum to map, then check if `prefix[current] - K` exists.

**Product of Array Except Self:**
- Hint 1: You can't use division. Think: product of all elements except self = product of left elements × product of right elements.
- Hint 2: Make two passes: first pass computes left products, second pass computes right products and multiplies with left.
- Hint 3: Or use prefix and suffix arrays. Or optimize space: compute left products in result array, then multiply by right products in reverse pass.

</details>

---

## ✅ Done When

- You can design a range query solution without rescanning each time.
- [Inference] You instinctively ask: “Can we amortize this with a prefix or diff array?”

🏁 **25 pts**
