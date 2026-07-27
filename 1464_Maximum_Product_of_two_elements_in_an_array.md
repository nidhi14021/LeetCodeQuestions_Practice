# 1464. Maximum Product of Two Elements in an Array

**Problem Link:** https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/

## Problem
Given an integer array `nums`, choose two different indices `i` and `j` such that:

```text
(nums[i] - 1) * (nums[j] - 1)
```

is maximized.

Return the maximum product.

## Approach (Brute Force)
- Initialize `max_val` to `0`.
- Use two nested loops to check every possible pair of elements.
- For each pair, calculate:
  ```text
  (nums[i] - 1) * (nums[j] - 1)
  ```
- If the current product is greater than `max_val`, update it.
- Return the maximum product.

## Solution

```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        max_val = 0

        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                ans = (nums[i] - 1) * (nums[j] - 1)

                if ans > max_val:
                    max_val = ans

        return max_val
```

## Example

**Input:**

```text
nums = [3,4,5,2]
```

**Process:**

```text
(3-1) × (4-1) = 2 × 3 = 6
(3-1) × (5-1) = 2 × 4 = 8
(3-1) × (2-1) = 2 × 1 = 2
(4-1) × (5-1) = 3 × 4 = 12
(4-1) × (2-1) = 3 × 1 = 3
(5-1) × (2-1) = 4 × 1 = 4
```

Maximum product:

```text
12
```

**Output:**

```text
12
```

## Complexity
- **Time Complexity:** `O(n²)`
- **Space Complexity:** `O(1)`