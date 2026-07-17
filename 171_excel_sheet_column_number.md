# 171. Excel Sheet Column Number

**Problem Link:** https://leetcode.com/problems/excel-sheet-column-number/

## Problem
Given a string `columnTitle` that represents the column title as it appears in an Excel sheet, return its corresponding column number.

## Approach
- Treat the column title as a **base-26** number.
- Traverse each character in the string.
- Convert the character to its corresponding value:
  - `A -> 1`, `B -> 2`, ..., `Z -> 26`
- Update the answer using:
  - `ans = ans * 26 + value`

## Solution

```python
class Solution:
    def titleToNumber(self, columnTitle: str) -> int:
        ans = 0

        for ch in columnTitle:
            value = ord(ch) - ord('A') + 1
            ans = ans * 26 + value

        return ans
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`