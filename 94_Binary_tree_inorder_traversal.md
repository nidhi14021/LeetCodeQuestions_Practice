# 94. Binary Tree Inorder Traversal

**Problem Link:** https://leetcode.com/problems/binary-tree-inorder-traversal/

## Problem
Given the `root` of a binary tree, return the **inorder traversal** of its nodes' values.

Inorder traversal follows the order:

```text
Left → Root → Right
```

## Approach (Recursion)
- Create an empty list `arr` to store the traversal.
- Define a recursive function `inorder(root)`.
- If the current node is `None`, return.
- Recursively visit the left subtree.
- Add the current node's value to `arr`.
- Recursively visit the right subtree.
- Return `arr`.

## Solution

```python
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        arr = []

        def inorder(root):
            if not root:
                return

            inorder(root.left)
            arr.append(root.val)
            inorder(root.right)

        inorder(root)
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
Left → Root → Right

1:
Left = None

Visit 1

Go Right → 2

2:
Go Left → 3

Visit 3

Visit 2
```

**Output:**

```text
[1,3,2]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(h)`

where:
- `n` = Number of nodes
- `h` = Height of the tree (recursion stack)