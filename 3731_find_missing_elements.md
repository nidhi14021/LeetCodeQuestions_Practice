# 3731. Find Missing Elements

**Problem Link:** https://leetcode.com/problems/find-missing-elements/

## Problem
Given an integer array `nums`, return all the missing integers between the **minimum** and **maximum** values in the array.

## Approach
- Find the minimum and maximum values in the array.
- Traverse from the minimum value to the maximum value.
- For each number:
  - Check whether it exists in the array.
  - If it does not exist, add it to the result list.
- Return the list of missing elements.

## Solution

```python
class Solution:
    def findMissingElements(self, nums: List[int]) -> List[int]:
        min_num = min(nums)
        max_num = max(nums)
        arr = []

        for i in range(min_num, max_num + 1):
            if i not in nums:
                arr.append(i)

        return arr
```

## Example 1

**Input:**

```text
nums = [1, 3, 5, 6]
```

**Process:**

```text
Minimum = 1
Maximum = 6

1 → Present
2 → Missing
3 → Present
4 → Missing
5 → Present
6 → Present
```

**Output:**

```text
[2, 4]
```

---

## Example 2

**Input:**

```text
nums = [4, 7, 9]
```

**Process:**

```text
Minimum = 4
Maximum = 9

4 → Present
5 → Missing
6 → Missing
7 → Present
8 → Missing
9 → Present
```

**Output:**

```text
[5, 6, 8]
```

## Complexity

- **Time Complexity:** `O((max_num - min_num + 1) × n)`
- **Space Complexity:** `O(k)`

Where:
- `n` = length of the array.
- `k` = number of missing elements.