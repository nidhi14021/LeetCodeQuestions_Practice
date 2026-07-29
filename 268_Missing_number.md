# 268. Missing Number

**Problem Link:** https://leetcode.com/problems/missing-number/

## Problem
Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

## Approach
- Find the length of the array `n`.
- Iterate from `0` to `n`.
- For each number, check if it is present in `nums`.
- If it is not present, return that number as the missing number.

## Solution

```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)

        for i in range(0, n + 1):
            if i not in nums:
                return i
```

## Example 1

**Input:**

```text
nums = [3,0,1]
```

**Process:**

```text
0 → Present
1 → Present
2 → Missing
```

**Output:**

```text
2
```

---

## Example 2

**Input:**

```text
nums = [0,1]
```

**Process:**

```text
0 → Present
1 → Present
2 → Missing
```

**Output:**

```text
2
```

---

## Example 3

**Input:**

```text
nums = [9,6,4,2,3,5,7,0,1]
```

**Process:**

```text
0 → Present
1 → Present
2 → Present
3 → Present
4 → Present
5 → Present
6 → Present
7 → Present
8 → Missing
```

**Output:**

```text
8
```

## Complexity
- **Time Complexity:** `O(n²)` (checking `i not in nums` takes `O(n)` for each of the `n+1` values)
- **Space Complexity:** `O(1)`