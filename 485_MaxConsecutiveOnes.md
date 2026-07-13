# 485. Max Consecutive Ones

🔗 **Problem Link:** https://leetcode.com/problems/max-consecutive-ones/

## Problem Statement

Given a binary array `nums`, return the maximum number of consecutive `1`s in the array.

### Example

**Input**
```text
nums = [1,1,0,1,1,1]
```

**Output**
```text
3
```

**Explanation**

The first two `1`s form a consecutive sequence of length `2`, while the last three `1`s form a consecutive sequence of length `3`. Hence, the answer is `3`.

---

## Approach

- Initialize two variables:
  - `count` to keep track of the current consecutive `1`s.
  - `max_count` to store the maximum consecutive `1`s found.
- Traverse the array:
  - If the current element is `1`, increment `count` and update `max_count`.
  - If the current element is `0`, reset `count` to `0`.
- Return `max_count`.

---

## Python Solution

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        count = 0
        max_count = 0

        for num in nums:
            if num == 1:
                count += 1
                max_count = max(max_count, count)
            else:
                count = 0

        return max_count
```

---

## Complexity Analysis

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

---

## Topics

- Array
- Counting
- Greedy