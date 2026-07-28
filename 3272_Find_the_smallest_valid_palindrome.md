# 3272. Find the Lexicographically Smallest Valid Palindrome

**Problem Link:** https://leetcode.com/problems/find-the-lexicographically-smallest-valid-palindrome/

## Problem
Given a palindrome string `s`, return the **lexicographically smallest palindrome** that can be formed using the same characters.

## Approach
- Count the frequency of each character using `Counter`.
- Traverse the characters in sorted order.
- Add half of each character's frequency to the left half of the palindrome.
- If a character has an odd frequency, use it as the middle character.
- Form the final palindrome as:
  - Left half
  - Middle character (if any)
  - Reverse of the left half

## Solution

```python
from collections import Counter

class Solution:
    def smallestPalindrome(self, s: str) -> str:
        freq = Counter(s)

        left = []
        mid = ""

        for ch in sorted(freq):
            left.append(ch * (freq[ch] // 2))

            if freq[ch] % 2 == 1:
                mid = ch

        left = "".join(left)

        return left + mid + left[::-1]
```

## Example 1

**Input:**

```text
s = "daccad"
```

**Process:**

```text
Frequency:
a → 2
c → 2
d → 2

Left half:
a + c + d = "acd"

Middle:
None

Right half:
"dca"

Result:
"acddca"
```

**Output:**

```text
"acddca"
```

---

## Example 2

**Input:**

```text
s = "babab"
```

**Process:**

```text
Frequency:
a → 2
b → 3

Left half:
a + b = "ab"

Middle:
b

Right half:
"ba"

Result:
"abbba"
```

**Output:**

```text
"abbba"
```

## Complexity
- **Time Complexity:** `O(n + k log k)`  
  - `n` = length of the string
  - `k` = number of distinct characters (sorting the keys)
- **Space Complexity:** `O(n)`