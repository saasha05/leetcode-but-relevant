
# Week 03 — Strings, Sliding Window & Streaming

**🎯 Objective**  
Recognize and apply sliding-window patterns to substrings and streams, replacing brute-force scans with linear passes.

---

## 📘 Study Material

- **Sliding Window Algorithm — Baeldung (CS)**  
  Gist: How to convert nested loops into a single moving window with two pointers.  
  Read: https://www.baeldung.com/cs/sliding-window-algorithm
- **Sliding Window Technique — GeeksforGeeks**  
  Gist: Classic problems demonstrating fixed and variable window patterns.  
  Read: https://www.geeksforgeeks.org/window-sliding-technique/

<details>
<summary><strong>Video Solutions</strong></summary>

- **Longest Substring Without Repeating Characters — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=wiGpQwVHdE0
- **Minimum Window Substring — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=jSto0O4AJbM

</details>

---

## 💡 Why It Matters (Senior Lens)

[Inference] Sliding windows power rate limiting, rolling metrics, streaming analytics, and LLM context management. Pattern recognition here is a direct performance lever.

---

## 🧠 Work Reflection

Pick a real streaming/monitoring scenario (auth failures, error rates, token usage). Redesign it conceptually with a sliding window instead of recomputing over full history.

---

## 🧩 Deliverables

- [ ] **Longest Substring Without Repeating Characters**  
      NeetCode: https://neetcode.io/problems/longest-substring-without-repeating-characters  
      LeetCode: https://leetcode.com/problems/longest-substring-without-repeating-characters/  
- [ ] **Minimum Window Substring**  
      NeetCode: https://neetcode.io/problems/minimum-window-with-characters  
      LeetCode: https://leetcode.com/problems/minimum-window-substring/  
- [ ] Draw or describe the pointer movement and invariant for one of the above.

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you see "substring" or "subarray" problems, ask: can I use two pointers to maintain a window instead of checking all possible substrings?
- Hint 2: Sliding window has two types: fixed-size (window size is constant) and variable-size (window expands/contracts based on condition). Which does your problem need?
- Hint 3: The key is maintaining an invariant. What condition must your window satisfy? Track this as you expand/contract.

**Edge Cases:**
- Empty strings or arrays
- All characters/elements are the same
- String with only one unique character
- Window size larger than input
- No valid window exists

**Common Pitfalls:**
- Forgetting to update the window state when moving pointers
- Not handling the case where no valid window exists
- Off-by-one errors in pointer movement
- Not maintaining the invariant correctly (e.g., duplicate count in window)

### Problem-Specific Hints

**Longest Substring Without Repeating Characters:**
- Hint 1: You need the longest substring with all unique characters. As you expand the window, what happens when you encounter a duplicate?
- Hint 2: Use two pointers (left, right) and a HashMap/Set to track characters in current window. When you see a duplicate, shrink from left until it's gone.
- Hint 3: The invariant: your window always contains unique characters. When right pointer finds a duplicate, move left pointer past the previous occurrence of that character.

**Minimum Window Substring:**
- Hint 1: You need the minimum window containing all characters from target string. How do you know when your window is valid?
- Hint 2: Use two pointers and track how many characters from target you've matched. Expand right until window is valid, then shrink left to find minimum.
- Hint 3: Maintain a count of required characters. When count reaches zero, window is valid. Shrink left while maintaining validity to find minimum window.

</details>

---

## ✅ Done When

- You can state the invariant your window maintains (no duplicates, all chars covered, etc.).
- You can look at a nested-loop substring solution and see the sliding-window alternative.

🏁 **25 pts**
