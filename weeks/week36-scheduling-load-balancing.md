
# Week 36 — Scheduling, Intervals & Load Balancing

**🎯 Objective**  
Integrate heap and interval reasoning to model schedulers, rate limiters, and distributed workload balancing.

---

## 📘 Study Material

- [Task Scheduler — LeetCode](https://leetcode.com/problems/task-scheduler/)
- [Interval Partitioning — GeeksforGeeks](https://www.geeksforgeeks.org/interval-partitioning-problem-using-priority-queue-set-1/)
- [Rate Limiter Design — Baeldung](https://www.baeldung.com/java-rate-limiter)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Task Scheduler — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=s8p8ukTyA2I

</details>

---

## 💡 Why It Matters (Senior Lens)

Modern systems constantly balance throughput vs fairness — heaps and intervals are the mechanics behind it.

---

## 🧠 Work Reflection

Pick one distributed system (CI/CD, async worker pool). Identify where heap or interval logic implicitly appears.

---

## 🧩 Deliverables

- [ ] **Task Scheduler** — [LeetCode](https://leetcode.com/problems/task-scheduler/)
- [ ] Conceptual design: “Heap + Interval Scheduler.”  
- [ ] 150-word reflection: "Load balancing via interval logic."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Scheduling = deciding what runs next. Heaps prioritize by deadline/priority. Intervals track resource availability.
- Hint 2: Task scheduler: use max-heap of frequencies. Schedule most frequent tasks first, with cooldown period between same tasks.
- Hint 3: Load balancing: distribute tasks across available resources. Track resource availability as intervals, use heap to select best resource.

**Edge Cases:**
- All tasks same type (maximum cooldown needed)
- More tasks than can be scheduled
- Cooldown period longer than task count
- No tasks available
- Resource constraints

**Common Pitfalls:**
- Not handling cooldown correctly
- Not prioritizing correctly
- Off-by-one errors in scheduling
- Not considering fairness
- Ignoring resource constraints

### Problem-Specific Hints

**Task Scheduler:**
- Hint 1: You need to schedule tasks with cooldown between same tasks. What's the minimum time? How do you prioritize?
- Hint 2: Count task frequencies. Use max-heap. Schedule most frequent first, track when it can run again (cooldown). Use idle slots if needed.
- Hint 3: Greedy: always schedule task with highest frequency that's not in cooldown. If all in cooldown, use idle. Time = max(tasks.length, (maxFreq-1) * (n+1) + count of maxFreq tasks).

</details>

---

## ✅ Done When

You can reason about scheduling fairness and priority mathematically.

🏁 **25 pts**
