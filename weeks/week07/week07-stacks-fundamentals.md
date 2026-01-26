
# Week 07 — Stack Fundamentals & Call Behavior

**🎯 Objective**  
Understand how stacks model call execution, recursion, and nested logic in programs.

---

## 📘 Study Material

- [A Guide to Stack in Java — Baeldung](https://www.baeldung.com/java-stack) — Overview of `Stack` class, push/pop behavior, and pitfalls.
- [Stack Data Structure (Java) — GeeksforGeeks](https://www.geeksforgeeks.org/stack-data-structure-introduction-program/) — Illustrates core operations with time complexities.
- [Stack Class (Java SE 17) — Oracle Docs](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Stack.html) — Official Java implementation and use cases.

<details>
<summary><strong>Video Solutions</strong></summary>

- **Valid Parentheses — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=WTzjTskDFMg
- **Min Stack — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=qkLl7nAwDPo

</details>

---

## 💡 Why It Matters (Senior Lens)

Call stacks underpin recursion, parsing, backtracking, undo systems, and memory management. As a lead, you should spot recursion depth risks and iterative refactor opportunities early.

---

## 🧠 Work Reflection

Find a production flow where recursion or nested logic could overflow the stack (e.g., tree traversal, parser, or data exporter). How would you refactor it?

---

## 🧩 Deliverables

- [ ] **Valid Parentheses** — [NeetCode](https://neetcode.io/problems/valid-parentheses)
- [ ] **Min Stack** — [NeetCode](https://neetcode.io/problems/min-stack)
- [ ] 100-word reflection on call stack depth and iterative alternatives.

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: When you see matching pairs, nested structures, or "last in, first out" logic, think stack. What needs to be processed in reverse order?
- Hint 2: Stacks are perfect for tracking state: push when entering, pop when exiting. Think about parentheses, function calls, or undo operations.
- Hint 3: For problems requiring O(1) access to minimum/maximum, maintain a separate stack or track the min/max as you push/pop.

**Edge Cases:**
- Empty input
- Single element
- All opening or all closing brackets
- Nested structures with maximum depth
- Stack overflow in recursive solutions

**Common Pitfalls:**
- Forgetting to check if stack is empty before popping
- Not handling mismatched pairs correctly
- Using recursion when iterative stack solution would be clearer
- Not maintaining min/max correctly in Min Stack problems

### Problem-Specific Hints

**Valid Parentheses:**
- Hint 1: You need to match opening and closing brackets. What data structure helps you track the most recent unclosed bracket?
- Hint 2: Use a stack. Push opening brackets, pop when you see matching closing bracket. If stack is empty at end, it's valid.
- Hint 3: When you see a closing bracket, check if stack is empty or if top doesn't match. If either is true, return false. Otherwise pop and continue.

**Min Stack:**
- Hint 1: You need O(1) access to minimum element. How can you track the minimum as elements are pushed and popped?
- Hint 2: Maintain a separate stack for minimums. When pushing, push min(current, minStack.top()) to min stack. When popping, pop from both.
- Hint 3: Or store pairs (value, min_so_far) in main stack. Or use a single stack with clever tracking of minimums.

</details>

---

## ✅ Done When

You can trace recursion as a stack evolution mentally and reason about base-case termination in any nested function.

🏁 **25 pts**
