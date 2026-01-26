# Week 3: Sliding Window - Practical Notes

A sliding window is a common optimization strategy for array/string problems that efficiently processes subarrays or substrings by expanding/contracting a window, avoiding repeated scanning of the same elements.

---

## Window Types

### Fixed-Size Window
- Window size remains constant as it slides
- Left and right pointers move together
- Common for: "subarray of size k", "every k elements"

**Pattern:**
```java
// Fixed window of size k
for (int R = 0; R < n; R++) {
    // Add nums[R] to window
    if (R >= k - 1) {  // Window is full
        // Process window
        // Remove nums[L] from window
        L++;
    }
}
```

### Variable-Size Window
- Window expands and contracts based on conditions
- Right pointer expands, left pointer contracts when condition is met
- Common for: "longest/shortest subarray", "minimum window", "at most k"

**Pattern:**
```java
// Variable window
int L = 0;
for (int R = 0; R < n; R++) {
    // Expand: add nums[R] to window
    while (window violates condition) {
        // Contract: remove nums[L] from window
        L++;
    }
    // Window is valid, process result
}
```

---

## Common Window Invariants

The invariant is the condition that must always be true for your window:

- **No duplicates**: All characters in window are unique
- **Sum constraint**: Window sum ≤ k, or window sum = k
- **Character coverage**: Window contains all required characters
- **Count constraint**: At most k distinct elements, or exactly k distinct elements

**Key insight:** The invariant determines when to expand vs contract.

---

## Algorithm Examples

### Example 1: Maximum Subarray Sum (Variable Window)
```java
// Return the left and right index of the max subarray sum
// Sliding window variation of Kadane's: O(n)
public static int[] maxSubarraySum(int[] nums) {
    int maxSum = nums[0];
    int curSum = 0;
    int maxL = 0, maxR = 0;
    int L = 0;

    for (int R = 0; R < nums.length; R++) {
        if (curSum < 0) {
            curSum = 0;
            L = R;
        }
        curSum += nums[R];
        if (curSum > maxSum) {
            maxSum = curSum;
            maxL = L; 
            maxR = R;     
        }    
    }    
    return new int[] {maxL, maxR};
}
```

### Example 2: Longest Substring Without Repeating Characters (Variable Window)
```java
// Return the longest substring with no repeating characters
public int lengthOfLongestSubstring(String s) {
    int len = s.length();
    int maxLen = 0, L = 0;
    Map<Character, Integer> chars = new HashMap<>();
    
    for (int R = 0; R < len; R++) {
        char currChar = s.charAt(R);
        // Move left pointer past last occurrence of current character
        if (chars.containsKey(currChar)) {
            L = Math.max(chars.get(currChar) + 1, L);
        }
        // Calculate length from pointers
        int currLen = R - L + 1;
        chars.put(currChar, R);
        maxLen = Math.max(maxLen, currLen);
    }
    return maxLen;
}
```

### Example 3: Minimum Window Substring (Variable Window)
```java
// Find minimum window containing all characters from target
public String minWindow(String s, String t) {
    Map<Character, Integer> need = new HashMap<>();
    for (char c : t.toCharArray()) {
        need.put(c, need.getOrDefault(c, 0) + 1);
    }
    
    int L = 0, R = 0;
    int valid = 0;  // Number of characters satisfied
    int start = 0, minLen = Integer.MAX_VALUE;
    Map<Character, Integer> window = new HashMap<>();
    
    while (R < s.length()) {
        char c = s.charAt(R);
        R++;
        
        // Expand window
        if (need.containsKey(c)) {
            window.put(c, window.getOrDefault(c, 0) + 1);
            if (window.get(c).equals(need.get(c))) {
                valid++;
            }
        }
        
        // Contract window when valid
        while (valid == need.size()) {
            if (R - L < minLen) {
                start = L;
                minLen = R - L;
            }
            
            char d = s.charAt(L);
            L++;
            
            if (need.containsKey(d)) {
                if (window.get(d).equals(need.get(d))) {
                    valid--;
                }
                window.put(d, window.get(d) - 1);
            }
        }
    }
    
    return minLen == Integer.MAX_VALUE ? "" : s.substring(start, start + minLen);
}
```

### Example 4: Fixed-Size Window Maximum
```java
// Maximum in each window of size k
public int[] maxSlidingWindow(int[] nums, int k) {
    int n = nums.length;
    int[] result = new int[n - k + 1];
    Deque<Integer> deque = new ArrayDeque<>();  // Store indices
    
    for (int R = 0; R < n; R++) {
        // Remove indices outside current window
        while (!deque.isEmpty() && deque.peekFirst() < R - k + 1) {
            deque.pollFirst();
        }
        
        // Remove smaller elements (they can't be max)
        while (!deque.isEmpty() && nums[deque.peekLast()] < nums[R]) {
            deque.pollLast();
        }
        
        deque.offerLast(R);
        
        // Window is complete
        if (R >= k - 1) {
            result[R - k + 1] = nums[deque.peekFirst()];
        }
    }
    
    return result;
}
```

---

## Real-World Applications

- **Rate limiting**: Track requests in a time window
- **Streaming analytics**: Rolling averages, moving medians
- **LLM context management**: Maintain token window within limits
- **Network monitoring**: Track packet rates, error rates over time windows
- **Session management**: Detect activity within time windows

---

## Questions to Think About (Sliding Window)

- What invariant does the window need to maintain?
- Is the window fixed-size or variable-size?
- When should the left pointer move?
- What state must be updated when expanding or shrinking the window?
- Does this replace a nested-loop scan over subarrays or substrings?
- How do I know when the window is valid vs invalid?
- What data structure helps track window state efficiently?

---

## How to Identify a Sliding Window Problem

- The problem involves subarrays or substrings
- You are working with contiguous ranges
- A brute-force approach would use nested loops
- The condition depends on a running range, not a single element
- The input can be processed incrementally from left to right
- You're asked for "longest", "shortest", "minimum", "maximum" subarray/substring
- The problem mentions "at most k", "at least k", or "exactly k" elements

---

## Pitfalls to Avoid

- Forgetting to maintain the window invariant
- Moving pointers without updating window state
- Off-by-one errors in window size calculation (R - L + 1)
- Applying sliding window to non-contiguous data
- Recomputing window state instead of updating it incrementally
- Not handling the case where no valid window exists
- Forgetting to update state when contracting the window
- Using nested loops inside the window expansion (defeats the purpose)