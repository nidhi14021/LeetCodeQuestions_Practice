# 1051. Height Checker

**Problem Link:** https://leetcode.com/problems/height-checker/

## Problem
A school is trying to take an annual photo of all the students.

The students are asked to stand in **non-decreasing order** by height.

Return the number of indices where the current order differs from the expected sorted order.

## Approach

- Create a sorted copy of the `heights` array called `expected`.
- Compare each element of `heights` with `expected`.
- If they are different, increment the count.
- Return the final count.

## Solution

```python
class Solution:
    def heightChecker(self, heights: List[int]) -> int:
        expected = sorted(heights)
        count = 0

        for i in range(len(heights)):
            if heights[i] != expected[i]:
                count += 1

        return count
```

## Example 1

**Input:**

```text
heights = [1,1,4,2,1,3]
```

**Process:**

```text
Original : [1,1,4,2,1,3]

Expected : [1,1,1,2,3,4]

Index 2 → 4 != 1 ✓
Index 4 → 1 != 3 ✓
Index 5 → 3 != 4 ✓
```

**Output:**

```text
3
```

---

## Example 2

**Input:**

```text
heights = [5,1,2,3,4]
```

**Process:**

```text
Original : [5,1,2,3,4]

Expected : [1,2,3,4,5]

All five positions are different.
```

**Output:**

```text
5
```

## Complexity

- **Time Complexity:** `O(n log n)` (sorting)
- **Space Complexity:** `O(n)`