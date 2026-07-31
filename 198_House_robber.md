# 198. House Robber

**Problem Link:** https://leetcode.com/problems/house-robber/

## Problem
You are given an integer array `nums` where each element represents the amount of money in a house.

You cannot rob two adjacent houses because they have connected security systems.

Return the maximum amount of money you can rob without alerting the police.

## Approach (Space Optimized Dynamic Programming)

- Maintain two variables:
  - `prev1` → Maximum money that can be robbed up to the previous house.
  - `prev2` → Maximum money that can be robbed up to the house before the previous one.
- For each house:
  - **Skip the current house:** `prev1`
  - **Rob the current house:** `prev2 + num`
- Take the maximum of these two choices.
- Update `prev1` and `prev2` after processing each house.

## Solution

```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        prev2 = 0
        prev1 = 0

        for num in nums:
            prev1, prev2 = max(prev1, prev2 + num), prev1

        return prev1
```

## Example 1

**Input:**

```text
nums = [1,2,3,1]
```

**Process:**

```text
House 1: max(0, 0+1) = 1
House 2: max(1, 0+2) = 2
House 3: max(2, 1+3) = 4
House 4: max(4, 2+1) = 4
```

**Output:**

```text
4
```

---

## Example 2

**Input:**

```text
nums = [2,7,9,3,1]
```

**Process:**

```text
House 1: max(0, 0+2) = 2
House 2: max(2, 0+7) = 7
House 3: max(7, 2+9) = 11
House 4: max(11, 7+3) = 11
House 5: max(11, 11+1) = 12
```

**Output:**

```text
12
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`