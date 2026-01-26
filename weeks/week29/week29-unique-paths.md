
# Week 29 — Unique Paths & Combinatorics vs DP

**🎯 Objective**  
Compare recurrence-based and combinatorial solutions to path-counting.

---

## 📘 Study Material

- [Unique Paths — LeetCode](https://leetcode.com/problems/unique-paths/)
- [Unique Paths II — LeetCode](https://leetcode.com/problems/unique-paths-ii/)
- [Dynamic Programming vs Combinatorics — Baeldung (CS)](https://www.baeldung.com/cs/dynamic-programming-vs-combinatorics)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Unique Paths — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=IlEsdxuD4lY
- **Unique Paths II — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=z6kwCB47t0c

</details>

---

## 💡 Why It Matters (Senior Lens)

In backend systems, some problems need DP; others just need math. Knowing when to stop coding and start calculating saves compute and time.

---

## 🧠 Work Reflection

Think about a prediction or estimation system. Where would you use formula vs iterative computation?

---

## 🧩 Deliverables

- [ ] **Unique Paths I & II.**  
- [ ] 100-word reflection: "DP or math — which scales better?"

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: To reach bottom-right, you need m-1 downs and n-1 rights in any order. This is a combinatorial problem: C(m+n-2, m-1).
- Hint 2: DP approach: paths[i][j] = paths[i-1][j] + paths[i][j-1]. Base case: paths[0][0] = 1, first row/column = 1.
- Hint 3: For obstacles, if cell has obstacle, paths[i][j] = 0. Otherwise same recurrence.

**Edge Cases:**
- 1x1 grid (1 path)
- Single row or column (1 path)
- Obstacle at start or end (0 paths)
- All obstacles
- Very large grid (considering integer overflow)

**Common Pitfalls:**
- Not recognizing combinatorial solution when no obstacles
- Off-by-one errors in grid indices
- Not handling obstacles correctly
- Forgetting base cases
- Not optimizing space (can use 1D array)

### Problem-Specific Hints

**Unique Paths I:**
- Hint 1: You need m-1 downs and n-1 rights. Number of ways = C(m+n-2, m-1) = (m+n-2)! / ((m-1)! * (n-1)!).
- Hint 2: DP: paths[i][j] = paths[i-1][j] + paths[i][j-1]. Initialize first row and column to 1.
- Hint 3: Can optimize space: use 1D array, update from left to right for each row.

**Unique Paths II:**
- Hint 1: Same as I, but obstacles block paths. If obstacle[i][j] = 1, paths[i][j] = 0.
- Hint 2: Initialize: if obstacle[0][0] = 1, return 0. First row/column: if obstacle, set to 0 and all subsequent to 0.
- Hint 3: Recurrence: if obstacle[i][j] = 1, paths[i][j] = 0. Otherwise, paths[i][j] = paths[i-1][j] + paths[i][j-1].

</details>

---

## ✅ Done When

You can select between combinatorial and iterative solutions rationally.

🏁 **20 pts**
