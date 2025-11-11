
# Week 34 — Merging & Intervals

**🎯 Objective**  
Reason about overlapping intervals to handle resource contention and allocation.

---

## 📘 Study Material

- [Merge Intervals — LeetCode](https://leetcode.com/problems/merge-intervals/)
- [Meeting Rooms II — LeetCode](https://leetcode.com/problems/meeting-rooms-ii/)
- [Interval Scheduling — GeeksforGeeks](https://www.geeksforgeeks.org/interval-scheduling-maximization/)

<details>
<summary><strong>Video Solutions</strong></summary>

- **Merge Intervals — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=44H3cEC2fFM
- **Meeting Rooms II — NeetCode YouTube**  
  Video walkthrough: https://www.youtube.com/watch?v=FdzJmTCVyJU

</details>

---

## 💡 Why It Matters (Senior Lens)

Intervals model *conflict windows* — overlapping jobs, time slots, or access ranges.

---

## 🧠 Work Reflection

Find one process in your system where overlap creates conflict (e.g., overlapping deployments). How could interval merging resolve it?

---

## 🧩 Deliverables

- [ ] **Merge Intervals** — [LeetCode](https://leetcode.com/problems/merge-intervals/)
- [ ] **Meeting Rooms II** — [LeetCode](https://leetcode.com/problems/meeting-rooms-ii/)
- [ ] 100-word reflection: "Intervals as contention resolution."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Intervals overlap if start of one is <= end of another. Sort intervals by start time to process in order.
- Hint 2: For merging: after sorting, if current interval overlaps with last merged, merge them. Otherwise add as new.
- Hint 3: For meeting rooms: track end times of active meetings. Use min-heap or sort start/end times separately.

**Edge Cases:**
- Empty intervals array
- Single interval
- No overlaps (all intervals separate)
- All intervals overlap (one big interval)
- Intervals with same start/end times

**Common Pitfalls:**
- Not sorting intervals first
- Incorrect overlap detection logic
- Off-by-one errors in comparison
- Not handling edge cases
- Confusing merge vs count logic

### Problem-Specific Hints

**Merge Intervals:**
- Hint 1: You need to merge overlapping intervals. Sort by start time. How do you detect if two intervals overlap?
- Hint 2: Intervals [a,b] and [c,d] overlap if a <= d and c <= b. After sorting, if current.start <= last.end, merge: last.end = max(last.end, current.end).
- Hint 3: Sort intervals by start. Initialize result with first interval. For each subsequent, if overlaps with last in result, merge. Otherwise add.

**Meeting Rooms II:**
- Hint 1: You need minimum rooms for all meetings. When does a room become free? Track end times of active meetings.
- Hint 2: Sort meetings by start time. Use min-heap of end times. For each meeting, if earliest end <= current start, reuse that room. Otherwise need new room.
- Hint 3: Or sort start and end times separately. Track active meetings. When start time encountered, increment. When end time, decrement. Maximum active is answer.

</details>

---

## ✅ Done When

You can detect and reason about overlaps or gaps using interval logic.

🏁 **20 pts**
