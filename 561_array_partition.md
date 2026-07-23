# 561. Array Partition

**Problem Link:** https://leetcode.com/problems/array-partition/

## Problem
Given an integer array `nums` of `2n` integers, group these integers into `n` pairs such that:

```text
(a1, b1), (a2, b2), ..., (an, bn)
```

The sum of the minimum value in each pair is maximized.

Return the maximum possible sum.

## Approach
- Sort the array in ascending order.
- Pair adjacent elements.
- Since the array is sorted, the first element in each pair is the minimum.
- Add every alternate element starting from index `0`.
- Return the total sum.

## Solution

```python
class Solution:
    def arrayPairSum(self, nums: List[int]) -> int:
        return sum(sorted(nums)[::2])
```

## Example

**Input:**

```text
nums = [1,4,3,2]
```

**Process:**

```text
Sorted Array: [1,2,3,4]

Pairs:
(1,2) -> min = 1
(3,4) -> min = 3

Sum = 1 + 3 = 4
```

**Output:**

```text
4
```

## Complexity
- **Time Complexity:** `O(n log n)` (sorting)
- **Space Complexity:** `O(n)` (due to `sorted()`)