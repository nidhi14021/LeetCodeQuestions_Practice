# 338. Counting Bits

**Problem Link:** https://leetcode.com/problems/counting-bits/

## Problem
Given an integer `n`, return an array `ans` of length `n + 1` such that for each `i` (`0 <= i <= n`), `ans[i]` is the number of `1`'s in the binary representation of `i`.

## Approach
- Create an empty list `arr`.
- Traverse all numbers from `0` to `n`.
- Convert each number to its binary representation.
- Count the number of `'1'`s in the binary string.
- Append the count to `arr`.
- Return the final list.

## Solution

```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        arr = []

        for i in range(0, n + 1):
            bi = f"{i:b}"
            x = bi.count("1")
            arr.append(x)

        return arr
```

## Example

**Input:**

```text
n = 5
```

**Process:**

```text
0 -> 0     -> 0 ones
1 -> 1     -> 1 one
2 -> 10    -> 1 one
3 -> 11    -> 2 ones
4 -> 100   -> 1 one
5 -> 101   -> 2 ones
```

**Output:**

```text
[0,1,1,2,1,2]
```

## Complexity
- **Time Complexity:** `O(n log n)`
- **Space Complexity:** `O(n)`