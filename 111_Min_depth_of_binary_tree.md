# 111. Minimum Depth of Binary Tree

**Problem Link:** https://leetcode.com/problems/minimum-depth-of-binary-tree/

## Problem
Given the `root` of a binary tree, return its minimum depth.

The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node.

## Approach (BFS / Level Order Traversal)
- If the tree is empty, return `0`.
- Use a queue to perform level-order traversal.
- Start from the root node at level `1`.
- Traverse each level one by one.
- If a leaf node (a node with no left and right child) is found, return the current level.
- Since BFS visits nodes level by level, the first leaf encountered gives the minimum depth.

## Solution

```python
from collections import deque

# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def minDepth(self, root: Optional[TreeNode]) -> int:
        q = deque()

        if root:
            q.append(root)
        else:
            return 0

        level = 1

        while q:
            for i in range(len(q)):
                node = q.popleft()

                if not node.left and not node.right:
                    return level

                if node.left:
                    q.append(node.left)

                if node.right:
                    q.append(node.right)

            level += 1

        return level
```

## Example

**Input:**

```text
    3
   / \
  9  20
     / \
    15  7
```

**Output:**

```text
2
```

**Explanation:**
- The nearest leaf node is `9`.
- Minimum depth = `2`.

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`