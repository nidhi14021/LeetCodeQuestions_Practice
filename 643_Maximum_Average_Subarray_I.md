# 643. Maximum Average Subarray I

**Problem Link:** https://leetcode.com/problems/maximum-average-subarray-i/

## Problem
Given an integer array `nums` consisting of `n` elements and an integer `k`, find the contiguous subarray of length `k` that has the maximum average value and return that value.

## Approach
- Use a **fixed-size sliding window** of length `k`.
- Compute the sum of the first `k` elements.
- Slide the window one element at a time:
  - Add the new element entering the window.
  - Remove the element leaving the window.
- Track the maximum window sum.
- Return the maximum sum divided by `k` as the maximum average.

## Solution

```python
class Solution:
    def findMaxAverage(self, nums: List[int], k: int) -> float:
        max_val = sum(nums[:k])
        ans = max_val

        for i in range(k, len(nums)):
            max_val += nums[i]
            max_val -= nums[i - k]
            ans = max(max_val, ans)

        return ans / k
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`