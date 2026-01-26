
# Week 08 — Monotonic Stack & Predictive State

**🎯 Objective**  
Use monotonic stacks to track next/previous greater or smaller elements efficiently for predictive or alerting systems.

---

## 📘 Study Material

- [Monotonic Stack Pattern — LeetCode](https://leetcode.com/explore/learn/card/queue-stack/230/usage-stack/1363/) — Core intuition and examples.
- [Daily Temperatures Explained — Baeldung (CS)](https://www.baeldung.com/cs/monotonic-stack) — How monotonic stacks optimize lookahead.
- [Monotonic Stack — GeeksforGeeks](https://www.geeksforgeeks.org/monotonic-stack/) — Applications for stock span, temperature, skyline, etc.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Daily Temperatures — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=cTBiBSnjO3c
- **Next Greater Element I — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=68a1Dc_qVq4

</details>

---

## 💡 Why It Matters (Senior Lens)

Monotonic stacks are foundational in analyzing trends — used in time-series alerting, skyline computation, and range optimization. 

---

## 🧠 Work Reflection

Design an alerting mechanism detecting a “rising trend” (CPU utilization, error rate) without full rescans — just with stack logic.

---

## 🧩 Deliverables

- [ ] **Daily Temperatures** — [NeetCode](https://neetcode.io/problems/daily-temperatures)
- [ ] **Next Greater Element I** — [NeetCode](https://neetcode.io/problems/next-greater-element)
- [ ] 100-word reflection: "Predictive analysis via monotonic stacks."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you need to find "next greater/smaller element" or "previous greater/smaller", monotonic stack maintains elements in sorted order.
- Hint 2: Monotonic stack keeps elements in increasing or decreasing order. As you process elements, pop elements that violate the monotonic property.
- Hint 3: The key insight: when you find an element that's greater than stack top, you've found the "next greater" for all elements you pop.

**Edge Cases:**
- No next greater element exists (return -1 or 0)
- All elements are the same
- Array is already sorted (increasing or decreasing)
- Empty arrays
- Single element arrays

**Common Pitfalls:**
- Not handling the case where no next greater element exists
- Confusing increasing vs decreasing monotonic stack
- Forgetting to pop elements that are no longer needed
- Off-by-one errors in index tracking

### Problem-Specific Hints

**Daily Temperatures:**
- Hint 1: For each day, you need the number of days until a warmer temperature. What does "warmer" mean in terms of the stack?
- Hint 2: Use a decreasing monotonic stack (stack top is smallest). When you see a temperature greater than stack top, you've found warmer days for all popped elements.
- Hint 3: Store indices in stack. For each temperature, while stack is not empty and current temp > stack top temp, calculate days difference and pop.

**Next Greater Element I:**
- Hint 1: You need to find next greater element in nums2 for each element in nums1. How can you preprocess nums2?
- Hint 2: Build a HashMap: element → next greater element by processing nums2 with monotonic stack. Then lookup for nums1.
- Hint 3: Process nums2 from left to right with decreasing stack. When you find greater element, map popped elements to current element.

</details>

---

## ✅ Done When

You can identify monotonic patterns in data and sketch their algorithmic equivalents.

🏁 **25 pts**
