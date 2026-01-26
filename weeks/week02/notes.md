# Week 2: HashMaps & Frequency - Practical Notes

This note compares three common approaches used in problems like **Top K Frequent Elements**, focusing on **trade-offs, constraints, and real-world usage**.

---

## 1. Sorting-based approach

### Idea
- Count frequencies using a map.
- Sort all distinct elements by frequency.
- Take the top `k`.

### Complexity
- Time: `O(m log m)` where `m = number of distinct elements`
- Space: `O(m)`

### When it works well
- Small input sizes
- One-off batch computations
- When you need **fully ordered results**, not just top `k`
- When simplicity/readability is more important than optimal asymptotics

### Downsides
- Sorts *everything*, even when `k` is small
- Wasteful for large datasets

### Real-world analogy
- Running an analytics job where the dataset fits comfortably in memory and latency is not critical (e.g., offline reports, dashboards).

---

## 2. Priority Queue approach

### Min-heap vs Max-heap in Priority Queues

Java’s `PriorityQueue` is a **min-heap by default**. The choice between min-heap and max-heap depends on *what you want to discard* during processing.

#### Min-heap (most common for Top-K)
- The **smallest element is at the top**
- Used when you want to **keep the best `k` elements seen so far**
- When heap size exceeds `k`, you remove the *worst* candidate

Typical use cases:
- Top K frequent elements
- K largest / K smallest problems
- Streaming data where memory is limited

Why it fits Top-K problems:
- You always want quick access to the *least valuable* item among the top `k`
- Eviction is `O(log k)`

#### Max-heap
- The **largest element is at the top**
- Used when you want to repeatedly extract the *global maximum*

Typical use cases:
- Sorting (heap sort)
- Repeatedly pulling highest-priority tasks
- Problems where you need the full ordering

Why it is usually *not* used for Top-K:
- You still need to remove the smallest element when size exceeds `k`
- That operation is inefficient with a max-heap

#### Rule of thumb
- **Keep top K elements** → Min-heap of size K  
- **Repeatedly extract max/min globally** → Max-heap / Min-heap accordingly

#### Java note
To create a max-heap in Java:
```
PriorityQueue<Integer> maxHeap =
    new PriorityQueue<>(Collections.reverseOrder());
```

For Top-K frequency problems, **min-heap + size constraint** is almost always the correct choice.

### Idea
- Count frequencies.
- Maintain a **min-heap of size `k`**.
- Remove the smallest-frequency element whenever size exceeds `k`.

### Complexity
- Time: `O(n + m log k)`
- Space: `O(m + k)`

### Why a min-heap
- The heap root is always the *worst* of the current top `k`.
- Easy to evict when a better candidate appears.

### When it works well
- `k` is much smaller than `m`
- Large datasets
- Memory constraints matter
- Streaming or incremental processing (with stored counts)

### Downsides
- Slightly more complex to reason about
- Does not produce a fully sorted result unless post-processed

### Real-world analogy
- Real-time leaderboards
- Top-N queries in databases
- Monitoring systems (top error types, top users, top endpoints)

---

## 3. Bucket Sort (Frequency Buckets)

### Idea
- Frequencies are bounded by `n`.
- Create an array of buckets indexed by frequency.
- Place numbers into `bucket[freq]`.
- Scan buckets from high → low.

### Complexity
- Time: `O(n)`
- Space: `O(n)`

### When it works well
- Frequency range is **small and bounded**
- Exact top-k required
- Batch processing
- Competitive programming / interviews

### Downsides
- Requires `O(n)` extra memory
- Not suitable for streaming
- Not viable if frequency range is large or unbounded

### Real-world analogy
- Histogram-style analytics
- Pre-aggregated logs
- Situations where data fits in memory and max frequency is known

---

## Choosing the right approach (rule of thumb)

| Constraint / Requirement | Best Choice |
|--------------------------|-------------|
| Small input | Sorting |
| Large input, small `k` | Min-heap |
| Tight memory | Min-heap |
| Need full ordering | Sorting |
| Bounded frequencies | Bucket sort |
| Streaming / online | Heap or approximate algorithms |

---

## Algorithms (Canonical Examples)

This section lists well-known algorithm patterns that commonly use **sorting**, **heaps**, or **bucket-style techniques**, along with why that choice fits.

---

### Code Templates (Java)

These are **minimal, interview-ready templates** for each approach. They are not optimized for edge embellishments—they show the core idea clearly.

---

#### Sorting-based (Top K Frequent)

