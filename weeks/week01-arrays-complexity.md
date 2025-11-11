# Week 01 — Arrays & Complexity at Scale

**🎯 Objective**  
Build a precise mental model of contiguous storage, indexing cost, and iteration so you can spot performance issues in real Java services.

---

## 📘 Study Material

- **Array vs List Performance in Java — Baeldung**  
  Gist: Compares arrays and lists with benchmarks; clarifies when lower-level arrays matter.  
  Read: https://www.baeldung.com/java-array-vs-list-performance
- **Array vs ArrayList in Performance — StackOverflow Thread**  
  Gist: Real-world discussion reinforcing that arrays are faster in tight loops, but design clarity often dominates until scale.  
  Read: https://stackoverflow.com/questions/716597/array-or-list-in-java-which-is-faster

<details>
<summary><strong>Video Solutions</strong></summary>

- **Two Sum — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=KLlXCFG5TnA
- **Best Time to Buy and Sell Stock — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=1pkOgXD63yU

</details>

---

## 💡 Why It Matters (Senior Lens)

You review PRs and designs. Recognizing O(n²) loops or accidental copies across millions of entries is part of your job, not an interview trick.

---

## 🧠 Work Reflection

Identify one production path (batch job, ETL, JSON mapping, report generation) that might secretly be O(n²). Outline how a change in data layout or iteration strategy would reduce cost.

---

## 🧩 Deliverables

- [ ] **Two Sum**  
      NeetCode: https://neetcode.io/problems/two-integer-sum  
      LeetCode: https://leetcode.com/problems/two-sum/  
- [ ] **Best Time to Buy and Sell Stock**  
      NeetCode: https://neetcode.io/problems/best-time-to-buy-and-sell-stock  
      LeetCode: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/  
- [ ] ~150-word reflection: *"Hidden complexity in one real system I've seen."*

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you see "find two elements" or "pair that sums to X", think about what data structure gives you O(1) lookups.
- Hint 2: For array problems, consider: can you solve this in one pass? What information do you need to track as you iterate?
- Hint 3: Remember that arrays give you O(1) random access. If you're doing nested loops, ask: "What am I searching for in the inner loop that I could precompute?"

**Edge Cases:**
- Empty arrays or arrays with one element
- All elements the same value
- Negative numbers (if problem allows them)
- Integer overflow when summing

**Common Pitfalls:**
- Using nested loops when a hash map would eliminate the inner search
- Forgetting that array indexing is O(1) but searching is O(n)
- Not considering space-time tradeoffs (using extra space to reduce time)

### Problem-Specific Hints

**Two Sum:**
- Hint 1: You need to find two numbers that sum to target. As you iterate, what have you already seen that you might need later?
- Hint 2: If you've seen `nums[i]`, what value would you need to find to complete the pair? Can you store what you've seen for O(1) lookup?
- Hint 3: Store each number and its index as you iterate. For each new number, check if `target - current_number` exists in your stored values.

**Best Time to Buy and Sell Stock:**
- Hint 1: You can only make one transaction. What's the minimum price you've seen so far, and what's the maximum profit you could make selling today?
- Hint 2: Track the minimum price encountered so far. For each day, calculate profit if you sold today (price - min_so_far) and keep the maximum.
- Hint 3: This is a single-pass problem. You don't need to look ahead or behind—just track the best buying opportunity (minimum) and best selling opportunity (current price - minimum).

</details>

---

## ✅ Done When

- You can annotate any nested loop with time/space complexity in realistic units (input size → cost).
- You can explain when a plain array is appropriate over `ArrayList` in a hot code path.

🏁 **25 pts**
