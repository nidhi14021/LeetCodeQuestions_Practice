# 495. Teemo Attacking

**Problem Link:** https://leetcode.com/problems/teemo-attacking/

## Problem

Our hero Teemo attacks Ashe at times given in `timeSeries`.

Each attack poisons Ashe for `duration` seconds.

If another attack happens before the poison ends, the poison duration is reset.

Return the total time Ashe is poisoned.

## Approach

- Initially, the total poisoned time is `0`.
- Traverse each attack time.
- Find the gap between the current attack and the next attack.
- If the gap is smaller than `duration`, only add the gap.
- Otherwise, add the full `duration`.
- After the loop, add the duration of the last attack.

## Solution

```python
class Solution:
    def findPoisonedDuration(self, timeSeries: List[int], duration: int) -> int:
        total = 0

        for i in range(len(timeSeries) - 1):
            gap = timeSeries[i + 1] - timeSeries[i]
            total += min(gap, duration)

        return total + duration
```

## Example 1

**Input:**

```text
timeSeries = [1,4]
duration = 2
```

**Process:**

```text
Attack at 1 → Poison lasts [1,2]

Gap = 4 - 1 = 3

Gap > duration

Add 2

Last attack:
Add 2
```

**Output:**

```text
4
```

---

## Example 2

**Input:**

```text
timeSeries = [1,2]
duration = 2
```

**Process:**

```text
Attack at 1 → Poison [1,2]

Gap = 2 - 1 = 1

Gap < duration

Add 1

Last attack:
Add 2

Total = 3
```

**Output:**

```text
3
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`