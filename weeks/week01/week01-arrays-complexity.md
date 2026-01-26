
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
- [ ] ~150-word reflection: *"Hidden complexity in one real system I've seen."*

---

## 🧱 Additional Practice

Sharpen your array and complexity skills further with these curated problems:

### Easy

- [Maximum Subarray](https://neetcode.io/problems/maximum-subarray)  
  Find the contiguous subarray with the largest sum (tests understanding of prefix sums/Kadane's algorithm).
- [Valid Anagram](https://neetcode.io/problems/is-anagram)  
  Determine if two strings are anagrams (tests frequency counting and array/hash map use).
- [Best Time to Buy and Sell Stock](https://neetcode.io/problems/best-time-to-buy-and-sell-stock)  
  Find maximum profit from one transaction (tests single-pass array traversal and min tracking).

### Medium

- [Product of Array Except Self](https://neetcode.io/problems/products-of-array-discluding-self)  
  Return an array where each element is the product of all other elements (tests prefix/suffix products and O(1) space tricks).
- [Longest Substring Without Repeating Characters](https://neetcode.io/problems/longest-substring-without-duplicates)  
  Find the length of the longest substring without repeating characters (tests sliding window and set/hash map).
- [3Sum](https://neetcode.io/problems/three-integer-sum)  
  Find all unique triplets that sum to zero (tests sorting, two pointers, and deduplication).

### Hard

- [First Missing Positive](https://neetcode.io/problems/first-missing-positive)  
  Find the smallest missing positive integer (tests in-place array manipulation and O(n) time).
- [Trapping Rain Water](https://neetcode.io/problems/trapping-rain-water)  
  Compute how much water can be trapped after raining (tests two-pointer and prefix/suffix max strategies).
- [Merge Intervals](https://neetcode.io/problems/merge-intervals)  
  Merge all overlapping intervals (tests sorting and in-place merging logic).

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

</details>

---

## ✅ Done When

- You can annotate any nested loop with time/space complexity in realistic units (input size → cost).
- You can explain when a plain array is appropriate over `ArrayList` in a hot code path.

🏁 **25 pts**
