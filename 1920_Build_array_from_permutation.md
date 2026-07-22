# 1920. Build Array from Permutation

**Problem Link:** https://leetcode.com/problems/build-array-from-permutation/

## Problem
Given a zero-based permutation `nums` (0-indexed), build an array `ans` of the same length where:

```text
ans[i] = nums[nums[i]]
```

Return the array `ans`.

## Approach
- Create an empty array `arr`.
- Traverse the array `nums`.
- For each index `i`, find `nums[nums[i]]`.
- Append the value to `arr`.
- Return the final array.

## Solution

```python
class Solution:
    def buildArray(self, nums: List[int]) -> List[int]:
        arr = []

        for i in range(len(nums)):
            arr.append(nums[nums[i]])

        return arr
```

## Example

**Input:**

```text
nums = [0,2,1,5,3,4]
```

**Process:**

```text
i = 0 → nums[nums[0]] = nums[0] = 0
arr = [0]

i = 1 → nums[nums[1]] = nums[2] = 1
arr = [0,1]

i = 2 → nums[nums[2]] = nums[1] = 2
arr = [0,1,2]

i = 3 → nums[nums[3]] = nums[5] = 4
arr = [0,1,2,4]

i = 4 → nums[nums[4]] = nums[3] = 5
arr = [0,1,2,4,5]

i = 5 → nums[nums[5]] = nums[4] = 3
arr = [0,1,2,4,5,3]
```

**Output:**

```text
[0,1,2,4,5,3]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`