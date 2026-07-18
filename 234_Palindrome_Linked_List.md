# 234. Palindrome Linked List

**Problem Link:** https://leetcode.com/problems/palindrome-linked-list/

## Problem
Given the `head` of a singly linked list, return `true` if it is a palindrome; otherwise, return `false`.

## Approach
- Traverse the linked list and store each node's value in an array.
- Use two pointers:
  - `left` starts from the beginning of the array.
  - `right` starts from the end of the array.
- Compare the elements at both pointers.
- If any pair is different, return `False`.
- If all pairs match, return `True`.

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        org = head
        temp = head
        arr = []

        while temp != None:
            arr.append(temp.val)
            temp = temp.next

        left = 0
        right = len(arr) - 1

        while left < right:
            if arr[left] != arr[right]:
                return False
            left += 1
            right -= 1

        return True
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`