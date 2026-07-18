# 206. Reverse Linked List

**Problem Link:** https://leetcode.com/problems/reverse-linked-list/

## Problem
Given the `head` of a singly linked list, reverse the list and return the new head.

## Approach
- Use three pointers:
  - `temp` to traverse the list.
  - `prev` to store the previous node.
  - `front` to store the next node before changing the link.
- Traverse the linked list:
  - Save the next node in `front`.
  - Reverse the current node's pointer.
  - Move `prev` and `temp` one step forward.
- When traversal is complete, `prev` points to the new head of the reversed list.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        temp = head
        prev = None

        while temp != None:
            front = temp.next
            temp.next = prev
            prev = temp
            temp = front

        return prev
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`