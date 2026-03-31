
# Week 06 — Capstone: Data Layout & Hot Paths

**🎯 Objective**  
Integrate arrays, maps, sets, sliding windows, and prefix sums into how you reason about real production performance.

---

## 📘 Study Material

- **Choosing the Right Java Collection — Baeldung**  
  Gist: Overview mapping use cases to List, Set, Map, Queue.  
  Read: https://www.baeldung.com/java-collections

<details>
<summary><strong>Video Solutions</strong></summary>

- **Two Sum — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=KLlXCFG5TnA
- **Group Anagrams — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=vzdNOK2oB2E

</details>

---

## 🧠 Work Reflection

Pick one system or service you know well. For each hot path, document:
- Current data structures used
- Access patterns (reads/writes/frequency)
- One improvement based on Phase 1 concepts

---

## 🧩 Deliverables

- [X] Re-implement **Two Sum** and **Group Anagrams** from memory (no notes).  
- [ ] 1–2 page write-up: *"Data layout and lookup patterns in <system>, and what I'd change now."*
---

## 🧱 Additional Practice

Additional NeetCode 150 problems reinforcing concepts from Weeks 1-6 (Arrays, HashMaps, HashSets, Sliding Window, Prefix Sums):

### Easy

- [ ] [Two Sum II - Input Array Is Sorted](https://neetcode.io/problems/two-sum-ii-input-array-is-sorted)  
  Two pointers on sorted array (builds on Two Sum with sorted input optimization).
- [x] [Ransom Note](https://neetcode.io/problems/ransom-note/question?list=allNC)
  Character frequency counting with HashMap (similar to Valid Anagram with frequency constraints).
- [x] [First Unique Character in a String](https://neetcode.io/problems/first-unique-character-in-a-string/question?list=allNC)
  HashMap for character frequency tracking and iteration order.
- [ ] [Maximum Average Subarray I](https://leetcode.com/problems/maximum-average-subarray-i/)
  Fixed-size sliding window pattern.
- [ ] [Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)
  Classic prefix sum problem for range queries.
- [ ] [Intersection of Two Arrays](https://neetcode.io/problems/intersection-of-two-arrays?list=allNC)
  HashSet set intersection operations.
- [ ] [Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)
  HashMap frequency counting (requires frequency, not just membership).### Medium

- [ ] [Container With Most Water](https://neetcode.io/problems/container-with-most-water)
  Two pointers with area calculation optimization.
- [ ] [Sort Characters By Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
  HashMap frequency counting combined with sorting/heap.
- [ ] [Subarray Product Less Than K](https://neetcode.io/problems/subarray-product-less-than-k/question)
  Variable-size sliding window with product constraint.
- [ ] [Fruit Into Baskets](https://leetcode.com/problems/fruit-into-baskets/)
  Sliding window with at most K distinct elements constraint.
- [ ] [Maximum Number of Vowels in a Substring of Given Length](https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/)
  Fixed-size sliding window with character counting.
- [ ] [Contiguous Array](https://leetcode.com/problems/contiguous-array/)
  Prefix sum concept combined with HashMap for tracking.
- [ ] [Subarray Sum Divisible by K](https://leetcode.com/problems/subarray-sum-divisible-by-k/)
  Extends Subarray Sum Equals K pattern with modulo arithmetic.
- [ ] [Find All Duplicates in an Array](https://leetcode.com/problems/find-all-duplicates-in-an-array/)
  HashSet usage for finding all duplicates.
- [ ] [4Sum](https://leetcode.com/problems/4sum/)
  Extends 3Sum pattern, combines HashMap lookups, two pointers, and deduplication.
- [ ] [Partition Labels](https://leetcode.com/problems/partition-labels/)
  Combines HashMap tracking with sliding window concept.
- [ ] [Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)
  Combines sliding window with HashMap frequency counting (similar to Permutation In String).---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: This capstone integrates Phase 1 concepts. When re-implementing from memory, think: what's the core pattern? (HashMap for lookups, arrays for iteration, sets for uniqueness)
- Hint 2: For "Two Sum", remember: you need O(1) lookups for complement. For "Group Anagrams", remember: anagrams have same sorted form.
- Hint 3: The goal is to demonstrate you understand when to use which data structure. Can you explain your choice in terms of time/space complexity?

**Edge Cases:**
- Review edge cases from previous weeks (empty inputs, single elements, duplicates)
- Consider production scenarios: what if input is very large? What about memory constraints?

**Common Pitfalls:**
- Relying on memorized code instead of understanding the pattern
- Not being able to explain why you chose a particular data structure
- Forgetting to handle edge cases you've seen before

### Problem-Specific Hints

**Two Sum (Re-implementation):**
- Hint 1: From memory, recall: you need to find two numbers summing to target. What gives you O(1) lookups?
- Hint 2: Iterate once, storing each number and its index. For each number, check if complement exists.
- Hint 3: The pattern: HashMap eliminates nested loop. Time: O(n), Space: O(n) for the map.

**Group Anagrams (Re-implementation):**
- Hint 1: Anagrams have same character frequencies. What's a good key? (Sorted string or character count)
- Hint 2: Group words by their sorted character representation. All anagrams sort to same string.
- Hint 3: Use HashMap: key = sorted string, value = list of anagrams. Time: O(n*k log k) where k is average word length.

</details>

---

## ✅ Done When

- [Inference] You can defend each major collection choice in that system.
- You can map each Phase 1 problem to a real-world analogue: logs, lookups, uniqueness, streaming, aggregations.

🏁 **25 pts**
