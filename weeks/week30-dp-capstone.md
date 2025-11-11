
# Week 30 — DP Capstone

**🎯 Objective**  
Synthesize memoization, recurrence, and optimization through complex, real-world analogues.

---

## 📘 Study Material

- [Edit Distance — LeetCode](https://leetcode.com/problems/edit-distance/)
- [Partition Equal Subset Sum — LeetCode](https://leetcode.com/problems/partition-equal-subset-sum/)
- [Knapsack Problem — GeeksforGeeks](https://www.geeksforgeeks.org/0-1-knapsack-problem-dp-10/)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Edit Distance — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=XYi2-LPrwm4
- **Partition Equal Subset Sum — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=IsvocB5BJhw

</details>

---

## 💡 Why It Matters (Senior Lens)

Edit distance = diffing configs, Knapsack = prioritization, Partition = load balancing. All are real-world applications of DP.

---

## 🧠 Work Reflection

Pick one process (deployment, planning, experiment design) that could benefit from DP-like optimization.

---

## 🧩 Deliverables

- [ ] One complex DP problem (Edit Distance / Knapsack / Partition).  
- [ ] 1-page reflection: "DP mindset for architecture."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Complex DP problems combine multiple concepts: 2D DP, string matching, subset problems. Break into subproblems.
- Hint 2: Edit Distance: 2D DP where dp[i][j] = min edits to convert word1[0:i] to word2[0:j]. Operations: insert, delete, replace.
- Hint 3: Partition/Subset: 0/1 knapsack variant. Can you partition array into two equal sum subsets? dp[i][sum] = can we make sum using first i elements.

**Edge Cases:**
- Empty strings/arrays
- Single element
- All elements same
- Impossible cases (sum is odd for partition)
- Very large inputs

**Common Pitfalls:**
- Not identifying the DP state correctly
- Confusing 2D DP dimensions
- Not handling base cases
- Off-by-one errors
- Not optimizing space when possible

### Problem-Specific Hints

**Edit Distance:**
- Hint 1: You need minimum operations (insert, delete, replace) to convert word1 to word2. What's the DP state?
- Hint 2: dp[i][j] = min edits for word1[0:i] to word2[0:j]. If word1[i] == word2[j], dp[i][j] = dp[i-1][j-1]. Otherwise, dp[i][j] = 1 + min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1]).
- Hint 3: Base cases: dp[0][j] = j (insert j chars), dp[i][0] = i (delete i chars).

**Partition Equal Subset Sum:**
- Hint 1: Can you partition array into two subsets with equal sum? If total sum is odd, impossible. Otherwise, check if subset sum = total/2 exists.
- Hint 2: This is 0/1 knapsack: can we make sum = total/2 using array elements? dp[i][sum] = dp[i-1][sum] || dp[i-1][sum-nums[i]].
- Hint 3: Optimize space: use 1D array, iterate backwards to avoid overwriting.

</details>

---

## ✅ Done When

You can articulate how DP principles inform system design and optimization.

🏁 **50 pts**
