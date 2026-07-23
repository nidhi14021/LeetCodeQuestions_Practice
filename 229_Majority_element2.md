# 229. Majority Element II

**Problem Link:** https://leetcode.com/problems/majority-element-ii/

## Problem
Given an integer array `nums` of size `n`, return all elements that appear **more than ⌊n / 3⌋ times**.

## Approach
- Use `Counter` to store the frequency of each element.
- Calculate the threshold as `n // 3`.
- Traverse the array.
- If the frequency of the current element is greater than `n // 3` and it is not already in the answer list, add it.
- Return the final list.

## Solution

```python
from collections import Counter

class Solution:
    def majorityElement(self, nums: List[int]) -> List[int]:
        arr = []
        n = len(nums)
        x = n // 3

        freq = Counter(nums)

        for i in range(len(nums)):
            if freq[nums[i]] > x:
                if nums[i] not in arr:
                    arr.append(nums[i])

        return arr
```

## Example

**Input:**

```text
nums = [3,2,3]
```

**Process:**

```text
Frequency:
3 -> 2
2 -> 1

n = 3
Threshold = 3 // 3 = 1

3 appears 2 times (>1) ✅
2 appears 1 time (not >1) ❌
```

**Output:**

```text
[3]
```

## Example 2

**Input:**

```text
nums = [1,1,1,3,3,2,2,2]
```

**Output:**

```text
[1,2]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`