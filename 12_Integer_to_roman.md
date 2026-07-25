# 12. Integer to Roman

**Problem Link:** https://leetcode.com/problems/integer-to-roman/

## Problem
Given an integer `num`, convert it to its corresponding **Roman numeral**.

Roman numerals are formed by using the following symbols:

| Value | Symbol |
|-------:|:------:|
| 1000 | M |
| 900 | CM |
| 500 | D |
| 400 | CD |
| 100 | C |
| 90 | XC |
| 50 | L |
| 40 | XL |
| 10 | X |
| 9 | IX |
| 5 | V |
| 4 | IV |
| 1 | I |

## Approach (Greedy)
- Store the decimal values and their corresponding Roman symbols in descending order.
- Traverse the values from largest to smallest.
- While the current value is less than or equal to `num`:
  - Append its Roman symbol to the answer.
  - Subtract the value from `num`.
- Continue until `num` becomes `0`.
- Return the final Roman numeral.

## Solution

```python
class Solution:
    def intToRoman(self, num: int) -> str:

        values = [1000,900,500,400,100,90,50,40,10,9,5,4,1]

        roman = ["M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"]

        ans = ""

        for i in range(len(values)):
            while num >= values[i]:
                ans += roman[i]
                num -= values[i]

        return ans
```

## Example 1

**Input:**

```text
num = 3749
```

**Process:**

```text
3749

1000 → M
1000 → M
1000 → M
500  → D
100  → C
100  → C
40   → XL
9    → IX
```

**Output:**

```text
"MMMDCCXLIX"
```

---

## Example 2

**Input:**

```text
num = 58
```

**Process:**

```text
58

50 → L
5  → V
1  → I
1  → I
1  → I
```

**Output:**

```text
"LVIII"
```

## Complexity
- **Time Complexity:** `O(1)` (fixed number of Roman symbols)
- **Space Complexity:** `O(1)`