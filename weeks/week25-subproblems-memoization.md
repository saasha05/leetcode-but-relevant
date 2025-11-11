
# Week 25 — Subproblems & Climbing Stairs

**🎯 Objective**  
Understand recurrence, overlapping subproblems, and memoization — the foundation of Dynamic Programming (DP).

---

## 📘 Study Material

- [Dynamic Programming Introduction — Baeldung (CS)](https://www.baeldung.com/cs/dynamic-programming) — Explains DP intuition with examples.
- [Climbing Stairs — LeetCode](https://leetcode.com/problems/climbing-stairs/) — Classic DP warm-up.
- [Overlapping Subproblems — GeeksforGeeks](https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming/) — Contrasts recursion vs memoization.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Climbing Stairs — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=Y0lT9Fck7qI

</details>

---

## 💡 Why It Matters (Senior Lens)

Memoization = caching. It’s the same pattern that powers query planners, permission resolvers, and ML inference caching.

---

## 🧠 Work Reflection

Pick one recurring computation in your system (permissions, scoring, analytics). Sketch what “cache the subproblem” would look like in that flow.

---

## 🧩 Deliverables

- [ ] **Climbing Stairs** (top-down and bottom-up).  
- [ ] 100-word reflection: "Caching subproblems I've seen."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: DP problems have overlapping subproblems (same subproblem computed multiple times) and optimal substructure (optimal solution contains optimal solutions to subproblems).
- Hint 2: Top-down: recursive solution with memoization (cache results). Bottom-up: iterative solution building from base cases.
- Hint 3: Identify the recurrence relation: how does the answer for n depend on answers for smaller values?

**Edge Cases:**
- n = 0 or n = 1 (base cases)
- Very large n (considering integer overflow)
- Negative n (if problem allows)

**Common Pitfalls:**
- Not identifying overlapping subproblems
- Forgetting to memoize (exponential time)
- Off-by-one errors in recurrence relation
- Not handling base cases correctly
- Confusing top-down vs bottom-up

### Problem-Specific Hints

**Climbing Stairs:**
- Hint 1: To reach step n, you can come from step n-1 (1 step) or step n-2 (2 steps). What's the recurrence?
- Hint 2: ways(n) = ways(n-1) + ways(n-2). Base cases: ways(1) = 1, ways(2) = 2. This is Fibonacci!
- Hint 3: Top-down: recursive function with memoization. Bottom-up: start from ways[1] and ways[2], build up to n. Can optimize space to O(1) using two variables.

</details>

---

## ✅ Done When

You can explain how recursion + memoization mirrors cache lookups and reuse.

🏁 **20 pts**
