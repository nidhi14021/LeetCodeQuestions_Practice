# 1732. Find the Highest Altitude

**Problem Link:** https://leetcode.com/problems/find-the-highest-altitude/

## Problem
There is a biker going on a road trip. The trip consists of `n + 1` points at different altitudes.

You are given an integer array `gain` where `gain[i]` is the net gain (or loss) in altitude between points `i` and `i + 1`.

The biker starts at altitude `0`.

Return the **highest altitude** reached during the trip.

## Approach
- Initialize `summ` as `0` because the biker starts at altitude `0`.
- Create a list `arr` and add the starting altitude (`0`).
- Traverse the `gain` array.
- Continuously add each gain/loss to `summ`.
- Store each new altitude in `arr`.
- Return the maximum value from `arr`.

## Solution

```python
class Solution:
    def largestAltitude(self, gain: List[int]) -> int:
        summ = 0
        arr = []
        arr.append(summ)

        for i in range(len(gain)):
            summ += gain[i]
            arr.append(summ)

        return max(arr)
```

## Example

**Input:**

```text
gain = [-5,1,5,0,-7]
```

**Process:**

```text
Start = 0

0 + (-5) = -5
-5 + 1 = -4
-4 + 5 = 1
1 + 0 = 1
1 + (-7) = -6

Altitudes = [0, -5, -4, 1, 1, -6]
```

**Output:**

```text
1
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`