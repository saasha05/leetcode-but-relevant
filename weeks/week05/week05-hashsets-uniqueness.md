
# Week 05 — HashSets, Uniqueness & Idempotency

**🎯 Objective**  
Use set semantics to enforce uniqueness, membership, and idempotent behavior.

---

## 📘 Study Material

- **Set vs List in Java — Baeldung**  
  Gist: Clarifies when uniqueness and membership checks justify a Set.  
  Read: https://www.baeldung.com/java-set-vs-list
- **HashSet in Java — GeeksforGeeks**  
  Gist: Operations, complexity, and backing via HashMap.  
  Read: https://www.geeksforgeeks.org/hashset-in-java/
- **HashSet vs ArrayList contains() Performance — Baeldung**  
  Gist: Why O(1) membership with sets matters at scale.  
  Read: https://www.baeldung.com/java-hashset-arraylist-contains-performance

<details>
<summary><strong>Video Solutions</strong></summary>

- **Contains Duplicate — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=3OamzN90kPg
- **Valid Anagram — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=9UtInBqnCgA
- **Valid Sudoku — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=TjFXEUCMqI8
- **Longest Consecutive Sequence — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=P6RZZMu_maU

</details>

---

## 💡 Why It Matters (Senior Lens)

[Inference] Idempotency keys, “process-once” guarantees, duplicate prevention in messages or payments — all are set problems.

---

## 🧠 Work Reflection

Identify a workflow that must be idempotent (e.g., charge, email, migration). How is it done now? How would you redesign with explicit set-based guarantees?

---

## 🧩 Deliverables

- [ ] **Contains Duplicate**  
      NeetCode: https://neetcode.io/problems/duplicate-integer/question?list=neetcode150
      LeetCode: https://leetcode.com/problems/contains-duplicate/  
- [ ] **Valid Anagram**  
      NeetCode: https://neetcode.io/problems/is-anagram/question?list=neetcode150 
      LeetCode: https://leetcode.com/problems/valid-anagram/  
- [ ] **Valid Sudoku**  
      NeetCode: https://neetcode.io/problems/valid-sudoku/question?list=neetcode150  
      LeetCode: https://leetcode.com/problems/valid-sudoku/  
- [ ] **Longest Consecutive Sequence**  
      NeetCode: https://neetcode.io/problems/longest-consecutive-sequence/question?list=neetcode150
      LeetCode: https://leetcode.com/problems/longest-consecutive-sequence/  
- [ ] Short reflection: "An idempotency strategy I trust or don't trust and why."

---

## 🧱 Additional Practice

Sharpen your HashSet and uniqueness skills further with these curated problems:

### Easy

- [Happy Number](https://neetcode.io/problems/non-cyclical-number/question?list=neetcode150)  
  Determine if a number is happy (tests cycle detection with HashSet).
- [Contains Duplicate II](https://neetcode.io/solutions/contains-duplicate-ii)  
  Check if array contains duplicate within k distance (tests sliding window + HashSet).

### Medium

- [Set Matrix Zeroes](https://neetcode.io/problems/set-zeroes-in-matrix)  
  Set entire row and column to zero if element is zero (tests in-place manipulation with sets).
- [Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/)  
  Count how many stones are jewels (tests HashSet membership checks).

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you need to check "have I seen this before?" or "is this unique?", HashSet gives O(1) membership checks.
- Hint 2: Sets are perfect for cycle detection: if you encounter something you've seen, you have a cycle. Think about this for "Happy Number".
- Hint 3: For consecutive sequences, think: what's the start of a sequence? If `num-1` doesn't exist, `num` is a sequence start. Use HashSet for O(1) lookups.

**Edge Cases:**
- Empty arrays
- Arrays with one element
- All elements are duplicates
- Negative numbers (if problem allows)
- Very large numbers (considering integer overflow)

**Common Pitfalls:**
- Using HashSet when you need frequency (should use HashMap)
- Not handling cycles correctly (infinite loops)
- Forgetting that HashSet doesn't preserve order
- Not considering space complexity (HashSet uses O(n) space)

### Problem-Specific Hints

**Contains Duplicate:**
- Hint 1: You need to check if any element appears more than once. What data structure gives you O(1) "have I seen this?" checks?
- Hint 2: As you iterate, add each element to a HashSet. If element already exists in set, you found a duplicate.
- Hint 3: Alternatively, compare HashSet size with array length. If sizes differ, there's a duplicate (but this doesn't tell you which element).

**Happy Number:**
- Hint 1: A number is happy if repeatedly summing squares of digits eventually reaches 1. What if it never reaches 1?
- Hint 2: If you see the same number twice during the process, you're in a cycle (not happy). Use HashSet to detect cycles.
- Hint 3: Keep computing sum of squares of digits. If result is 1, return true. If result is in your HashSet, return false (cycle detected). Otherwise, add to HashSet and continue.

**Valid Anagram:**
- Hint 1: Two strings are anagrams if they have the same character frequencies. How can you check this efficiently with sets?
- Hint 2: You could use two HashSets and compare, or use one HashSet to track characters from first string and remove from second.
- Hint 3: Or use HashMap for frequency counting, but with HashSet: add all chars from first string, then check if all chars from second string exist and remove them. If set is empty at end, they're anagrams.

**Valid Sudoku:**
- Hint 1: A valid Sudoku has no duplicates in rows, columns, or 3x3 boxes. How can you check for duplicates efficiently?
- Hint 2: Use HashSet to track seen numbers. For each cell, check if the number already exists in the current row, column, or box.
- Hint 3: Create sets for each row, column, and box. Box index = (row/3)*3 + (col/3). If a number is already in any of these sets, the Sudoku is invalid.

**Longest Consecutive Sequence:**
- Hint 1: You need the longest consecutive sequence. A sequence starts when `num-1` doesn't exist. How can you check this efficiently?
- Hint 2: Put all numbers in HashSet for O(1) lookups. For each number, if `num-1` doesn't exist, it's a sequence start. Count how long the sequence is.
- Hint 3: Only check sequences starting from numbers where `num-1` is missing. This ensures O(n) time (each number checked at most twice: once as start, once as part of another sequence).

</details>

---

## ✅ Done When

- You can clearly justify where sets belong (and where they’re overkill).
- You can talk concretely about uniqueness and idempotent system design.

🏁 **25 pts**
