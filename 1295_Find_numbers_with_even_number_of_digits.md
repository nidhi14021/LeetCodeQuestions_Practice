# 1295. Find Numbers with Even Number of Digits

**Problem Link:** https://leetcode.com/problems/find-numbers-with-even-number-of-digits/

## Problem
Given an array `nums` of integers, return how many of them contain an even number of digits.

## Approach
- Traverse each number in the array.
- Count the number of digits using a `while` loop.
- Store each digit count in an array.
- Traverse the digit count array.
- If the digit count is even, increment the answer.
- Return the final count.

## Solution

```python
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        arr = []

        count_new = 0

        for num in nums:
            count = 0
            temp = num

            while temp > 0:
                count += 1
                temp = temp // 10

            arr.append(count)

        for i in range(len(arr)):
            if arr[i] % 2 == 0:
                count_new += 1

        return count_new
```

## Example

**Input:**

```text
nums = [12,345,2,6,7896]
```

**Digit Counts:**

```text
12    -> 2
345   -> 3
2     -> 1
6     -> 1
7896  -> 4
```

**Output:**

```text
2
```

## Complexity
- **Time Complexity:** `O(n × d)` where `d` is the number of digits.
- **Space Complexity:** `O(n)`