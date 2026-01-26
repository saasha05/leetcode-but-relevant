# 🧠 AGENTS.md
> Internal guide for maintaining and extending the **leetcode-but-relevant** curriculum.

---

## 0. Why This File Exists

This is a **handoff document for humans and AI agents** working on this repo.

It captures:
- The intent behind the curriculum.
- How the phases fit together.
- How weeks are supposed to feel for a **senior/lead-level engineer**.
- Rules for adding, editing, or enriching content without diluting it.

If you are generating or editing content, read this before touching anything.

---

## 1. Target Audience & Constraints

Design everything for someone who:

- Is already a practicing engineer (mid → senior → lead), not a beginner.
- Has limited time: ~1 focused 2-hour block per week.
- Is rusty on "interview-style" problems but strong in real-world engineering.
- Cares about:
  - System behavior,
  - Tradeoffs,
  - Code correctness and maintainability,
  - Being able to pass serious interviews without turning into a LeetCode grinder.
- Is primarily using **Java** in examples and mental models (but files stay language-agnostic where possible).

Key principle:
**Every week must feel like it respects their time and brain.**

No hand-holding tutorials. No walls of code. No vibe of "for beginners." 

---

## 2. Overall Structure

- Curriculum length: **42 weeks**.
- Organized into **6 phases**.
- Implemented as **one markdown file per week** in `weeks/`.
- All weeks share a consistent structure:
  - 🎯 Objective
  - 📘 Study Material (verified / reputable)
  - 💡 Why It Matters (Senior Lens)
  - 🧠 Work Reflection
  - 🧩 Deliverables
  - ✅ Done When
  - 🏁 Points

Total points across the track are ~1000; they are for **self-accountability**, not grading.

---

## 3. Phase-by-Phase Narrative

This is the context that was missing.

Each phase exists for a specific conceptual shift. Use this when evolving, debugging, or extending the curriculum.

### Phase 1 — Arrays, Strings & Hashing (Weeks 1–6)

**Purpose:** Rebuild raw computational intuition.

- Focus on: complexity, iteration patterns, hash maps, sets, prefix sums, sliding window.
- Role: Clean up "I kinda remember this" into "I can see hidden O(n²) and data layout issues in real code."
- Expected by end:
  - Can reason about hot paths, caching needs, uniqueness, idempotency.
  - Can connect LeetCode-style problems directly to:
    - API latency,
    - billing/metrics queries,
    - duplicate prevention,
    - streaming windows.

### Phase 2 — Stacks, Queues & Pointers (Weeks 7–12)

**Purpose:** Build control-flow and execution-model intuition.

- Focus on: stack semantics, recursion behavior, monotonic stack, queues, BFS, two pointers, fast/slow pointers.
- Role: Turn interview patterns into mental models for:
  - call stacks,
  - async pipelines,
  - retries,
  - workflows,
  - cycle detection.
- Expected by end:
  - Reads stack traces as stories, not noise.
  - Can map queue/BFS and pointer patterns to production message flows and data scans.

### Phase 3 — Trees & Graphs (Weeks 13–18)

**Purpose:** Unlock graph-thinking as the default lens for systems.

- Focus on: traversals, LCA, serialization, grids/islands, graph representation, topological sort.
- Role: Replace "trees/graphs are scary interview topics" with:
  - "this is literally my service graph, ACL graph, data lineage graph."
- Expected by end:
  - Comfort modeling:
    - microservice dependencies,
    - rollout and migration DAGs,
    - config/ownership hierarchies,
    - failure domains.
  - Can talk about cycles, ordering, and connectivity like a staff engineer.

### Phase 4 — Dynamic Programming (Weeks 25–30)

**Purpose:** Make DP feel like **architecture and optimization**, not puzzles.

- Focus on: subproblems, memoization, knapsack-style tradeoffs, LIS, paths.
- Role: Show DP as:
  - caching,
  - planning,
  - diffing,
  - resource allocation,
  - long-term optimization.
