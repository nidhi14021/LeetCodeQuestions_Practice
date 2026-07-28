# 1523. Count Odd Numbers in an Interval Range

**Problem Link:** https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/

## Problem
Given two non-negative integers `low` and `high`, return the number of odd numbers between `low` and `high` (inclusive).

## Approach
- Find half of the numbers in the range using:
  ```text
  (high - low) // 2
  ```
- If either `low` or `high` is odd, there is one extra odd number in the range.
- Add `1` to the count in that case.
- Return the final count.

## Solution

```python
class Solution:
    def countOdds(self, low: int, high: int) -> int:
        count = (high - low) // 2

        if low % 2 != 0 or high % 2 != 0:
            count += 1

        return count
```

## Example 1

**Input:**

```text
low = 3
high = 7
```

**Process:**

```text
Numbers = 3, 4, 5, 6, 7

(high - low) // 2
= (7 - 3) // 2
= 2

low is odd, so add 1.

Count = 3
```

**Output:**

```text
3
```

---

## Example 2

**Input:**

```text
low = 8
high = 10
```

**Process:**

```text
Numbers = 8, 9, 10

(high - low) // 2
= (10 - 8) // 2
= 1

Neither low nor high is odd.

Count = 1
```

**Output:**

```text
1
```

## Complexity
- **Time Complexity:** `O(1)`
- **Space Complexity:** `O(1)`