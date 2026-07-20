# 4. Median of Two Sorted Arrays

**Problem Link:** https://leetcode.com/problems/median-of-two-sorted-arrays/

## Problem
Given two sorted arrays `nums1` and `nums2` of sizes `m` and `n`, return the median of the two sorted arrays.

## Approach
- Merge both arrays into a single array.
- Sort the merged array.
- Find the total number of elements.
- If the length is even, return the average of the two middle elements.
- If the length is odd, return the middle element.

## Solution

```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        new = nums1 + nums2

        new.sort()

        n = len(new)

        if n % 2 == 0:
            return (new[n // 2] + new[n // 2 - 1]) / 2
        else:
            return new[n // 2]
```

## Example 1

**Input:**

```text
nums1 = [1,3]
nums2 = [2]
```

**Merged Array:**

```text
[1,2,3]
```

**Output:**

```text
2.0
```

---

## Example 2

**Input:**

```text
nums1 = [1,2]
nums2 = [3,4]
```

**Merged Array:**

```text
[1,2,3,4]
```

**Output:**

```text
2.5
```

## Complexity
- **Time Complexity:** `O((m+n) log(m+n))`
- **Space Complexity:** `O(m+n)`