
# Week 02 — HashMaps & Frequency as Infrastructure

**🎯 Objective**  
Understand how `HashMap` works internally (buckets, load factor, collisions, tree bins) and when to trust or question O(1).

---

## 📘 Study Material

- **A Guide to Java HashMap — Baeldung**  
  Gist: Usage plus internals; baseline for how HashMap behaves.  
  Read: https://www.baeldung.com/java-hashmap
- **The Java HashMap Under the Hood — Baeldung**  
  Gist: Buckets, collisions, resize behavior, and Java 8+ treeification details.  
  Read: https://www.baeldung.com/java-hashmap-advanced
- **Internal Working of HashMap in Java — GeeksforGeeks**  
  Gist: Stepwise explanation of `put`/`get`, hashing, and collision resolution.  
  Read: https://www.geeksforgeeks.org/java/internal-working-of-hashmap-java/

<details>
<summary><strong>Video Solutions</strong></summary>

- **Valid Anagram — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=9UtInBqnCgA
- **Group Anagrams — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=vzdNOK2oB2E
- **Top K Frequent Elements — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=YPTqKIgVk-k
- **Encode and Decode Strings — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=B1k_sx-osg0

</details>

---

## 💡 Why It Matters (Senior Lens)

[Inference] Caches, session stores, routing tables, feature stores: all built on map semantics. You’re expected to reason about key choice, memory usage, and worst-case behavior.

---

## 🧠 Work Reflection

List three hot code paths (API gateway, auth, recsys, billing) where a map is or could be used. For each: key type, expected cardinality, acceptable memory, impact if distribution is skewed.

---

## 🧩 Deliverables

- [ ] **Valid Anagram**  
      NeetCode: https://neetcode.io/problems/is-anagram/question?list=neetcode150  
- [ ] **Group Anagrams**  
      NeetCode: https://neetcode.io/problems/anagram-groups/question?list=neetcode150
- [ ] **Top K Frequent Elements**  
      NeetCode: https://neetcode.io/problems/top-k-elements-in-list/question?list=neetcode150 
- [ ] **Encode and Decode Strings**  
      NeetCode: https://neetcode.io/problems/encode-and-decode-strings  
      LeetCode: https://leetcode.com/problems/encode-and-decode-strings/  
- [ ] ~150-word note: *"When 'O(1)' hashmap access degrades and how I'd detect it."*

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you need to count frequencies or check membership, HashMap gives you O(1) average-case lookups. What information do you need to store as the key?
- Hint 2: For frequency problems, consider: do you need the exact count, or just presence? That determines HashMap vs HashSet.
- Hint 3: Remember HashMap's worst-case is O(n) due to collisions. For interview problems, assume average O(1), but in production, consider key distribution.

**Edge Cases:**
- Empty strings or arrays
- All characters/elements are the same
- Case sensitivity (if problem doesn't specify)
- Unicode characters vs ASCII
- Very large input sizes (considering HashMap memory)

**Common Pitfalls:**
- Using HashMap when HashSet would suffice (only need membership, not count)
- Not considering character frequency vs element frequency
- Forgetting to handle empty inputs
- Using nested loops when HashMap eliminates the need

### Problem-Specific Hints

**Valid Anagram:**
- Hint 1: Two strings are anagrams if they have the same character frequencies. How can you count characters efficiently?
- Hint 2: You could sort both strings, but that's O(n log n). Can you count frequencies in O(n) using a HashMap?
- Hint 3: Count characters in first string (increment), then count in second string (decrement). If all counts are zero, they're anagrams. Or use two HashMaps and compare.

**Group Anagrams:**
- Hint 1: Anagrams have the same character frequencies. What could serve as a unique key for all anagrams of a word?
- Hint 2: You could use sorted string as key (all anagrams sort to same string), or character frequency map as key. Which is more efficient?
- Hint 3: Group words by their sorted character representation. All anagrams will have the same sorted form, so they'll map to the same key in your HashMap.

**Top K Frequent Elements:**
- Hint 1: First, count frequencies using HashMap. Then you need the K most frequent. What data structure helps you get the top K efficiently?
- Hint 2: After counting frequencies, you could sort by frequency (O(n log n)), but can you do better? Think about heap/priority queue.
- Hint 3: Use HashMap to count, then use a min-heap of size K to keep track of top K. Or use bucket sort if frequencies are bounded.

**Encode and Decode Strings:**
- Hint 1: You need to encode multiple strings into one string and decode it back. How can you handle strings of different lengths?
- Hint 2: Use a delimiter, but what if the delimiter appears in the strings? Use length prefix: encode as "length#string" for each string.
- Hint 3: When encoding, prepend each string with its length and a delimiter (e.g., "5#hello3#abc"). When decoding, read length, then read that many characters.

</details>

---

## ✅ Done When

- You can describe buckets, load factor, collisions, and worst-case complexity.
- [Inference] You challenge “just add a HashMap” with concrete questions (keys, growth, GC).

🏁 **25 pts**
