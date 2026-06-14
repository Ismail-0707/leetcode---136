# 136. Single Number

## Problem
Given a non-empty array of integers `nums`, every element appears twice except for one. Find that single one.

## Approach - HashSet

Use a HashSet to track numbers:

- If a number is not present in the set, add it.
- If the number is already present, remove it.
- Since every duplicate appears twice, it gets added and then removed.
- At the end, only the unique element remains in the set.

## Algorithm

1. Create an empty HashSet.
2. Traverse the array.
3. If the current number exists in the set, remove it.
4. Otherwise, add it to the set.
5. Return the remaining element from the set.

## Code

```java
class Solution {
    public int singleNumber(int[] nums) {
        HashSet<Integer> set = new HashSet<>();

        for (int num : nums) {
            if (set.contains(num)) {
                set.remove(num);
            } else {
                set.add(num);
            }
        }

        return set.iterator().next();
    }
}
```

## Dry Run

Input:

```text
nums = [4,1,2,1,2]
```

Operations:

```text
4 -> {4}
1 -> {4,1}
2 -> {4,1,2}
1 -> {4,2}
2 -> {4}
```

Remaining element:

```text
4
```

Output:

```text
4
```

## Complexity Analysis

- Time Complexity: O(n)
- Space Complexity: O(n)

## Key Concept

A HashSet stores unique elements only. Duplicate numbers are removed when encountered the second time, leaving the single non-repeating element in the set.
