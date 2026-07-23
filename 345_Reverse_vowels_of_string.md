# 345. Reverse Vowels of a String

**Problem Link:** https://leetcode.com/problems/reverse-vowels-of-a-string/

## Problem
Given a string `s`, reverse only all the vowels in the string and return the resulting string.

The vowels are:

```text
a, e, i, o, u, A, E, I, O, U
```

## Approach (Two Pointers)
- Convert the string into a list since strings are immutable in Python.
- Create a string containing all uppercase and lowercase vowels.
- Initialize two pointers:
  - `left` at the beginning.
  - `right` at the end.
- Move `left` until it points to a vowel.
- Move `right` until it points to a vowel.
- Swap the two vowels.
- Continue until `left` is no longer less than `right`.
- Convert the list back into a string and return it.

## Solution

```python
class Solution:
    def reverseVowels(self, s: str) -> str:
        s = list(s)
        vowel = "aeiouAEIOU"

        left = 0
        right = len(s) - 1

        while left < right:
            while left < right and s[left] not in vowel:
                left += 1

            while left < right and s[right] not in vowel:
                right -= 1

            s[left], s[right] = s[right], s[left]

            left += 1
            right -= 1

        return "".join(s)
```

## Example

**Input:**

```text
s = "hello"
```

**Process:**

```text
Initial:
h e l l o
  ^     ^

Swap:
h o l l e
```

**Output:**

```text
"holle"
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`