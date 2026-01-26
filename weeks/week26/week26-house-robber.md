
# Week 26 — House Robber & Local Decisions

**🎯 Objective**  
Use DP to balance local and global optimization with exclusion constraints.

---

## 📘 Study Material

- [House Robber — LeetCode](https://leetcode.com/problems/house-robber/)
- [House Robber II — LeetCode](https://leetcode.com/problems/house-robber-ii/)
- [Optimal Substructure — Baeldung (CS)](https://www.baeldung.com/cs/optimal-substructure) — Core DP property definition.

<details>
<summary><strong>Video Solutions</strong></summary>

- **House Robber — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=73r3KWiEvyk
- **House Robber II — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=rWAJCfYYOt4

</details>

---

## 💡 Why It Matters (Senior Lens)

Greedy decisions feel simpler — DP ensures global optimality when local choices interact, like in resource allocation or feature rollout.

---

## 🧠 Work Reflection

Describe one engineering decision where local optimization backfired (e.g., aggressive caching). How could a DP mindset have improved it?

---

## 🧩 Deliverables

- [ ] **House Robber I & II.**  
- [ ] 150-word reflection: "Local vs global optimization."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you have exclusion constraints (can't pick adjacent items), DP helps find global optimum. Greedy (pick max) might miss better combinations.
- Hint 2: For each position, decide: rob it (add value, skip next) or skip it (consider next). Take the maximum.
- Hint 3: Recurrence: rob[i] = max(rob[i-2] + nums[i], rob[i-1]). Either rob current and skip previous, or skip current.

**Edge Cases:**
- Empty array
- Single house
- Two houses
- All houses have same value
- Very large values (considering integer overflow)

**Common Pitfalls:**
- Using greedy (always pick max) instead of DP
- Not handling exclusion constraint correctly
- Off-by-one errors in array indices
- Forgetting base cases
- Not optimizing space (can use O(1) with two variables)

### Problem-Specific Hints

**House Robber I:**
- Hint 1: You can't rob adjacent houses. For each house, decide: rob it or skip it. What's the maximum you can get?
- Hint 2: rob[i] = max(rob[i-2] + nums[i], rob[i-1]). Base cases: rob[0] = nums[0], rob[1] = max(nums[0], nums[1]).
- Hint 3: Use two variables: robPrev (max if rob previous) and robCurrent (max if rob current). Update: newRob = max(robPrev + nums[i], robCurrent).

**House Robber II:**
- Hint 1: Houses are arranged in a circle. First and last are adjacent. How can you handle this?
- Hint 2: Run House Robber I twice: once excluding first house, once excluding last house. Take maximum.
- Hint 3: If you rob first, can't rob last. If you rob last, can't rob first. So solve for [0, n-2] and [1, n-1], take max.

</details>

---

## ✅ Done When

You can explain tradeoffs between greedy vs dynamic strategies.

🏁 **20 pts**
