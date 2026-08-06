# 1200. Minimum Absolute Difference

**Problem Link:** https://leetcode.com/problems/minimum-absolute-difference/

## Problem
Given an array of distinct integers `arr`, return all pairs of elements with the **minimum absolute difference** of any two elements.

Return the pairs in ascending order.

## Approach

- Sort the array.
- Find the minimum difference between every pair of adjacent elements.
- Traverse the sorted array again.
- If the difference between two adjacent elements equals the minimum difference, add the pair to the answer.
- Return the list of pairs.

## Solution

```python
class Solution:
    def minimumAbsDifference(self, arr: List[int]) -> List[List[int]]:
        arr.sort()

        diff = float('inf')

        for i in range(len(arr) - 1):
            if arr[i + 1] - arr[i] < diff:
                diff = arr[i + 1] - arr[i]

        ans = []

        for i in range(len(arr) - 1):
            if arr[i + 1] - arr[i] == diff:
                ans.append([arr[i], arr[i + 1]])

        return ans
```

## Example 1

**Input:**

```text
arr = [4,2,1,3]
```

**Process:**

```text
Sorted Array:

[1,2,3,4]

Differences:

2 - 1 = 1
3 - 2 = 1
4 - 3 = 1

Minimum Difference = 1

Pairs:
[1,2]
[2,3]
[3,4]
```

**Output:**

```text
[[1,2],[2,3],[3,4]]
```

---

## Example 2

**Input:**

```text
arr = [1,3,6,10,15]
```

**Process:**

```text
Sorted Array:

[1,3,6,10,15]

Differences:

3 - 1 = 2
6 - 3 = 3
10 - 6 = 4
15 - 10 = 5

Minimum Difference = 2

Pair:
[1,3]
```

**Output:**

```text
[[1,3]]
```

## Complexity

- **Time Complexity:** `O(n log n)` (Sorting the array)
- **Space Complexity:** `O(1)` (Ignoring the output list)