# Move Zeroes (LeetCode 283)

**Problem Link:** https://leetcode.com/problems/move-zeroes/

## Problem Statement

Given an integer array `nums`, move all `0`s to the end of it while maintaining the relative order of the non-zero elements.

**Note:** You must do this in-place without making a copy of the array.

### Example

**Input:**
```
nums = [0,1,0,3,12]
```

**Output:**
```
[1,3,12,0,0]
```

---

## Language

**Python 3**

---

## Approach (Two Pointers)

- Use a pointer `j` to keep track of the position where the next non-zero element should be placed.
- Traverse the array using pointer `i`.
- Whenever a non-zero element is found, swap it with the element at index `j`.
- Increment `j` after every successful swap.
- By the end of the traversal, all non-zero elements remain in their original order, and all zeros are automatically moved to the end.

---

## Time Complexity

- **Time:** `O(n)`
- **Space:** `O(1)`

---

## Python Solution

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        j = 0

        for i in range(len(nums)):
            if nums[i] != 0:
                nums[j], nums[i] = nums[i], nums[j]
                j += 1
```