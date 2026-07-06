# LeetCode 389 - Find the Difference

🔗 **Problem Link:** https://leetcode.com/problems/find-the-difference/

**Language:** Python 3

## Approach
- Traverse string `t`.
- Compare the frequency of each character in `t` and `s` using `count()`.
- Return the character whose frequency differs.

**Time Complexity:** `O(n²)`  
**Space Complexity:** `O(1)`

## Solution

```python
class Solution:
    def findTheDifference(self, s: str, t: str) -> str:
        for i in range(len(t)):
            if t.count(t[i]) != s.count(t[i]):
                return t[i]
```