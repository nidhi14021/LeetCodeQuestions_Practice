# 507. Perfect Number

**Problem Link:** https://leetcode.com/problems/perfect-number/

## Problem
A perfect number is a positive integer that is equal to the sum of its positive divisors, excluding the number itself.

Given an integer `num`, return `true` if it is a perfect number; otherwise, return `false`.

## Approach
- If `num <= 1`, return `False` since 1 is not a perfect number.
- Initialize `total = 1` because `1` is a divisor of every positive integer.
- Iterate from `2` to `√num`.
- If `i` divides `num`, add both `i` and `num // i` to the sum.
- Avoid adding the square root twice when `i == num // i`.
- Finally, check whether the sum of divisors equals `num`.

## Solution

```python
class Solution:
    def checkPerfectNumber(self, num: int) -> bool:
        if num <= 1:
            return False

        total = 1

        for i in range(2, int(num ** 0.5) + 1):
            if num % i == 0:
                total += i
                if i != num // i:
                    total += num // i

        return total == num
```

## Complexity
- **Time Complexity:** `O(√n)`
- **Space Complexity:** `O(1)`