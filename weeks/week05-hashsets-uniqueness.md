
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
- **Happy Number — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=ljz85bxOYJ0
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
      NeetCode: https://neetcode.io/problems/duplicate-integer  
      LeetCode: https://leetcode.com/problems/contains-duplicate/  
- [ ] **Happy Number**  
      LeetCode: https://leetcode.com/problems/happy-number/  
- [ ] **Longest Consecutive Sequence**  
      NeetCode: https://neetcode.io/problems/longest-consecutive-sequence  
      LeetCode: https://leetcode.com/problems/longest-consecutive-sequence/  
- [ ] Short reflection: "An idempotency strategy I trust or don't trust and why."

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
