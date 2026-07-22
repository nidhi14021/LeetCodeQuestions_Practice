# 1480. Running Sum of 1d Array

**Problem Link:** https://leetcode.com/problems/running-sum-of-1d-array/

## Problem
Given an array `nums`, return the running sum of `nums`.

The running sum of an array is defined as:

```text
runningSum[i] = sum(nums[0] ... nums[i])
```

## Approach
- Traverse the array starting from index `1`.
- Add the previous running sum to the current element.
- Store the updated value back into the same array.
- Return the modified array.

## Solution

```python
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        for i in range(1, len(nums)):
            nums[i] += nums[i - 1]

        return nums
```

## Example

**Input:**

```text
nums = [1, 2, 3, 4]
```

**Process:**

```text
Initial Array: [1, 2, 3, 4]

i = 1 -> [1, 3, 3, 4]
i = 2 -> [1, 3, 6, 4]
i = 3 -> [1, 3, 6, 10]
```

**Output:**

```text
[1, 3, 6, 10]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`