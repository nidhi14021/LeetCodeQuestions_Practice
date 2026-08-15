# 1207. Unique Number of Occurrences

**Problem Link:** https://leetcode.com/problems/unique-number-of-occurrences/

## Problem

Given an array of integers `arr`, return `true` if the number of occurrences of each value is unique.

Otherwise, return `false`.

## Approach

- First, find all the different numbers in the array.
- Count how many times each number occurs using `arr.count()`.
- Store all occurrence counts in a list.
- Convert the occurrence list into a `set`.
- If the length of the list and set are the same, all occurrence counts are unique.

## Solution

```python
class Solution:
    def uniqueOccurrences(self, arr: List[int]) -> bool:
        counts = []

        for num in arr:
            if num not in counts:
                counts.append(num)

        occurrences = []

        for num in counts:
            occurrences.append(arr.count(num))

        return len(occurrences) == len(set(occurrences))
```

## Example 1

**Input:**

```text
arr = [1,2,2,1,1,3]
```

**Process:**

```text
1 → 3 times
2 → 2 times
3 → 1 time

Occurrences = [3,2,1]

All occurrence counts are different.
```

**Output:**

```text
true
```

---

## Example 2

**Input:**

```text
arr = [1,2]
```

**Process:**

```text
1 → 1 time
2 → 1 time

Occurrences = [1,1]

Both numbers have the same occurrence count.
```

**Output:**

```text
false
```

## Complexity

- **Time Complexity:** `O(n²)` because `arr.count()` and `num not in counts` can take `O(n)`.
- **Space Complexity:** `O(n)`