- Expected by end:
  - Can explain how the same reasoning applies to:
    - rollout strategies,
    - scheduling,
    - experiment design,
    - cost management.

### Phase 5 — Binary Search, Heaps & Intervals (Weeks 31–36)

**Purpose:** Encode performance tuning, prioritization, and scheduling.

- Focus on: binary search (classic + parametric), heaps/priority queues, interval merging, scheduling.
- Role:
  - Binary search = threshold tuning.
  - Heaps = "what runs next".
  - Intervals = conflicts, capacity, and SLAs.
- Expected by end:
  - Can design/critique:
    - job schedulers,
    - query plans,
    - rate limiters,
    - deployment / maintenance windows.

### Phase 6 — Integration & Mock Interviews (Weeks 37–42)

**Purpose:** Synthesize everything into interview-ready and job-real behavior.

- Focus on:
  - Hybrid patterns,
  - realistic mock interviews,
  - system design framing,
  - behavioral clarity.
- Role:
  - Pressure-test: can this person show senior/lead-level thinking end-to-end?
- Expected by end:
  - Candidate can:
    - Solve mid/hard problems while narrating tradeoffs,
    - Do a system design that references concrete DS/Algo instincts,
    - Communicate clearly under interview constraints.

---

## 4. Design Rules for Weeks

When modifying or adding a week:

1. **Anchor to a real engineering behavior.**
   - Every week must answer: "Where does this show up in real systems?"
2. **Minimal but high-signal readings.**
   - Prefer:
     - Baeldung (Java, CS)
     - GeeksforGeeks (for standard CS topics)
     - Official docs
     - LeetCode / NeetCode pages
     - A small number of high-signal resources (system design primer, etc.)
   - No SEO-churn blogs. No filler.
3. **Reflections are non-optional.**
   - They are not fluff; they force transfer from "toy problem" → "production reasoning.

4. **Notes about patterns and common algorithms**
  - Each week has notes to reference for the topic to catch up or revise the topic
  - The notes should have the following
    - Questions to Think About
    - How to Identify a Prefix Sum Problem
    - Pitfalls to Avoid
    - Algorithm examples
  - There should be a focus on where each pattern is applied in the real world
5. **Voice & stance:**
   - Talking to a peer, not a student.
   - Assume context, but never assume memorization.
   - Focus on clarity, not hype.

---

## 5. How Agents Should Work With This Repo

If you are an AI agent (Cursor, etc.):

- ✅ Read `AGENTS.md` before making structural changes.
- ✅ Use `templates/week-template.md` when proposing new weeks.
- ✅ Keep all **existing weeks** stable; if adding content:
  - Prefer sections like "Further Reading" or "Extended Exercises".
  - Or create `weekXX-notes.md` instead of mutating the core spec.
- ✅ Ensure any new links are from reputable sources.
- ✅ Maintain the same headings, emoji markers, and tone.

- ❌ Do not:
  - Turn this into a beginner course.
  - Dump large code solutions.
  - Add vague motivational content.
  - Break the one-week-per-file convention.

---

## 6. Future Extensions (Optional)

Ideas that align with the existing design:

- **Phase 7 (optional):** Real-world systems:
  - Caches, search, feeds, payments, feature flags, etc.
  - Each mapped to a subset of patterns from Weeks 1–42.
- **AI Pairing Tracks:**
  - Show how to supervise LLMs:
    - Validate complexity,
    - Check invariants,
    - Catch hallucinated logic.
- **Company-specific tracks:**
  - Index subsets of weeks by role: Backend, Infrastructure, AI/ML, etc.

These should live in new files (e.g., `tracks/`), not by rewriting base weeks.

---

## 7. Mental Model Summary

If you're unsure whether a change "fits":

Ask:
1. Does it make a strong engineer **think better about real systems**?
2. Does it tie algorithms to **ownership, reliability, and performance**?
3. Does it respect the reader's time and intelligence?

If yes → it probably belongs.  
If no → don't add it.

---

