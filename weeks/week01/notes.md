# Week 1: Arrays & Complexity - Practical Notes

---

## Common Big O Patterns

- **O(1)**: Constant time — accessing an element by index in an array or a key in a hash map.
- **O(n)**: Linear time — iterating through an array or list once.
- **O(n²)**: Quadratic time — nested loops iterating over the same data.
- **O(log n)**: Logarithmic time — binary search in a sorted array.
- **O(n log n)**: Typical for efficient sorting algorithms like mergesort or heapsort.

---

## When to Use Arrays vs Maps vs Sets

- **Arrays**
  - Ordered collection, indexed access.
  - Use when order matters or you need quick access by index.
  - O(1) random access, O(n) search.
  
- **Maps (HashMap)**
  - Key-value pairs, fast lookup by key.
  - Use when you need to associate values with unique keys.
  - O(1) average-case lookup, O(n) worst-case (collisions).
  
- **Sets (HashSet)**
  - Collection of unique elements, fast membership checking.
  - Use when you need to avoid duplicates or check existence quickly.
  - O(1) average-case membership test.

---

## How to Identify an Array-Type Problem

- Input is a contiguous collection of values (e.g., `int[]`, `String[]`)
- You are asked to iterate, scan, or compare elements
- The problem mentions indices, positions, or ranges
- Constraints emphasize time complexity over structure (e.g., "one pass", "single traversal")
- You need to find pairs, triplets, or subarrays
- The problem involves finding maximum/minimum in a range

---

## Pitfalls to Avoid

- Using nested loops when a single pass would suffice
- Forgetting that searching an unsorted array is O(n)
- Ignoring edge cases like empty arrays or arrays of size 1
- Modifying the array without accounting for index shifts
- Assuming order does not matter when it actually does
- Not considering space-time tradeoffs (extra space for better time)
- Forgetting integer overflow when summing large arrays

---

## Questions to Think About (Arrays & Complexity)

- Can this be solved in one pass?
- What is the cost of iterating over this array?
- Am I doing repeated work that could be avoided?
- Would a map or set reduce time complexity?
- How does input size affect runtime in real systems?
- Is the array sorted? (Opens up binary search possibilities)
- Can I use two pointers instead of nested loops?

---

## Example: Reasoning About Time Complexity in Java

```java
int sum = 0;
for (int i = 0; i < arr.length; i++) {      // O(n)
    sum += arr[i];
}
```
- The loop runs `n` times where `n` is the length of `arr`.
- Each iteration is O(1), so total time complexity is **O(n)**.

**Nested loop example:**
```java
for (int i = 0; i < n; i++) {              // O(n)
    for (int j = 0; j < n; j++) {          // O(n)
        // O(1) operation
    }
}
```
- Total: **O(n²)** — each element compared with every other element.

---

## Algorithm Examples

### Kadane's Algorithm (Maximum Subarray Sum)
```java
// O(n) - Find maximum sum of contiguous subarray
public static int kadanes(int[] nums) {
    int maxSum = nums[0];
    int curSum = 0;

    for (int n : nums) {
        curSum = Math.max(curSum, 0);  // Reset if negative
        curSum += n;
        maxSum = Math.max(maxSum, curSum);
    }
    return maxSum;
}
```

### Index Placement (Cyclic Sort Pattern)
```java
// In-place placement of values toward their correct index
// Useful for problems like "First Missing Positive"
public void indexPlacement(int[] nums) {
    int n = nums.length;
    for (int i = 0; i < n; i++) {
        // Keep moving nums[i] to its home index while possible
        while (nums[i] > 0 && nums[i] <= n && nums[nums[i] - 1] != nums[i]) {
            int correctIndex = nums[i] - 1;
            // Swap nums[i] with nums[correctIndex]
            int temp = nums[i];
            nums[i] = nums[correctIndex];
            nums[correctIndex] = temp;
        }
    }
}
```

### Two Pointers (Array Reversal)
```java
// Reverse array in-place using two pointers
public void reverse(int[] nums) {
    int left = 0, right = nums.length - 1;
    while (left < right) {
        int temp = nums[left];
        nums[left] = nums[right];
        nums[right] = temp;
        left++;
        right--;
    }
}
```

---

## Real-World Applications

- **API latency**: Detecting O(n²) loops in request processing
- **Batch jobs**: Optimizing ETL pipelines that iterate over large datasets
- **JSON mapping**: Efficiently transforming nested data structures
- **Report generation**: Avoiding repeated scans over the same data
- **Hot paths**: Identifying performance bottlenecks in production code