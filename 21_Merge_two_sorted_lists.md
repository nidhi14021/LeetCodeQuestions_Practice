# 21. Merge Two Sorted Lists

**Problem Link:** https://leetcode.com/problems/merge-two-sorted-lists/

## Problem
You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one sorted linked list and return its head.

## Approach (Recursion)
- If one of the lists is empty, return the other list.
- Compare the values of the first nodes of both lists.
- If `list1.val` is smaller than or equal to `list2.val`:
  - Connect `list1` to the merged result of `list1.next` and `list2`.
- Otherwise:
  - Connect `list2` to the merged result of `list1` and `list2.next`.
- Return the head of the merged linked list.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        if not list1 or not list2:
            return list1 or list2

        if list1.val <= list2.val:
            list1.next = self.mergeTwoLists(list1.next, list2)
            return list1
        else:
            list2.next = self.mergeTwoLists(list1, list2.next)
            return list2
```

## Example

**Input:**

```text
list1 = [1,2,4]
list2 = [1,3,4]
```

**Output:**

```text
[1,1,2,3,4,4]
```

## Complexity
- **Time Complexity:** `O(n + m)`
- **Space Complexity:** `O(n + m)` (due to recursive call stack)