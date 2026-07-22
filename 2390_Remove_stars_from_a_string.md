# 2390. Removing Stars From a String

**Problem Link:** https://leetcode.com/problems/removing-stars-from-a-string/

## Problem
You are given a string `s` containing lowercase English letters and stars (`*`).

Each `*` removes the closest non-star character to its left as well as the `*` itself.

Return the final string after all stars have been removed.

## Approach (Stack)
- Create an empty stack.
- Traverse each character in the string.
- If the character is `*`, remove the last character from the stack using `pop()`.
- Otherwise, push the character onto the stack.
- Finally, join all characters in the stack to form the answer.

## Solution

```python
class Solution:
    def removeStars(self, s: str) -> str:
        stack = []

        for ch in s:
            if ch == "*":
                stack.pop()
            else:
                stack.append(ch)

        ans = "".join(stack)

        return ans
```

## Example

**Input:**

```text
s = "leet**cod*e"
```

**Process:**

```text
Stack: []

l  -> [l]
e  -> [l, e]
e  -> [l, e, e]
t  -> [l, e, e, t]
*  -> [l, e, e]
*  -> [l, e]
c  -> [l, e, c]
o  -> [l, e, c, o]
d  -> [l, e, c, o, d]
*  -> [l, e, c, o]
e  -> [l, e, c, o, e]
```

**Output:**

```text
"lecoe"
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`