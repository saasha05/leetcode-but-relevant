# Week 4: Prefix Sums & Difference Arrays - Practical Notes

Prefix sums are a common optimization strategy that precomputes cumulative sums to answer range sum queries in O(1). Useful for problems involving sums or counts over intervals, billing queries, and analytics.

---

## Basic Prefix Sum

### Concept
- `prefix[i]` = sum of elements from index 0 to i-1 (or 0 to i, depending on convention)
- Range sum from `i` to `j`: `prefix[j+1] - prefix[i]` (or `prefix[j] - prefix[i-1]`)

### Algorithm Example

```java
// Standard prefix sum array
public static int[] buildPrefixSum(int[] arr) {
    int n = arr.length;
    int[] prefix = new int[n + 1];
    
    // prefix[0] = 0 (empty prefix)
    for (int i = 0; i < n; i++) {
        prefix[i + 1] = prefix[i] + arr[i];
    }
    
    return prefix;
}

// Query range sum from index i to j (inclusive)
public static int rangeSum(int[] prefix, int i, int j) {
    return prefix[j + 1] - prefix[i];
}
```

### Alternative: In-place with ArrayList

```java
public static ArrayList<Integer> buildPrefixSum(int[] arr) {
    int n = arr.length;
    ArrayList<Integer> prefixSum = new ArrayList<>();
    
    // Initialize first element
    prefixSum.add(arr[0]);
    
    // Add present element with previous element
    for (int i = 1; i < n; i++) {
        prefixSum.add(prefixSum.get(i - 1) + arr[i]);
    }
    
    return prefixSum;
}
```

---

## Difference Array (Range Updates)

### Concept
- Efficiently apply range updates (add value to all elements in range [L, R])
- Use difference array: `diff[i] = arr[i] - arr[i-1]`
- To apply update: `diff[L] += value`, `diff[R+1] -= value`
- Reconstruct: `arr[i] = arr[i-1] + diff[i]`

### Algorithm Example

```java
// Apply range update: add 'val' to all elements from L to R
public static void rangeUpdate(int[] diff, int L, int R, int val) {
    diff[L] += val;
    if (R + 1 < diff.length) {
        diff[R + 1] -= val;
    }
}

// Build difference array from original array
public static int[] buildDiffArray(int[] arr) {
    int n = arr.length;
    int[] diff = new int[n];
    diff[0] = arr[0];
    
    for (int i = 1; i < n; i++) {
        diff[i] = arr[i] - arr[i - 1];
    }
    
    return diff;
}

// Reconstruct array from difference array
public static int[] reconstruct(int[] diff) {
    int n = diff.length;
    int[] arr = new int[n];
    arr[0] = diff[0];
    
    for (int i = 1; i < n; i++) {
        arr[i] = arr[i - 1] + diff[i];
    }
    
    return arr;
}
```

---

## Prefix Product

Similar to prefix sum, but for products. Useful for problems like "Product of Array Except Self".

```java
// Prefix and suffix products
public static int[] productExceptSelf(int[] nums) {
    int n = nums.length;
    int[] result = new int[n];
    
    // Left products
    result[0] = 1;
    for (int i = 1; i < n; i++) {
        result[i] = result[i - 1] * nums[i - 1];
    }
    
    // Right products (suffix)
    int right = 1;
    for (int i = n - 1; i >= 0; i--) {
        result[i] *= right;
        right *= nums[i];
    }
    
    return result;
}
```

---

## 2D Prefix Sums

For matrix/2D array range queries.

```java
// Build 2D prefix sum
public static int[][] build2DPrefixSum(int[][] matrix) {
    int m = matrix.length;
    int n = matrix[0].length;
    int[][] prefix = new int[m + 1][n + 1];
    
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            prefix[i + 1][j + 1] = matrix[i][j] 
                + prefix[i][j + 1] 
                + prefix[i + 1][j] 
                - prefix[i][j];
        }
    }
    
    return prefix;
}

// Query sum of submatrix from (r1, c1) to (r2, c2) inclusive
public static int submatrixSum(int[][] prefix, int r1, int c1, int r2, int c2) {
    return prefix[r2 + 1][c2 + 1] 
        - prefix[r1][c2 + 1] 
        - prefix[r2 + 1][c1] 
        + prefix[r1][c1];
}
```

---

## Real-World Applications

- **Billing systems**: "Total charges between date A and B"
- **Analytics**: "Daily active users in a time range"
- **Metrics**: "Request count in last N minutes"
- **Reporting**: Pre-aggregated data for dashboard queries
- **Range updates**: Batch updates to time-series data

---

## Questions to Think About (Prefix Sums)

- What range queries am I answering repeatedly?
- Can I precompute something to avoid rescanning?
- What does prefix[i] represent exactly?
- How do I derive a range result from two prefix values?
- Do negative numbers affect the correctness of my approach?
- Am I doing multiple range updates? (Consider difference array)
- Is this a 1D or 2D problem?

---

## How to Identify a Prefix Sum Problem

- The problem asks for sums or counts over subarrays or ranges
- You are computing overlapping ranges repeatedly
- A brute-force solution would recompute the same sums
- Constraints suggest multiple queries or repeated aggregation
- The input is static while queries vary
- You need to answer "sum from i to j" queries efficiently
- The problem involves range updates (difference array)

---

## Pitfalls to Avoid

- Off-by-one errors in prefix indexing (0-indexed vs 1-indexed)
- Forgetting to initialize the base prefix value (usually 0)
- Confusing prefix sum with a running sum
- Recomputing range sums instead of using differences
- Assuming all values are non-negative when they are not
- Not handling empty ranges or invalid indices
- Forgetting to account for inclusive vs exclusive ranges
- In 2D: Not subtracting the overlapping region twice