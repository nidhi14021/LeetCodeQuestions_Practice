# 455. Assign Cookies

**Problem Link:** https://leetcode.com/problems/assign-cookies/

## Problem

You are given two integer arrays:

- `g` → The greed factor of each child.
- `s` → The size of each cookie.

Each child can receive at most one cookie. A child is satisfied if the cookie size is **greater than or equal to** the child's greed factor.

Return the maximum number of satisfied children.

## Approach (Greedy)

- Sort both `g` and `s`.
- Start with the smallest cookie.
- For each child:
  - Check whether the current cookie can satisfy the child.
  - If yes, increase `count` and move to the next cookie.
  - If the cookie is too small, move to the next cookie.
- Return the total number of satisfied children.

## Solution

```python
class Solution:
    def findContentChildren(self, g: List[int], s: List[int]) -> int:
        g.sort()
        s.sort()

        count = 0
        j = 0

        for i in range(len(g)):
            while j < len(s):
                if s[j] >= g[i]:
                    count += 1
                    j += 1
                    break
                j += 1

        return count
```

## Example 1

**Input:**

```text
g = [1,2,3]
s = [1,1]
```

**Process:**

```text
Child with greed 1 → Cookie 1 ✓
Child with greed 2 → Cookie 1 ✗
No more suitable cookies
```

**Output:**

```text
1
```

---

## Example 2

**Input:**

```text
g = [1,2]
s = [1,2,3]
```

**Process:**

```text
Child with greed 1 → Cookie 1 ✓
Child with greed 2 → Cookie 2 ✓
```

**Output:**

```text
2
```

## Complexity

- **Time Complexity:** `O(n log n + m log m)` due to sorting.
- **Space Complexity:** `O(1)` excluding sorting space.