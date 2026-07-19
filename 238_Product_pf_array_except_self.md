# 238. Product of Array Except Self

**Problem Link:** https://leetcode.com/problems/product-of-array-except-self/

## Problem
Given an integer array `nums`, return an array `answer` such that `answer[i]` is equal to the product of all the elements of `nums` except `nums[i]`.

You must solve it without using division and in `O(n)` time.

## Approach
- Create two arrays:
  - `prefix` stores the product of all elements before the current index.
  - `suffix` stores the product of all elements after the current index.
- Traverse from left to right to fill the `prefix` array.
- Traverse from right to left to fill the `suffix` array.
- Multiply the corresponding values of `prefix` and `suffix` to get the final answer.

## Solution

```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        n = len(nums)

        suffix = [1] * n
        prefix = [1] * n

        for i in range(1, n):
            prefix[i] = prefix[i - 1] * nums[i - 1]

        for i in range(n - 2, -1, -1):
            suffix[i] = suffix[i + 1] * nums[i + 1]

        ans = [1] * n

        for i in range(n):
            ans[i] = prefix[i] * suffix[i]

        return ans
```

## Example

**Input:**

```text
nums = [1,2,3,4]
```

**Prefix:**

```text
[1,1,2,6]
```

**Suffix:**

```text
[24,12,4,1]
```

**Output:**

```text
[24,12,8,6]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`