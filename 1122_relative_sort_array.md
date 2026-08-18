# 1122. Relative Sort Array

**Problem Link:** https://leetcode.com/problems/relative-sort-array/

## Problem

Given two arrays `arr1` and `arr2`, sort the elements of `arr1` so that:

- The elements that appear in `arr2` come first.
- They should appear in the same order as they appear in `arr2`.
- If an element appears multiple times in `arr1`, include all its occurrences.
- The remaining elements that are not present in `arr2` should be placed at the end in ascending order.

## Approach

- Create an empty array `arrnew`.
- Traverse every number in `arr2`.
- Find that number in `arr1`.
- Add all its occurrences to `arrnew`.
- Remove the added elements from `arr1`.
- Sort the remaining elements of `arr1`.
- Add the remaining elements to `arrnew`.
- Return `arrnew`.

## Solution

```python
class Solution:
    def relativeSortArray(self, arr1: List[int], arr2: List[int]) -> List[int]:
        arrnew = []

        for num in arr2:
            while num in arr1:
                arrnew.append(num)
                arr1.remove(num)

        arr1.sort()
        arrnew.extend(arr1)

        return arrnew
```

## Example

**Input:**

```text
arr1 = [2,3,1,3,2,4,6,7,9,2,19]
arr2 = [2,1,4,3,9,6]
```

**Process:**

```text
arr2 order:

2 → [2,2,2]
1 → [1]
4 → [4]
3 → [3,3]
9 → [9]
6 → [6]
```

Remaining elements:

```text
[7,19]
```

Sort remaining elements:

```text
[7,19]
```

Final array:

```text
[2,2,2,1,4,3,3,9,6,7,19]
```

**Output:**

```text
[2,2,2,1,4,3,3,9,6,7,19]
```

## Important Point

Do **not** use `set()` because duplicate values are important.

For example:

```text
arr1 = [2,2,2]
```

The output must contain all three `2`s.

## Complexity

- **Time Complexity:** `O(n²)` because `in` and `remove()` on a list can take `O(n)`.
- **Space Complexity:** `O(n)` for the result array.