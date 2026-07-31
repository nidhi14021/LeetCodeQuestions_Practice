# 66. Plus One

**Problem Link:** https://leetcode.com/problems/plus-one/

## Problem
You are given a large integer represented as an integer array `digits`, where each element is a digit of the integer.

Increment the integer by one and return the resulting array of digits.

## Approach
- Convert the array of digits into an integer.
- Add `1` to the integer.
- Extract each digit of the new number using modulo (`% 10`).
- Reverse the extracted digits to get the correct order.
- Return the resulting array.

## Solution

```python
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        num = 0

        for i in range(len(digits)):
            num = num * 10 + digits[i]

        num2 = num + 1
        arr = []

        while num2 > 0:
            dig = num2 % 10
            num2 = num2 // 10
            arr.append(dig)

        return arr[::-1]
```

## Example 1

**Input:**

```text
digits = [1,2,3]
```

**Process:**

```text
Number = 123

123 + 1 = 124

Digits = [1,2,4]
```

**Output:**

```text
[1,2,4]
```

---

## Example 2

**Input:**

```text
digits = [4,3,2,1]
```

**Process:**

```text
Number = 4321

4321 + 1 = 4322

Digits = [4,3,2,2]
```

**Output:**

```text
[4,3,2,2]
```

---

## Example 3

**Input:**

```text
digits = [9]
```

**Process:**

```text
Number = 9

9 + 1 = 10

Digits = [1,0]
```

**Output:**

```text
[1,0]
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`