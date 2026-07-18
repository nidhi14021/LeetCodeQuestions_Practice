# 83. Remove Duplicates from Sorted List

**Problem Link:** https://leetcode.com/problems/remove-duplicates-from-sorted-list/

## Problem
Given the `head` of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.

## Approach
- Traverse the linked list using a pointer `temp`.
- Compare the current node with the next node (`front`).
- If both nodes have the same value, skip the duplicate node by updating `temp.next`.
- Otherwise, move `temp` to the next node.
- Continue until the end of the list.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        temp = head

        while temp != None and temp.next != None:
            front = temp.next

            if temp.val == front.val:
                front = front.next
                temp.next = front
            else:
                front = front.next
                temp = temp.next

        return head
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`