
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

- [ ] Re-implement **Two Sum** and **Group Anagrams** from memory (no notes).  
- [ ] 1–2 page write-up: *"Data layout and lookup patterns in <system>, and what I'd change now."*

---

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
