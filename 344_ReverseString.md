# 344. Reverse String

**Problem Link:** https://leetcode.com/problems/reverse-string/

## Approach
- Use two pointers: `left` at the beginning and `right` at the end.
- Swap the characters at both pointers.
- Move `left` forward and `right` backward until they meet.

## Python Solution

```python
class Solution:
    def reverseString(self, s: List[str]) -> None:
        left = 0
        right = len(s) - 1

        while left < right:
            s[left], s[right] = s[right], s[left]

            left += 1
            right -= 1
```

## Time Complexity
- **O(n)**

## Space Complexity
- **O(1)**