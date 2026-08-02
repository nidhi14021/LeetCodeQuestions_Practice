# 1636. Sort Array by Increasing Frequency

**Problem Link:** https://leetcode.com/problems/sort-array-by-increasing-frequency/

## Problem

Given an array of integers `nums`, sort the array in increasing order based on the frequency of the values.

If multiple values have the same frequency, sort them in **decreasing order**.

Return the sorted array.

---

## Approach (Hash Map + Custom Sorting)

- Use `Counter` to calculate the frequency of each number.
- Compare every pair of elements using nested loops.
- Swap elements according to the rules:
  - If the frequency of `nums[i]` is greater than `nums[j]`, swap them.
  - If both elements have the same frequency:
    - Place the larger value before the smaller value.
- Return the sorted array.

---

## Solution

```python
from collections import Counter

class Solution:
    def frequencySort(self, nums: List[int]) -> List[int]:
        count = Counter(nums)

        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if count[nums[i]] > count[nums[j]]:
                    nums[i], nums[j] = nums[j], nums[i]

                elif count[nums[i]] == count[nums[j]]:
                    if nums[i] < nums[j]:
                        nums[i], nums[j] = nums[j], nums[i]

        return nums