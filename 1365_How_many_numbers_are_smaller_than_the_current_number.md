# 1365. How Many Numbers Are Smaller Than the Current Number

**Problem Link:** https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/

## Problem
Given the array `nums`, for each `nums[i]`, find out how many numbers in the array are smaller than it. Return the answer in an array.

## Approach
- Traverse each element of the array.
- For every element, compare it with every other element.
- Count how many elements are smaller than the current element.
- Store the count in the answer array.
- Return the final array.

## Solution

```python
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:

        arr = []

        for i in range(len(nums)):
            count = 0

            for j in range(len(nums)):
                if nums[i] > nums[j]:
                    count += 1

            arr.append(count)

        return arr
```

## Example

**Input:**

```text
nums = [8,1,2,2,3]
```

**Output:**

```text
[4,0,1,1,3]
```

**Explanation:**

- 8 has 4 smaller numbers (1, 2, 2, 3)
- 1 has 0 smaller numbers
- 2 has 1 smaller number (1)
- 2 has 1 smaller number (1)
- 3 has 3 smaller numbers (1, 2, 2)

## Complexity
- **Time Complexity:** `O(n²)`
- **Space Complexity:** `O(n)` (for the output array)