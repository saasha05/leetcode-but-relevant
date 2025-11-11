
# Week 35 — Query Optimization & Search Strategy

**🎯 Objective**  
Apply search and heap patterns to query planning, indexing, and ranking.

---

## 📘 Study Material

- [Binary Search Trees & Indexing — Baeldung (CS)](https://www.baeldung.com/cs/binary-search-tree)
- [Database Indexing in DBMS — GeeksforGeeks](https://www.geeksforgeeks.org/database-indexing-in-dbms/)
- [Priority Queues in Query Planning — Medium](https://medium.com/@techqueryoptimization/priority-queues-in-database-query-plans-2abcf68b65b1)

<details>
<summary><strong>Video Solutions</strong></summary>

This week focuses on conceptual understanding rather than specific problems. Review binary search and heap patterns from previous weeks in the context of query optimization.

</details>

---

## 💡 Why It Matters (Senior Lens)

Binary search and heaps are query optimizers in disguise — balancing speed vs cost in execution plans.

---

## 🧠 Work Reflection

Take one real API or SQL query. How would you optimize latency via indexing or priority queues?

---

## 🧩 Deliverables

- [ ] Write a conceptual query plan using heap-based ordering.  
- [ ] 150-word essay: "Search logic in query planning."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: Query optimization = choosing efficient access patterns. Binary search for indexed lookups, heaps for result ordering.
- Hint 2: Indexes enable binary search on sorted data. B-tree indexes allow O(log n) lookups instead of O(n) scans.
- Hint 3: Result ranking uses heaps: maintain top K results as you scan, avoiding full sort.

**Edge Cases:**
- No indexes available (full table scan)
- Very large result sets
- Multiple indexes to choose from
- Query with multiple conditions
- Memory constraints

**Common Pitfalls:**
- Not considering index selectivity
- Over-indexing (slows writes)
- Not using heap for top K when K << n
- Ignoring query plan analysis
- Not considering data distribution

### Problem-Specific Hints

**Query Plan Design:**
- Hint 1: Think about access patterns: do you need exact match (hash index), range query (B-tree), or top K (heap)?
- Hint 2: For range queries, binary search on indexed column. For top K results, use min-heap of size K as you scan.
- Hint 3: Combine patterns: use index to filter, then heap to rank. Consider cost: index lookup + heap operations vs full scan + sort.

</details>

---

## ✅ Done When

You can explain query optimization as a binary search and heap problem combined.

🏁 **25 pts**