```java
Map<Integer, Integer> freq = new HashMap<>();
for (int n : nums) {
    freq.put(n, freq.getOrDefault(n, 0) + 1);
}

List<Map.Entry<Integer, Integer>> entries =
    new ArrayList<>(freq.entrySet());

entries.sort((a, b) -> b.getValue() - a.getValue());

int[] result = new int[k];
for (int i = 0; i < k; i++) {
    result[i] = entries.get(i).getKey();
}
```

---

#### Min-Heap (PriorityQueue) — Preferred

```java
Map<Integer, Integer> freq = new HashMap<>();
for (int n : nums) {
    freq.put(n, freq.getOrDefault(n, 0) + 1);
}

PriorityQueue<int[]> heap = new PriorityQueue<>(
    (a, b) -> a[1] - b[1]   // min-heap by frequency
);

for (Map.Entry<Integer, Integer> e : freq.entrySet()) {
    heap.offer(new int[]{e.getKey(), e.getValue()});
    if (heap.size() > k) {
        heap.poll(); // remove smallest frequency
    }
}

int[] result = new int[k];
int i = 0;
while (!heap.isEmpty()) {
    result[i++] = heap.poll()[0];
}
```

---

#### Bucket Sort (Frequency Buckets)

```java
Map<Integer, Integer> freq = new HashMap<>();
for (int n : nums) {
    freq.put(n, freq.getOrDefault(n, 0) + 1);
}

List<Integer>[] buckets = new List[nums.length + 1];

for (Map.Entry<Integer, Integer> e : freq.entrySet()) {
    int count = e.getValue();
    if (buckets[count] == null) {
        buckets[count] = new ArrayList<>();
    }
    buckets[count].add(e.getKey());
}

int[] result = new int[k];
int idx = 0;
for (int f = buckets.length - 1; f >= 0 && idx < k; f--) {
    if (buckets[f] != null) {
        for (int num : buckets[f]) {
            result[idx++] = num;
            if (idx == k) break;
        }
    }
}
```

---

**Interview note:**  
If you can write *one* of these from memory and explain *why* you chose it, that’s usually sufficient.

---

### Sorting-based algorithms

**Examples**
- Top K Frequent Elements (naive)
- Sort Characters by Frequency
- Merge Intervals (after sorting)
- Activity Selection (by end time)
- Scheduling / interval problems with full ordering

**Why sorting**
- You need a **global order**
- You need to process *all* elements in ranked sequence
- Constraints are small or batch-oriented

**Mental model**
> “I need to see everything in order.”

---

### Heap-based algorithms (Priority Queue)

**Examples**
- Top K Frequent Elements
- Kth Largest / Kth Smallest Element
- Merge K Sorted Lists
- Sliding Window Maximum
- Dijkstra’s shortest path
- Task scheduling / CPU scheduling

**Why heaps**
- You only care about the **best or worst element at any moment**
- You want **incremental selection**
- `k` is small relative to input size
- Streaming or online input

**Mental model**
> “I only care about the next best candidate.”

---

### Bucket / Counting-based algorithms

**Examples**
- Top K Frequent Elements (bucket version)
- Sort Colors (Dutch National Flag variant)
- Counting Sort
- Frequency arrays (anagrams, character counts)
- Histogram-based analytics

**Why buckets**
- Values or frequencies are **bounded**
- You want **linear time**
- Memory trade-off is acceptable

**Mental model**
> “The value range is small — index directly.”

---

### When NOT to use each

**Avoid sorting when**
- `k` is small and input is large

**Avoid heaps when**
- You need full ordering
- Heap operations dominate runtime

**Avoid buckets when**
- Value or frequency range is large/unbounded
- Memory is constrained
- Input is streaming

---

### Interview signal
Being able to say:
- *“This is a heap problem because I only need the top k as I iterate”*
- *“This is a bucket problem because frequencies are bounded by n”*

is often more important than writing the code perfectly.

---

## Interview takeaway
- Sorting is correct but often suboptimal.
- Heap is the safest general-purpose solution.
- Bucket sort is optimal **only when constraints allow it**.
- Always state **why** you chose an approach.

## Questions to Think About (HashMaps & Frequency)

- What is the key and what is the value?
- Do I need presence, exact counts, or ordering by frequency?
- Is average-case O(1) map access acceptable for this use case?
- Do I need the top K elements or a full ordering?
- Are frequencies bounded by input size?

## How to Identify a HashMap / Frequency Problem

- The problem asks how often elements appear
- You need to group items by a derived key
- Membership or counts matter more than order
- Constraints hint at counting or aggregation
- You are asked for “most frequent”, “group by”, or “top K”

## Pitfalls to Avoid

- Sorting when only top K is required
- Using a HashMap when a HashSet would suffice
- Ignoring worst-case HashMap behavior entirely
- Choosing the wrong heap type (min vs max)
- Over-allocating buckets when frequency bounds are unclear