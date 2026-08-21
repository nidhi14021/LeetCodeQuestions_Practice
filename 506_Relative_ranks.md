# 506. Relative Ranks

**Problem Link:** https://leetcode.com/problems/relative-ranks/

## Problem

You are given an integer array `score` where `score[i]` represents the score of the `ith` athlete.

All scores are unique.

The athletes are ranked based on their scores:

- Highest score → **Gold Medal**
- Second highest score → **Silver Medal**
- Third highest score → **Bronze Medal**
- Remaining athletes → Their rank number as a string

Return the rank of each athlete in their original order.

## Approach

- Sort the scores in descending order.
- Traverse the original `score` array.
- Find the position of each score in the sorted array.
- Based on its position:
  - `0` → `"Gold Medal"`
  - `1` → `"Silver Medal"`
  - `2` → `"Bronze Medal"`
  - Otherwise → `rank + 1`
- Store the result in `ans`.

## Solution

```python
class Solution:
    def findRelativeRanks(self, score: List[int]) -> List[str]:
        sorted_score = sorted(score, reverse=True)
        ans = []

        for num in score:
            rank = sorted_score.index(num)

            if rank == 0:
                ans.append("Gold Medal")
            elif rank == 1:
                ans.append("Silver Medal")
            elif rank == 2:
                ans.append("Bronze Medal")
            else:
                ans.append(str(rank + 1))

        return ans
```

## Example 1

**Input:**

```text
score = [5,4,3,2,1]
```

**Sorted scores:**

```text
[5,4,3,2,1]
```

**Ranks:**

```text
5 → Gold Medal
4 → Silver Medal
3 → Bronze Medal
2 → 4
1 → 5
```

**Output:**

```text
["Gold Medal","Silver Medal","Bronze Medal","4","5"]
```

---

## Example 2

**Input:**

```text
score = [10,3,8,9,4]
```

**Sorted scores:**

```text
[10,9,8,4,3]
```

**Ranks:**

```text
10 → Gold Medal
3  → 5
8  → Bronze Medal
9  → Silver Medal
4  → 4
```

**Output:**

```text
["Gold Medal","5","Bronze Medal","Silver Medal","4"]
```

## Complexity

- **Time Complexity:** `O(n²)` because `index()` searches through the sorted list for every score.
- **Space Complexity:** `O(n)` for the sorted array and result array.