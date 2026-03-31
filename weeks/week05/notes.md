# Week 5: HashSets, Uniqueness & Idempotency - Practical Notes

HashSets provide O(1) average-case membership testing and enforce uniqueness. They're essential for duplicate detection, cycle detection, and idempotent system design.

---

## Core Concepts

- **Uniqueness**: HashSet stores only unique elements, automatically preventing duplicates
- **Membership Testing**: O(1) average-case `contains()` operation vs O(n) for lists
- **Cycle Detection**: If you encounter an element you've seen before, you've found a cycle
- **Idempotency**: Process-once guarantees using set-based tracking of processed items
- **Backing Structure**: HashSet in Java is backed by HashMap, so it shares similar performance characteristics

---

## When to Use HashSet vs HashMap vs List

- **HashSet**
  - Use when: You only need to check membership ("have I seen this?")
  - Use when: You need to enforce uniqueness
  - Use when: Order doesn't matter
  - Complexity: O(1) average-case add/remove/contains, O(n) worst-case (collisions)
  - Space: O(n) for n unique elements

- **HashMap**
  - Use when: You need to associate values with keys
  - Use when: You need frequency counts or key-value relationships
  - Use when: HashSet isn't enough (you need more than just membership)
  - Complexity: O(1) average-case operations, O(n) worst-case
  - Space: O(n) for n key-value pairs

- **List/ArrayList**
  - Use when: Order matters
  - Use when: Duplicates are allowed
  - Use when: You need indexed access
  - Complexity: O(1) indexed access, O(n) contains/search
  - Space: O(n) for n elements

**Rule of thumb**: If you only need "have I seen this?", use HashSet. If you need "how many times have I seen this?", use HashMap.

---

## How to Identify a HashSet Problem

- The problem asks about duplicates or uniqueness
- You need to check "have I seen this before?" repeatedly
- The problem involves cycle detection (repeated states)
- You need to track processed items for idempotency
- The problem asks "is this unique?" or "does this contain duplicates?"
- You're doing repeated membership checks that would be O(n) with a list
- Order doesn't matter, only presence/absence

---

## Pitfalls to Avoid

- Using HashSet when you need frequency counts (should use HashMap)
- Not handling cycles correctly, leading to infinite loops
- Forgetting that HashSet doesn't preserve insertion order (use LinkedHashSet if needed)
- Not considering space complexity (HashSet uses O(n) space)
- Using nested loops with list.contains() when HashSet would eliminate the inner search
- Not initializing the set before use
- Confusing HashSet with TreeSet (HashSet is O(1), TreeSet is O(log n) but maintains order)

---

## Questions to Think About (HashSets & Uniqueness)

- Do I only need to check membership, or do I need frequency counts?
- Is order important, or just presence/absence?
- What happens if I see the same element twice? (cycle detection)
- How can I ensure idempotency in this operation?
- Would repeated contains() checks on a list be a bottleneck?
- Can I use HashSet to eliminate nested loops?
- What's the worst-case behavior if hash distribution is poor?

---

## Algorithm Examples

### Example 1: Contains Duplicate
```java
// O(n) - Check if array contains any duplicate
public boolean containsDuplicate(int[] nums) {
    Set<Integer> seen = new HashSet<>();
    for (int num : nums) {
        if (seen.contains(num)) {
            return true;
        }
        seen.add(num);
    }
    return false;
}
```

### Example 2: Valid Sudoku
```java
// O(1) - Check if 9x9 Sudoku board is valid
// Uses HashSet to track seen numbers in rows, columns, and boxes
public boolean isValidSudoku(char[][] board) {
    Set<String> seen = new HashSet<>();
    
    for (int i = 0; i < 9; i++) {
        for (int j = 0; j < 9; j++) {
            char num = board[i][j];
            if (num == '.') continue;
            
            String rowKey = num + " in row " + i;
            String colKey = num + " in col " + j;
            String boxKey = num + " in box " + (i/3) + "-" + (j/3);
            
            if (!seen.add(rowKey) || !seen.add(colKey) || !seen.add(boxKey)) {
                return false;
            }
        }
    }
    return true;
}
```

### Example 3: Longest Consecutive Sequence
```java
// O(n) - Find longest consecutive sequence
// Key insight: Only check sequences starting from sequence beginnings
public int longestConsecutive(int[] nums) {
    Set<Integer> numSet = new HashSet<>();
    for (int num : nums) {
        numSet.add(num);
    }
    
    int longest = 0;
    for (int num : numSet) {
        // Only check if this is the start of a sequence
        if (!numSet.contains(num - 1)) {
            int currentNum = num;
            int currentStreak = 1;
            
            while (numSet.contains(currentNum + 1)) {
                currentNum++;
                currentStreak++;
            }
            
            longest = Math.max(longest, currentStreak);
        }
    }
    return longest;
}
```

