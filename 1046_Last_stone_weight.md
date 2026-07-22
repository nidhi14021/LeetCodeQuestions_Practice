# 1046. Last Stone Weight

**Problem Link:** https://leetcode.com/problems/last-stone-weight/

## Problem
You are given an array `stones` where `stones[i]` is the weight of the `i`th stone.

On each turn:
- Choose the two heaviest stones.
- If they are equal, both stones are destroyed.
- If they are not equal, the smaller stone is destroyed, and the larger stone's weight becomes the difference of the two.

Repeat until at most one stone remains.

Return the weight of the last remaining stone. If no stones remain, return `0`.

## Approach
- While there is more than one stone:
  - Sort the array.
  - Remove the two largest stones.
  - If they are different, add their difference back to the array.
- If one stone remains, return its weight.
- Otherwise, return `0`.

## Solution

```python
class Solution:
    def lastStoneWeight(self, stones: List[int]) -> int:

        while len(stones) > 1:
            stones.sort()

            x = stones.pop()
            y = stones.pop()

            if x != y:
                stones.append(x - y)

        if stones:
            return stones[0]

        return 0
```

## Example

**Input:**

```text
stones = [2,7,4,1,8,1]
```

**Process:**

```text
Sort: [1,1,2,4,7,8]
8 - 7 = 1
Stones: [1,1,2,4,1]

Sort: [1,1,1,2,4]
4 - 2 = 2
Stones: [1,1,1,2]

Sort: [1,1,1,2]
2 - 1 = 1
Stones: [1,1,1]

Sort: [1,1,1]
1 and 1 are equal, both destroyed

Remaining stone: [1]
```

**Output:**

```text
1
```

## Complexity
- **Time Complexity:** `O(n² log n)`
- **Space Complexity:** `O(1)`