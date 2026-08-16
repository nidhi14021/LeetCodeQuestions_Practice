# 724. Find Pivot Index

**Problem Link:** https://leetcode.com/problems/find-pivot-index/

## Problem

Given an integer array `nums`, find the **pivot index**.

The pivot index is the index where:

```text
Sum of elements on the left = Sum of elements on the right
```

The pivot element itself is not included in either sum.

If there is no pivot index, return `-1`.

If there are multiple pivot indexes, return the **leftmost** one.

## Approach

- Calculate the total sum of the array.
- Keep track of the sum of elements on the left using `left_sum`.
- For every index:
  - The right sum is:

```text
right_sum = total_sum - left_sum - nums[i]
```

- If `left_sum == right_sum`, return the current index.
- Otherwise, add the current element to `left_sum`.
- If no pivot index is found, return `-1`.

## Solution

```python
class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        total = sum(nums)
        left_sum = 0

        for i in range(len(nums)):
            right_sum = total - left_sum - nums[i]

            if left_sum == right_sum:
                return i

            left_sum += nums[i]

        return -1
```

## Example 1

**Input:**

```text
nums = [1,7,3,6,5,6]
```

**Process:**

```text
Index 0:
Left = 0
Right = 27

Index 1:
Left = 1
Right = 20

Index 2:
Left = 8
Right = 17

Index 3:
Left = 11
Right = 11 ✓
```

So, the pivot index is `3`.

**Output:**

```text
3
```

## Example 2

**Input:**

```text
nums = [1,2,3]
```

```text
Index 0:
Left = 0
Right = 5

Index 1:
Left = 1
Right = 3

Index 2:
Left = 3
Right = 0
```

No pivot index exists.

**Output:**

```text
-1
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`