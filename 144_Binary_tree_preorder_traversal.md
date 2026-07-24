# 144. Binary Tree Preorder Traversal

**Problem Link:** https://leetcode.com/problems/binary-tree-preorder-traversal/

## Problem
Given the `root` of a binary tree, return the **preorder traversal** of its nodes' values.

Preorder traversal follows the order:

```text
Root → Left → Right
```

## Approach (Recursion)
- Create an empty list `arr` to store the traversal.
- Define a recursive function `pre(root)`.
- If the current node is `None`, return.
- Visit the current node by adding its value to `arr`.
- Recursively traverse the left subtree.
- Recursively traverse the right subtree.
- Return `arr`.

## Solution

```python
class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        arr = []

        def pre(root):
            if not root:
                return

            arr.append(root.val)
            pre(root.left)
            pre(root.right)

        pre(root)
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
Root → Left → Right

Visit 1

Left = None

Go Right → 2

Visit 2

Go Left → 3

Visit 3
```

**Output:**

```text
[1,2,3]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(h)`

where:
- `n` = Number of nodes
- `h` = Height of the tree (recursion stack)