# 747. Largest Number At Least Twice of Others

**Problem Link:** https://leetcode.com/problems/largest-number-at-least-twice-of-others/

## Problem

Given an integer array `nums`, return the **index of the largest integer** if it is **at least twice as large as every other number** in the array.

Otherwise, return `-1`.

## Approach

- Find the maximum element in the array.
- Traverse the array.
- Skip the maximum element itself.
- Check if any other element is **more than half** of the maximum (i.e., `2 * nums[i] > max_num`).
- If such an element exists, return `-1`.
- Otherwise, return the index of the maximum element.

## Solution

```python
class Solution:
    def dominantIndex(self, nums: List[int]) -> int:
        max_num = max(nums)

        for i in range(len(nums)):
            if nums[i] != max_num and 2 * nums[i] > max_num:
                return -1

        return nums.index(max_num)
```

## Example 1

**Input:**

```text
nums = [3,6,1,0]
```

**Process:**

```text
Maximum = 6

3 × 2 = 6 ✓
1 × 2 = 2 ✓
0 × 2 = 0 ✓

6 is at least twice every other number.
```

**Output:**

```text
1
```

---

## Example 2

**Input:**

```text
nums = [1,2,3,4]
```

**Process:**

```text
Maximum = 4

1 × 2 = 2 ✓
2 × 2 = 4 ✓
3 × 2 = 6 > 4 ❌

Condition fails.
```

**Output:**

```text
-1
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`