# 1047. Remove All Adjacent Duplicates In String

**Problem Link:** https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/

## Problem
Given a string `s`, repeatedly remove adjacent duplicate characters until no more adjacent duplicates remain. Return the final string.

## Approach
- Use a **stack** to keep track of characters.
- Traverse each character in the string.
- If the current character is the same as the top of the stack, remove the top element.
- Otherwise, push the current character onto the stack.
- Join the remaining characters in the stack to form the final string.

## Solution

```python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        stack = []

        for ch in s:
            if stack and stack[-1] == ch:
                stack.pop()
            else:
                stack.append(ch)

        result = "".join(stack)

        return result
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`