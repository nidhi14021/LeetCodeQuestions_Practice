# 2150. Find All Lonely Numbers in the Array

**Problem Link:** https://leetcode.com/problems/find-all-lonely-numbers-in-the-array/

## Problem
Given an integer array `nums`, return all the **lonely** numbers in the array.

A number is **lonely** if:
- It appears exactly once.
- Neither `num - 1` nor `num + 1` exists in the array.

## Approach
- Use `Counter` to store the frequency of each number.
- Traverse the array.
- If the current number appears only once:
  - Check that both `num - 1` and `num + 1` are not present in the frequency map.
- If both conditions are satisfied, add the number to the answer list.
- Return the final list.

## Solution

```python
from collections import Counter

class Solution:
    def findLonely(self, nums: List[int]) -> List[int]:
        freq = Counter(nums)
        arr = []

        for i in range(len(nums)):
            if freq[nums[i]] == 1:
                if nums[i] + 1 not in freq and nums[i] - 1 not in freq:
                    arr.append(nums[i])

        return arr
```

## Example

**Input:**

```text
nums = [10,6,5,8]
```

**Frequency Map:**

```text
{
 10:1,
 6:1,
 5:1,
 8:1
}
```

**Check:**

```text
10 → Unique, 9 and 11 not present ✅
6  → 5 is present ❌
5  → 6 is present ❌
8  → Unique, 7 and 9 not present ✅
```

**Output:**

```text
[10, 8]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`