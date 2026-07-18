# 876. Middle of the Linked List

**Problem Link:** https://leetcode.com/problems/middle-of-the-linked-list/

## Problem
Given the `head` of a singly linked list, return the middle node of the linked list.

- If there are two middle nodes, return the **second middle node**.

## Approach 1: Counting Nodes
- Traverse the linked list to count the total number of nodes.
- Find the middle position:
  - If the number of nodes is odd, middle = `(count + 1) // 2`.
  - If the number of nodes is even, return the second middle, i.e., `(count + 2) // 2`.
- Traverse the linked list again until the middle position.
- Return the middle node.

## Solution (Counting Approach)

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        count = 0

        temp = head

        while temp:
            count += 1
            temp = temp.next

        if count % 2 != 0:
            x = (count + 1) // 2
        else:
            x = (count + 2) // 2

        temp = head

        for i in range(1, x):
            temp = temp.next

        return temp
```

## Approach 2: Slow and Fast Pointer
- Initialize two pointers:
  - `slow` moves one step at a time.
  - `fast` moves two steps at a time.
- When `fast` reaches the end, `slow` will be at the middle.
- If the list has an even number of nodes, `slow` automatically points to the second middle node.

## Solution (Slow & Fast Pointer)

```python
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:

        slow = head
        fast = head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        return slow
```

## Complexity

### Counting Approach
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

### Slow & Fast Pointer Approach
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`