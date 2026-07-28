# 796. Rotate String

**Problem Link:** https://leetcode.com/problems/rotate-string/

## Problem
Given two strings `s` and `goal`, return `true` if and only if `s` can become `goal` after some number of left shifts.

A left shift moves the leftmost character of the string to the end.

For example:

```text
"abcde" → "bcdea"
```

## Approach
- If the lengths of `s` and `goal` are different, return `False`.
- Perform at most `len(s)` left shifts.
- After each shift, check if `s` is equal to `goal`.
- If they become equal, return `True`.
- If no match is found after all shifts, return `False`.

## Solution

```python
class Solution:
    def rotateString(self, s: str, goal: str) -> bool:
        if len(s) != len(goal):
            return False

        for i in range(len(s)):
            if s == goal:
                return True

            s = s[1:] + s[0]

        return False
```

## Example 1

**Input:**

```text
s = "abcde"
goal = "cdeab"
```

**Process:**

```text
Original: abcde

Shift 1 → bcdea
Shift 2 → cdeab ✓
```

**Output:**

```text
True
```

---

## Example 2

**Input:**

```text
s = "abcde"
goal = "abced"
```

**Process:**

```text
Original: abcde

Shift 1 → bcdea
Shift 2 → cdeab
Shift 3 → deabc
Shift 4 → eabcd
Shift 5 → abcde

No match found.
```

**Output:**

```text
False
```

## Complexity
- **Time Complexity:** `O(n²)` (up to `n` shifts, each creating a new string of length `n`)
- **Space Complexity:** `O(n)`