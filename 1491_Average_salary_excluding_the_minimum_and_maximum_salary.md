# 1491. Average Salary Excluding the Minimum and Maximum Salary

**Problem Link:** https://leetcode.com/problems/average-salary-excluding-the-minimum-and-maximum-salary/

## Problem

Given an array `salary` where `salary[i]` represents the salary of an employee, return the **average salary excluding the minimum and maximum salary**.

The answer should be returned as a floating-point number.

## Approach

- Find the minimum salary.
- Find the maximum salary.
- Remove both from the array.
- Calculate the sum of the remaining salaries.
- Divide the sum by the number of remaining salaries.
- Return the average.

## Solution

```python
class Solution:
    def average(self, salary: List[int]) -> float:
        min_sal = min(salary)
        max_sal = max(salary)

        salary.remove(min_sal)
        salary.remove(max_sal)

        summ = 0

        for i in range(len(salary)):
            summ += salary[i]

        avg = summ / len(salary)

        return avg
```

## Example 1

**Input:**

```text
salary = [4000,3000,1000,2000]
```

**Process:**

```text
Minimum = 1000
Maximum = 4000

Remove both:

[3000,2000]

Sum = 3000 + 2000
    = 5000

Average = 5000 / 2
        = 2500
```

**Output:**

```text
2500.0
```

---

## Example 2

**Input:**

```text
salary = [1000,2000,3000]
```

**Process:**

```text
Minimum = 1000
Maximum = 3000

Remaining:

[2000]

Average = 2000 / 1
        = 2000
```

**Output:**

```text
2000.0
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`