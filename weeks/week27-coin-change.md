
# Week 27 — Coin Change & Resource Allocation

**🎯 Objective**  
Learn to minimize or maximize cost given constraints — foundational for resource scheduling.

---

## 📘 Study Material

- [Coin Change — LeetCode](https://leetcode.com/problems/coin-change/)
- [Unbounded Knapsack — GeeksforGeeks](https://www.geeksforgeeks.org/unbounded-knapsack-dp-23/)
- [Optimization with DP — Baeldung (CS)](https://www.baeldung.com/cs/optimization-dynamic-programming)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Coin Change — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=H9bfqozjoqs

</details>

---

## 💡 Why It Matters (Senior Lens)

Every “least cost” or “minimum effort” optimization in production is a coin change problem under the hood.

---

## 🧠 Work Reflection

Pick a resource (compute, cost, API quota). Redefine it as a DP: what’s your “amount” and “denominations”?

---

## 🧩 Deliverables

- [ ] **Coin Change** (bottom-up and top-down).  
- [ ] 100-word note: "Resource allocation as DP."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Coin change is an unbounded knapsack problem. You can use each coin unlimited times. Find minimum coins to make amount.
- Hint 2: dp[i] = minimum coins to make amount i. For each coin, if coin <= i, dp[i] = min(dp[i], dp[i-coin] + 1).
- Hint 3: Initialize dp[0] = 0, dp[i] = amount+1 (impossible) for i > 0. Iterate through amounts, try each coin.

**Edge Cases:**
- amount = 0 (return 0)
- No coins available
- Impossible to make amount (return -1)
- Coins with value 0 or negative
- Very large amount

**Common Pitfalls:**
- Not handling impossible case correctly
- Using greedy (always pick largest coin) - doesn't work for all cases
- Off-by-one errors
- Not initializing dp array correctly
- Forgetting coins can be reused

### Problem-Specific Hints

**Coin Change:**
- Hint 1: You need minimum coins to make amount. For each amount, try each coin. What's the recurrence?
- Hint 2: dp[amount] = min over all coins: dp[amount - coin] + 1. Base case: dp[0] = 0.
- Hint 3: Initialize dp with amount+1 (impossible). For each amount from 1 to target, for each coin, if coin <= amount, update dp[amount] = min(dp[amount], dp[amount-coin] + 1).

</details>

---

## ✅ Done When

You can translate cost tradeoffs or quotas into DP problems fluently.

🏁 **20 pts**
