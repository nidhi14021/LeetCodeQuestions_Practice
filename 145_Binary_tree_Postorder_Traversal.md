# 145. Binary Tree Postorder Traversal

**Problem Link:** https://leetcode.com/problems/binary-tree-postorder-traversal/

## Problem
Given the `root` of a binary tree, return the **postorder traversal** of its nodes' values.

Postorder traversal follows the order:

```text
Left → Right → Root
```

## Approach (Recursion)
- Create an empty list `arr` to store the traversal.
- Define a recursive function `post(root)`.
- If the current node is `None`, return.
- Recursively traverse the left subtree.
- Recursively traverse the right subtree.
- Visit the current node by adding its value to `arr`.
- Return `arr`.

## Solution

```python
class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        arr = []

        def post(root):
            if not root:
                return

            post(root.left)
            post(root.right)
            arr.append(root.val)

        post(root)
        return arr
```

## Example

**Input:**

```text
        1
         \
          2
         /
        3
```

**Traversal:**

```text
Left → Right → Root

1:
Left = None

Go Right → 2

2:
Go Left → 3

Visit 3

Right = None

Visit 2

Visit 1
```

**Output:**

```text
[3,2,1]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(h)`

where:
- `n` = Number of nodes
- `h` = Height of the tree (recursion stack)