# 905. Sort Array By Parity

**Problem Link:** https://leetcode.com/problems/sort-array-by-parity/

## Problem
Given an integer array `nums`, move all the even integers to the beginning of the array, followed by all the odd integers.

Return any array that satisfies this condition.

## Approach
- Create two separate lists:
  - `even` to store even numbers.
  - `odd` to store odd numbers.
- Traverse the array.
- If a number is even, add it to the `even` list.
- Otherwise, add it to the `odd` list.
- Return the concatenation of `even` and `odd`.

## Solution

```python
class Solution:
    def sortArrayByParity(self, nums: List[int]) -> List[int]:
        even = []
        odd = []

        for num in nums:
            if num % 2 == 0:
                even.append(num)
            else:
                odd.append(num)

        return even + odd
```

## Example

**Input:**

```text
nums = [3,1,2,4]
```

**Process:**

```text
Even: []

3 -> Odd  = [3]
1 -> Odd  = [3,1]
2 -> Even = [2]
4 -> Even = [2,4]
```

**Output:**

```text
[2,4,3,1]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`