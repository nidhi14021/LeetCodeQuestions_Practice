# 412. Fizz Buzz

**Problem Link:** https://leetcode.com/problems/fizz-buzz/

## Problem
Given an integer `n`, return a string array `answer` (1-indexed) where:

- If `i` is divisible by **3** and **5**, return `"FizzBuzz"`.
- If `i` is divisible by **3**, return `"Fizz"`.
- If `i` is divisible by **5**, return `"Buzz"`.
- Otherwise, return the string representation of `i`.

## Approach
- Create an empty list `arr`.
- Traverse numbers from `1` to `n`.
- Check divisibility:
  - If divisible by both `3` and `5`, append `"FizzBuzz"`.
  - Else if divisible by `5`, append `"Buzz"`.
  - Else if divisible by `3`, append `"Fizz"`.
  - Otherwise, append the number as a string.
- Return the final list.

## Solution

```python
class Solution:
    def fizzBuzz(self, n: int) -> List[str]:
        arr = []

        for i in range(1, n + 1):
            if i % 3 == 0 and i % 5 == 0:
                arr.append("FizzBuzz")
            elif i % 5 == 0:
                arr.append("Buzz")
            elif i % 3 == 0:
                arr.append("Fizz")
            else:
                arr.append(str(i))

        return arr
```

## Example

**Input:**

```text
n = 15
```

**Process:**

```text
1  → "1"
2  → "2"
3  → "Fizz"
4  → "4"
5  → "Buzz"
6  → "Fizz"
7  → "7"
8  → "8"
9  → "Fizz"
10 → "Buzz"
11 → "11"
12 → "Fizz"
13 → "13"
14 → "14"
15 → "FizzBuzz"
```

**Output:**

```text
["1","2","Fizz","4","Buzz","Fizz","7","8","Fizz","Buzz","11","Fizz","13","14","FizzBuzz"]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`