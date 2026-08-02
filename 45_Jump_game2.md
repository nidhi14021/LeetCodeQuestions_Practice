# 45. Jump Game II

**Problem Link:** https://leetcode.com/problems/jump-game-ii/

## Problem
You are given a 0-indexed array `nums`, where each element represents the maximum jump length from that position.

Return the **minimum number of jumps** required to reach the last index.

It is guaranteed that you can always reach the last index.

## Approach (Greedy)

- Use three variables:
  - `jumps` → Number of jumps taken.
  - `end` → End of the current jump range.
  - `farthest` → Farthest index reachable so far.
- Traverse the array (except the last element).
- Update the farthest reachable index.
- Whenever you reach the end of the current range (`i == end`):
  - Increment the jump count.
  - Update the current range to the farthest reachable index.
- Return the total number of jumps.

## Solution

```python
class Solution:
    def jump(self, nums: List[int]) -> int:
        jumps = 0
        end = 0
        farthest = 0

        for i in range(len(nums) - 1):
            farthest = max(farthest, i + nums[i])

            if i == end:
                jumps += 1
                end = farthest

        return jumps
```

## Example 1

**Input:**

```text
nums = [2,3,1,1,4]
```

**Process:**

```text
Initially:
jumps = 0
end = 0
farthest = 0

i = 0
farthest = max(0, 0 + 2) = 2
i == end
jumps = 1
end = 2

i = 1
farthest = max(2, 1 + 3) = 4

i = 2
farthest = max(4, 2 + 1) = 4
i == end
jumps = 2
end = 4
```

**Output:**

```text
2
```

---

## Example 2

**Input:**

```text
nums = [2,3,0,1,4]
```

**Process:**

```text
Initially:
jumps = 0
end = 0
farthest = 0

i = 0
farthest = 2
jumps = 1
end = 2

i = 1
farthest = 4

i = 2
farthest = 4
jumps = 2
end = 4
```

**Output:**

```text
2
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`