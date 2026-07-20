# 137. Single Number II

**Problem Link:** https://leetcode.com/problems/single-number-ii/

## Problem
Given an integer array `nums`, every element appears **three times** except for one, which appears exactly once. Find the single element and return it.

## Approach
- Traverse the array.
- For each element, count its occurrences using `count()`.
- If the count is `1`, return that element.

## Solution

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        for i in range(len(nums)):
            if nums.count(nums[i]) == 1:
                return nums[i]
```

## Complexity
- **Time Complexity:** `O(n²)`
- **Space Complexity:** `O(1)`