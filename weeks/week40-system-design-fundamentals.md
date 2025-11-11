
# Week 40 — System Design Fundamentals

**🎯 Objective**  
Translate algorithmic reasoning into scalable service design — the bridge from coding to architecture.

---

## 📘 Study Material

- [System Design Primer — GitHub](https://github.com/donnemartin/system-design-primer)
- [Baeldung — Designing Scalable Java Systems](https://www.baeldung.com/java-scalable-system-design)

<details>
<summary><strong>Video Solutions</strong></summary>

This week focuses on system design concepts. Review how algorithms from previous weeks apply to system design (caching, indexing, load balancing).

</details>

---

## 💡 Why It Matters (Senior Lens)

Understanding how algorithms influence latency, throughput, and complexity helps you build better systems, not just solve puzzles.

---

## 🧠 Work Reflection

Pick a service (notification, analytics, scheduler). Identify one algorithmic pattern that defines its behavior.

---

## 🧩 Deliverables

- [ ] 1-page design doc: "Algorithmic tradeoffs in <service>."

---

<details>
<summary><strong>💡 Problem-Solving Hints</strong></summary>

### Pattern Hints (General)

**Approach:**
- Hint 1: System design connects algorithms to infrastructure. How does your algorithm choice affect latency, throughput, cost?
- Hint 2: Think about: data structures for storage, algorithms for processing, tradeoffs between consistency and performance.
- Hint 3: Map algorithmic patterns to system components: hash maps → caches, heaps → schedulers, graphs → service dependencies.

**Edge Cases:**
- Scale considerations (what breaks at 10x, 100x?)
- Failure scenarios
- Consistency vs availability tradeoffs
- Cost optimization opportunities

**Common Pitfalls:**
- Not connecting algorithms to real system behavior
- Ignoring scale implications
- Not considering tradeoffs
- Over-engineering
- Not explaining reasoning

### Problem-Specific Hints

**System Design:**
- Hint 1: Identify the core algorithmic pattern in your service. How does it scale? What are the bottlenecks?
- Hint 2: Consider: what data structures store state? What algorithms process requests? How do they interact?
- Hint 3: Explain tradeoffs: why this algorithm? What are alternatives? How does complexity affect infrastructure cost?

</details>

---

## ✅ Done When

You can connect time complexity to infrastructure cost.

🏁 **25 pts**
