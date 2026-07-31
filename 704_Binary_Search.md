# 704. Binary Search

**Problem Link:** https://leetcode.com/problems/binary-search/

## Problem
Given a sorted array of integers `nums` and an integer `target`, return the index of `target` if it exists in the array. Otherwise, return `-1`.

You must write an algorithm with **O(log n)** runtime complexity.

## Approach
- Initialize two pointers:
  - `low` at the beginning of the array.
  - `high` at the end of the array.
- While `low <= high`:
  - Find the middle index `mid`.
  - If `nums[mid]` equals the target, return `mid`.
  - If `nums[mid]` is less than the target, search the right half.
  - Otherwise, search the left half.
- If the target is not found, return `-1`.

## Solution

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        low = 0
        high = len(nums) - 1

        while low <= high:
            mid = (low + high) // 2

            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                low = mid + 1
            else:
                high = mid - 1

        return -1
```

## Example 1

**Input:**

```text
nums = [-1,0,3,5,9,12]
target = 9
```

**Process:**

```text
low = 0, high = 5

mid = 2 → nums[2] = 3
3 < 9 → Search right half

low = 3, high = 5

mid = 4 → nums[4] = 9
Target found at index 4
```

**Output:**

```text
4
```

---

## Example 2

**Input:**

```text
nums = [-1,0,3,5,9,12]
target = 2
```

**Process:**

```text
low = 0, high = 5

mid = 2 → nums[2] = 3
3 > 2 → Search left half

low = 0, high = 1

mid = 0 → nums[0] = -1
-1 < 2 → Search right half

low = 1, high = 1

mid = 1 → nums[1] = 0
0 < 2 → Search right half

Target not found
```

**Output:**

```text
-1
```

## Complexity

- **Time Complexity:** `O(log n)`
- **Space Complexity:** `O(1)`