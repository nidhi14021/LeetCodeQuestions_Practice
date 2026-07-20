# 141. Linked List Cycle

**Problem Link:** https://leetcode.com/problems/linked-list-cycle/

## Problem
Given `head`, the head of a linked list, determine if the linked list has a cycle in it.

Return `true` if there is a cycle in the linked list. Otherwise, return `false`.

## Approach (Slow & Fast Pointer)
- Initialize two pointers:
  - `slow` moves one node at a time.
  - `fast` moves two nodes at a time.
- Traverse the linked list while `fast` and `fast.next` are not `None`.
- If `slow` and `fast` meet at any point, a cycle exists.
- If `fast` reaches the end of the list, there is no cycle.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:

        slow = head
        fast = head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

            if slow == fast:
                return True

        return False
```

## Example

**Input:**

```text
3 -> 2 -> 0 -> -4
     ^         |
     |_________|
```

**Output:**

```text
True
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`