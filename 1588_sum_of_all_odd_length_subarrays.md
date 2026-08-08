# 1588. Sum of All Odd Length Subarrays

**Problem Link:** https://leetcode.com/problems/sum-of-all-odd-length-subarrays/

## Problem

Given an array of positive integers `arr`, return the **sum of all possible odd-length subarrays**.

A subarray is a contiguous part of the array.

## Approach

- Use two loops to generate every possible subarray.
- Store the current subarray in `sub`.
- Check whether the length of the subarray is odd.
- If the length is odd, add its sum to `ans`.
- Return `ans`.

## Solution

```python
class Solution:
    def sumOddLengthSubarrays(self, arr: List[int]) -> int:
        ans = 0

        for i in range(len(arr)):
            for j in range(i, len(arr)):
                sub = arr[i:j+1]

                if len(sub) % 2 == 1:
                    ans += sum(sub)

        return ans
```

## Example 1

**Input:**

```text
arr = [1,4,2,5,3]
```

**Odd-Length Subarrays:**

```text
[1] = 1
[4] = 4
[2] = 2
[5] = 5
[3] = 3

[1,4,2] = 7
[4,2,5] = 11
[2,5,3] = 10

[1,4,2,5,3] = 15
```

**Total:**

```text
1 + 4 + 2 + 5 + 3 + 7 + 11 + 10 + 15 = 58
```

**Output:**

```text
58
```

## Complexity

- **Time Complexity:** `O(n³)` because `sum(sub)` can take `O(n)`.
- **Space Complexity:** `O(n)` because of the temporary `sub` list.