# 739. Daily Temperatures

**Problem Link:** https://leetcode.com/problems/daily-temperatures/

## Problem
Given an array `temperatures`, return an array `answer` such that `answer[i]` is the number of days you have to wait after the `iᵗʰ` day to get a warmer temperature.

If there is no future day with a warmer temperature, return `0` for that day.

## Approach (Monotonic Stack)
- Create an answer array initialized with `0`.
- Use a stack to store the **indices** of temperatures.
- Traverse the array from left to right.
- While the current temperature is greater than the temperature at the index on the top of the stack:
  - Pop the index.
  - Calculate the number of days waited.
  - Store it in the answer array.
- Push the current index onto the stack.
- The remaining indices in the stack have no warmer future day, so their values remain `0`.

## Solution

```python
class Solution:
    def dailyTemperatures(self, temperatures: List[int]) -> List[int]:
        n = len(temperatures)
        ans = [0] * n
        stack = []

        for i in range(n):
            while stack and temperatures[i] > temperatures[stack[-1]]:
                index = stack.pop()
                ans[index] = i - index

            stack.append(i)

        return ans
```

## Example 1

**Input:**

```text
temperatures = [73,74,75,71,69,72,76,73]
```

**Process:**

```text
Day 0 (73) → Warmer day is 74 after 1 day.
Day 1 (74) → Warmer day is 75 after 1 day.
Day 2 (75) → Warmer day is 76 after 4 days.
Day 3 (71) → Warmer day is 72 after 2 days.
Day 4 (69) → Warmer day is 72 after 1 day.
Day 5 (72) → Warmer day is 76 after 1 day.
Day 6 (76) → No warmer day.
Day 7 (73) → No warmer day.
```

**Output:**

```text
[1,1,4,2,1,1,0,0]
```

---

## Example 2

**Input:**

```text
temperatures = [30,40,50,60]
```

**Process:**

```text
30 → 40 after 1 day
40 → 50 after 1 day
50 → 60 after 1 day
60 → No warmer day
```

**Output:**

```text
[1,1,1,0]
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`