### Example 4: Happy Number (Cycle Detection)
```java
// O(log n) - Determine if number is happy (reaches 1)
// Uses HashSet to detect cycles
public boolean isHappy(int n) {
    Set<Integer> seen = new HashSet<>();
    
    while (n != 1 && !seen.contains(n)) {
        seen.add(n);
        n = getNext(n);
    }
    
    return n == 1;
}

private int getNext(int n) {
    int sum = 0;
    while (n > 0) {
        int digit = n % 10;
        sum += digit * digit;
        n /= 10;
    }
    return sum;
}
```

### Example 5: Valid Anagram (Using HashSet)
```java
// O(n) - Check if two strings are anagrams using HashSet
// Alternative to HashMap frequency counting
public boolean isAnagram(String s, String t) {
    if (s.length() != t.length()) return false;
    
    // Count characters in first string
    Map<Character, Integer> count = new HashMap<>();
    for (char c : s.toCharArray()) {
        count.put(c, count.getOrDefault(c, 0) + 1);
    }
    
    // Decrement for second string
    for (char c : t.toCharArray()) {
        if (!count.containsKey(c)) return false;
        count.put(c, count.get(c) - 1);
        if (count.get(c) == 0) {
            count.remove(c);
        }
    }
    
    return count.isEmpty();
}
```

---

## Real-World Applications

- **Idempotency Keys**: Track processed request IDs to prevent duplicate processing in payment systems, email sends, or migrations
- **Duplicate Prevention**: Prevent duplicate messages in message queues, duplicate entries in databases, or duplicate API calls
- **Cycle Detection**: Detect infinite loops in state machines, recursive algorithms, or graph traversals
- **Session Management**: Track active sessions, logged-in users, or active connections
- **Cache Invalidation**: Track which cache keys have been invalidated
- **Feature Flags**: Track which users have seen which features (idempotent feature rollout)
- **Deduplication**: Remove duplicate records in ETL pipelines or data processing jobs

---

## Additional Notes

### HashSet vs LinkedHashSet vs TreeSet

**HashSet**:
- No order guarantee
- O(1) average-case operations
- Use when order doesn't matter

**LinkedHashSet**:
- Maintains insertion order
- O(1) average-case operations
- Use when you need order + uniqueness

**TreeSet**:
- Maintains sorted order
- O(log n) operations
- Use when you need sorted unique elements

### Cycle Detection Pattern

```java
// Generic cycle detection template
Set<State> seen = new HashSet<>();
State current = initialState;

while (current != null && !seen.contains(current)) {
    seen.add(current);
    current = getNextState(current);
}

// If current is null, no cycle. If current is in seen, cycle detected.
```

### Idempotency Pattern

```java
// Generic idempotency pattern
Set<String> processed = new HashSet<>();

public void processRequest(String requestId, Request request) {
    if (processed.contains(requestId)) {
        return; // Already processed, idempotent
    }
    
    // Process request
    doWork(request);
    
    // Mark as processed
    processed.add(requestId);
}
```

---

## Code Templates (Interview-Ready)

### Template 1: Duplicate Detection
```java
// Check for duplicates in array
public boolean hasDuplicate(int[] nums) {
    Set<Integer> seen = new HashSet<>();
    for (int num : nums) {
        if (!seen.add(num)) {  // add() returns false if already present
            return true;
        }
    }
    return false;
}
```

### Template 2: Cycle Detection
```java
// Detect cycle in sequence
public boolean hasCycle(State start) {
    Set<State> visited = new HashSet<>();
    State current = start;
    
    while (current != null) {
        if (visited.contains(current)) {
            return true; // Cycle detected
        }
        visited.add(current);
        current = getNext(current);
    }
    return false;
}
```

### Template 3: Unique Elements
```java
// Get unique elements from array
public List<Integer> getUnique(int[] nums) {
    Set<Integer> unique = new HashSet<>();
    for (int num : nums) {
        unique.add(num);
    }
    return new ArrayList<>(unique);
}
```

---

## Interview Takeaways

- HashSet is for membership testing, HashMap is for frequency counting
- Always consider: "Do I need counts or just presence?"
- Cycle detection is a classic HashSet use case
- Idempotency is a production concern that HashSet solves elegantly
- O(1) membership checks can eliminate nested loops
- Remember worst-case O(n) behavior due to hash collisions
- If order matters, use LinkedHashSet; if sorting matters, use TreeSet

