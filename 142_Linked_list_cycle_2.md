# 142. Linked List Cycle II

**Problem Link:** https://leetcode.com/problems/linked-list-cycle-ii/

## Problem
Given the `head` of a linked list, return the node where the cycle begins. If there is no cycle, return `None`.

## Approach (Using HashSet)
- Create an empty set to store visited nodes.
- Traverse the linked list using a pointer `temp`.
- If the current node is already present in the set, return that node because it is the start of the cycle.
- Otherwise, add the current node to the set and move to the next node.
- If the traversal reaches `None`, there is no cycle, so return `None`.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        visited = set()
        temp = head

        while temp:
            if temp in visited:
                return temp

            visited.add(temp)
            temp = temp.next

        return None
```

## Example

**Input:**

```text
3 -> 2 -> 0 -> -4
     ^        |
     |________|
```

**Output:**

```text
Node with value 2
```

**Explanation:**
- Traverse the linked list and store each visited node in a set.
- When node `2` is encountered again, it is already present in the set.
- Therefore, node `2` is the starting node of the cycle.

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`