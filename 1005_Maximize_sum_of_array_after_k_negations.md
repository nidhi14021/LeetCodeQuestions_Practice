# 1005. Maximize Sum Of Array After K Negations

**Problem Link:** https://leetcode.com/problems/maximize-sum-of-array-after-k-negations/

## Problem

Given an integer array `nums` and an integer `k`, choose an index and negate `nums[i]` exactly `k` times.

Return the largest possible sum of the array after performing the `k` negations.

## Approach (Greedy)

- Sort the array.
- Find the smallest element.
- Negate the smallest element because changing the smallest value gives the best chance of increasing the sum.
- Decrease `k` by `1`.
- Repeat until `k` becomes `0`.
- Return the sum of the array.

## Solution

```python
class Solution:
    def largestSumAfterKNegations(self, nums: List[int], k: int) -> int:
        while k > 0:
            nums.sort()

            nums[0] = -nums[0]
            k -= 1

        return sum(nums)
```

## Example 1

**Input:**

```text
nums = [4,2,3]
k = 1
```

**Process:**

```text
Sort:
[2,3,4]

Negate smallest:
[-2,3,4]

Sum:
-2 + 3 + 4 = 5
```

**Output:**

```text
5
```

---

## Example 2

**Input:**

```text
nums = [3,-1,0,2]
k = 3
```

**Process:**

```text
Start:
[3,-1,0,2]

1st negation:
[-3,0,2,1]

2nd negation:
[-2,0,1,3]

3rd negation:
[-1,0,2,3]

Sum:
-1 + 0 + 2 + 3 = 4
```

**Output:**

```text
4
```

## Important Point

We must decrease `k` after every negation:

```python
k -= 1
```

Otherwise:

```python
while k > 0:
```

will never end and cause **TLE**.

## Complexity

- **Time Complexity:** `O(k × n log n)` because the array is sorted in every iteration.
- **Space Complexity:** `O(1)` excluding the sorting space.