# 203. Remove Linked List Elements

**Problem Link:** https://leetcode.com/problems/remove-linked-list-elements/

## Problem
Given the `head` of a linked list and an integer `val`, remove all the nodes of the linked list that have `Node.val == val`, and return the new head.

## Approach
- First, remove all matching nodes from the beginning of the linked list.
- Traverse the remaining list using a pointer `temp`.
- Keep another pointer `front` pointing to the next node.
- If `front.val` equals `val`, skip that node by updating `temp.next`.
- Otherwise, move `temp` to the next node.
- Return the updated `head`.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:

        while head and head.val == val:
            head = head.next

        temp = head

        while temp != None and temp.next != None:
            front = temp.next

            if front.val == val:
                front = front.next
                temp.next = front
            else:
                temp = temp.next

        return head
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`