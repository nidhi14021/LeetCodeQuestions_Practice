# 3658. GCD of Odd and Even Sums

**Problem Link:** https://leetcode.com/problems/gcd-of-odd-and-even-sums/

## Problem
Given an integer `n`, find the GCD of:
- The sum of the first `n` odd numbers.
- The sum of the first `n` even numbers.

## Approach
- Calculate the sum of the first `n` even numbers using a loop.
- Calculate the sum of the first `n` odd numbers using a loop.
- Use Python's built-in `gcd()` function to find their greatest common divisor.

## Solution

```python
from math import gcd

class Solution:
    def gcdOfOddEvenSums(self, n: int) -> int:

        sumOdd = 0
        sumEven = 0

        for i in range(2, 2 * n + 1, 2):
            sumEven += i

        for i in range(1, 2 * n, 2):
            sumOdd += i

        return gcd(sumOdd, sumEven)
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`