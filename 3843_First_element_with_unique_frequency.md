# 3843. First Element with Unique Frequency

**Problem Link:** https://leetcode.com/problems/first-element-with-unique-frequency/

## Problem

You are given an integer array `nums`.

Return the first element (scanning from left to right) in `nums` whose frequency is unique.

A frequency is unique if no other integer appears the same number of times in `nums`.

If there is no such element, return `-1`.

---

## Approach (Hash Map / Frequency Counting)

- Use `Counter` to store the frequency of each number.
- Store the count of frequencies using another `Counter`.
- Traverse the original array from left to right:
  - Check the frequency of the current element.
  - If that frequency occurs only once, return the element.
- If no element has a unique frequency, return `-1`.

---

## Solution

```python
from collections import Counter

class Solution:
    def firstUniqueFreq(self, nums: List[int]) -> int:
        count = Counter(nums)
        freq = Counter(count.values())

        for num in nums:
            if freq[count[num]] == 1:
                return num

        return -1