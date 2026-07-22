# 1672. Richest Customer Wealth

**Problem Link:** https://leetcode.com/problems/richest-customer-wealth/

## Problem
You are given an `m x n` integer matrix `accounts` where:
- `accounts[i]` represents the wealth of the `i`th customer.
- Each row contains the money a customer has in different bank accounts.

Return the **maximum wealth** among all customers.

## Approach
- Initialize `maximum` as `0`.
- Traverse each customer (row).
- Calculate the total wealth (`summ`) by adding all account balances of that customer.
- Update `maximum` if the current customer's wealth is greater.
- Return `maximum`.

## Solution

```python
class Solution:
    def maximumWealth(self, accounts: List[List[int]]) -> int:
        maximum = 0

        for acc in range(len(accounts)):
            summ = 0

            for j in range(len(accounts[acc])):
                summ += accounts[acc][j]

                if summ > maximum:
                    maximum = summ

        return maximum
```

## Example

**Input:**

```text
accounts = [[1,2,3],[3,2,1]]
```

**Process:**

```text
Customer 1:
1 + 2 + 3 = 6
Maximum = 6

Customer 2:
3 + 2 + 1 = 6
Maximum = 6
```

**Output:**

```text
6
```

## Complexity
- **Time Complexity:** `O(m × n)`
- **Space Complexity:** `O(1)`