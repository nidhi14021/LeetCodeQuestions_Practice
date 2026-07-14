# 217. Contains Duplicate

**Problem Link:** https://leetcode.com/problems/contains-duplicate/

## Approach
- Sort the array so that duplicate elements become adjacent.
- Use two pointers:
  - `left` points to the current element.
  - `right` points to the next element.
- Compare `nums[left]` and `nums[right]`.
  - If they are equal, a duplicate exists, so return `True`.
  - Otherwise, move both pointers one step ahead.
- If no duplicates are found, return `False`.

## Python Solution

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        nums.sort()

        left = 0
        right = 1

        while right < len(nums):
            if nums[left] == nums[right]:
                return True
            left += 1
            right += 1

        return False
```

## Example

**Input:**
```text
nums = [1,2,3,1]
```

**Sorted Array:**
```text
[1,1,2,3]
```

**Comparison:**
```text
left = 0, right = 1
1 == 1 → True
```

**Output:**
```text
True
```
