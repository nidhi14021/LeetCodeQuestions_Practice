# 605. Can Place Flowers

**Problem Link:** https://leetcode.com/problems/can-place-flowers/

## Problem

You have a flowerbed represented by an array of `0`s and `1`s.

- `0` means the plot is empty.
- `1` means the plot already has a flower.
- Flowers cannot be planted in adjacent plots.

Given `flowerbed` and an integer `n`, return `true` if `n` flowers can be planted without violating the rule.

## Approach

- Traverse the flowerbed.
- If the current position is `0`, check its left and right sides.
- If both sides are empty, plant a flower there.
- Decrease `n` by `1`.
- At the end, if `n <= 0`, return `true`.

## Solution

```python
class Solution:
    def canPlaceFlowers(self, flowerbed: List[int], n: int) -> bool:
        for i in range(len(flowerbed)):
            if flowerbed[i] == 0:
                if i == 0 or flowerbed[i - 1] == 0:
                    if i == len(flowerbed) - 1 or flowerbed[i + 1] == 0:
                        flowerbed[i] = 1
                        n -= 1

        return n <= 0
```

## Example 1

**Input:**

```text
flowerbed = [1,0,0,0,1]
n = 1
```

**Process:**

```text
[1,0,0,0,1]

Position 2 is empty.
Left = 0
Right = 0

Plant flower:

[1,0,1,0,1]

n = 0
```

**Output:**

```text
true
```

## Example 2

**Input:**

```text
flowerbed = [1,0,0,0,1]
n = 2
```

Only one flower can be planted.

```text
n = 1
```

**Output:**

```text
false
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`