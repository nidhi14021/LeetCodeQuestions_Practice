# LeetCode 2357 — Make Array Zero by Subtracting Equal Amounts

**Problem Link:** https://leetcode.com/problems/make-array-zero-by-subtracting-equal-amounts/

**Difficulty:** Easy

## Solution

```python
class Solution:
    def minimumOperations(self, nums: List[int]) -> int:
        nums = set(nums)

        if 0 in nums:
            nums.remove(0)

        return len(nums)