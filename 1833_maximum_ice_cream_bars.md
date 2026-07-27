# 1833. Maximum Ice Cream Bars

**Problem Link:** https://leetcode.com/problems/maximum-ice-cream-bars/

## Problem
You are given an array `costs` where `costs[i]` is the cost of the `iᵗʰ` ice cream bar, and an integer `coins` representing the number of coins you have.

Return the **maximum number of ice cream bars** you can buy.

## Approach (Greedy)
- Sort the `costs` array in ascending order.
- Start buying the cheapest ice cream bars first.
- Keep adding the cost of each bar to `summ`.
- If the total cost is less than or equal to `coins`, increase the count.
- If the total exceeds `coins`, stop buying.
- Return the total number of ice cream bars purchased.

## Solution

```python
class Solution:
    def maxIceCream(self, costs: List[int], coins: int) -> int:
        costs.sort()
        count = 0
        summ = 0

        for i in range(len(costs)):
            summ += costs[i]

            if summ <= coins:
                count += 1
            else:
                break

        return count
```

## Example

**Input:**

```text
costs = [1,3,2,4,1]
coins = 7
```

**Process:**

```text
Sorted costs = [1,1,2,3,4]

Buy 1 → Total = 1
Buy 1 → Total = 2
Buy 2 → Total = 4
Buy 3 → Total = 7
Cannot buy 4 (Total would be 11)

Ice cream bars bought = 4
```

**Output:**

```text
4
```

## Complexity
- **Time Complexity:** `O(n log n)` (sorting the array)
- **Space Complexity:** `O(1)` (excluding the space used by the sorting algorithm)