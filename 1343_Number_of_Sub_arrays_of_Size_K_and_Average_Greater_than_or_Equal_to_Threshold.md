# 1343. Number of Sub-arrays of Size K and Average Greater than or Equal to Threshold

**Problem Link:** https://leetcode.com/problems/number-of-sub-arrays-of-size-k-and-average-greater-than-or-equal-to-threshold/

## Problem
Given an integer array `arr` and two integers `k` and `threshold`, return the number of contiguous subarrays of size `k` whose average is greater than or equal to `threshold`.

## Approach
- Use a **fixed-size sliding window** of length `k`.
- Calculate the sum of the first `k` elements.
- If the average of the current window is greater than or equal to `threshold`, increment the count.
- Slide the window one element at a time:
  - Add the new element entering the window.
  - Remove the element leaving the window.
- Continue counting all valid subarrays.

## Solution

```python
class Solution:
    def numOfSubarrays(self, arr: List[int], k: int, threshold: int) -> int:
        sub_arr = sum(arr[:k])
        count = 0

        if sub_arr / k >= threshold:
            count += 1

        for i in range(k, len(arr)):
            sub_arr += arr[i]
            sub_arr -= arr[i - k]

            if sub_arr / k >= threshold:
                count += 1

        return count
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

> **Optimization:** Instead of checking `sub_arr / k >= threshold`, compare `sub_arr >= k * threshold` to avoid floating-point division.