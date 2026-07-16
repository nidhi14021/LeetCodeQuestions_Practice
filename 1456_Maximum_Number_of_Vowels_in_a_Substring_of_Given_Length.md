# 1456. Maximum Number of Vowels in a Substring of Given Length

**Problem Link:** https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/

## Problem
Given a string `s` and an integer `k`, return the maximum number of vowel letters in any substring of `s` with length `k`.

## Approach
- Use a **fixed-size sliding window** of length `k`.
- Count the vowels in the first window.
- Slide the window one character at a time:
  - Add the new character if it is a vowel.
  - Remove the character leaving the window if it is a vowel.
- Keep track of the maximum number of vowels found in any window.

## Solution

```python
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        vowels = "aeiou"
        count = 0

        for i in range(k):
            if s[i] in vowels:
                count += 1
        ans = count

        for i in range(k, len(s)):
            if s[i] in vowels:
                count += 1

            if s[i - k] in vowels:
                count -= 1

            ans = max(ans, count)

        return ans
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`