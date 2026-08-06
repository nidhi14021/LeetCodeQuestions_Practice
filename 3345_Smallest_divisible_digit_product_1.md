# 3345. Smallest Divisible Digit Product I

**Problem Link:** https://leetcode.com/problems/smallest-divisible-digit-product-i/

## Problem
You are given two integers `n` and `t`.

Return the **smallest number greater than or equal to `n`** such that the **product of its digits** is divisible by `t`.

## Approach (Brute Force)

- Start checking from the number `n`.
- Find the product of all its digits.
- If the product is divisible by `t`, return the current number.
- Otherwise, increment the number and repeat the process.

## Solution

```python
class Solution:
    def smallestNumber(self, n: int, t: int) -> int:
        while True:
            num = n
            product = 1

            while num > 0:
                product *= num % 10
                num //= 10

            if product % t == 0:
                return n

            n += 1
```

## Example 1

**Input:**

```text
n = 10
t = 2
```

**Process:**

```text
Number = 10

Digits:
1 × 0 = 0

0 % 2 = 0

Return 10
```

**Output:**

```text
10
```

---

## Example 2

**Input:**

```text
n = 15
t = 3
```

**Process:**

```text
15

1 × 5 = 5

5 % 3 ≠ 0

Try next number

16

1 × 6 = 6

6 % 3 = 0

Return 16
```

**Output:**

```text
16
```

## Complexity

- **Time Complexity:** `O(k × d)`
  - `k` = Number of integers checked.
  - `d` = Number of digits in each integer.

- **Space Complexity:** `O(1)`