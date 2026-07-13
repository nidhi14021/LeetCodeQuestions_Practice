# 1089. Duplicate Zeros

**Problem Link:** https://leetcode.com/problems/duplicate-zeros/

## Approach
- Traverse the array using an index `i`.
- Whenever a `0` is found:
  - Insert another `0` immediately after it using `insert()`.
  - Remove the last element using `pop()` to maintain the original array size.
  - Increment `i` by 1 to skip the newly inserted zero.
- Continue until the end of the array.

## Python Solution

```python
class Solution:
    def duplicateZeros(self, arr: List[int]) -> None:
        i = 0

        while i < len(arr) - 1:
            if arr[i] == 0:
                arr.insert(i + 1, 0)
                arr.pop()
                i += 1
            i += 1
```

## Example

**Input:**
```text
arr = [1,0,2,3,0,4,5,0]
```

**Output:**
```text
[1,0,0,2,3,0,0,4]
```

## Time Complexity
- **O(n²)**

## Space Complexity
- **O(1)** (ignoring the temporary shifts performed by `insert()`).