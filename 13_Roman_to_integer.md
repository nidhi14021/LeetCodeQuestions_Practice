# 13. Roman to Integer

**Problem Link:** https://leetcode.com/problems/roman-to-integer/

## Problem
Given a Roman numeral `s`, convert it to an integer.

Roman numerals are represented by the following symbols:

| Symbol | Value |
|:------:|------:|
| I | 1 |
| V | 5 |
| X | 10 |
| L | 50 |
| C | 100 |
| D | 500 |
| M | 1000 |

### Special Cases (Subtractive Notation)

| Roman | Value |
|:-----:|------:|
| IV | 4 |
| IX | 9 |
| XL | 40 |
| XC | 90 |
| CD | 400 |
| CM | 900 |

## Approach
- Store each Roman symbol and its corresponding integer value in a dictionary.
- Traverse the string from left to right.
- If the current symbol has a smaller value than the next symbol, subtract its value.
- Otherwise, add its value.
- Return the final integer.

## Solution

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        roman = {
            "I": 1,
            "V": 5,
            "X": 10,
            "L": 50,
            "C": 100,
            "D": 500,
            "M": 1000
        }

        ans = 0

        for i in range(len(s)):
            if i < len(s) - 1 and roman[s[i]] < roman[s[i + 1]]:
                ans -= roman[s[i]]
            else:
                ans += roman[s[i]]

        return ans
```

## Example 1

**Input:**

```text
s = "III"
```

**Process:**

```text
I = 1
I = 1
I = 1

1 + 1 + 1 = 3
```

**Output:**

```text
3
```

---

## Example 2

**Input:**

```text
s = "LVIII"
```

**Process:**

```text
L = 50
V = 5
I = 1
I = 1
I = 1

50 + 5 + 1 + 1 + 1 = 58
```

**Output:**

```text
58
```

---

## Example 3

**Input:**

```text
s = "MCMXCIV"
```

**Process:**

```text
M  = +1000
C  = -100   (before M)
M  = +1000
X  = -10    (before C)
C  = +100
I  = -1     (before V)
V  = +5

Total = 1994
```

**Output:**

```text
1994
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`