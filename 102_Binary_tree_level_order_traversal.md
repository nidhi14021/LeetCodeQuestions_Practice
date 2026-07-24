# 102. Binary Tree Level Order Traversal

**Problem Link:** https://leetcode.com/problems/binary-tree-level-order-traversal/

## Problem
Given the `root` of a binary tree, return the **level order traversal** of its nodes' values.

Level order traversal means visiting the tree **level by level**, from **left to right**.

## Approach (BFS using Queue)
- If the tree is empty, return an empty list.
- Create a queue and add the root node.
- While the queue is not empty:
  - Create an empty list `level` to store the current level's nodes.
  - Traverse all nodes currently in the queue (one level).
  - Remove each node from the queue.
  - Add its value to `level`.
  - Add its left and right children to the queue if they exist.
  - Add `level` to the final answer.
- Return the final list.

## Solution

```python
from collections import deque

class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        arr = []
        q = deque([root])

        if not root:
            return arr

        while q:
            level = []

            for i in range(len(q)):
                node = q.popleft()
                level.append(node.val)

                if node.left:
                    q.append(node.left)

                if node.right:
                    q.append(node.right)

            arr.append(level)

        return arr
```

## Example

**Input:**

```text
        3
       / \
      9   20
         /  \
        15   7
```

**Process:**

```text
Queue = [3]

Level 1:
Pop 3
Level = [3]
Queue = [9,20]

Level 2:
Pop 9
Pop 20
Level = [9,20]
Queue = [15,7]

Level 3:
Pop 15
Pop 7
Level = [15,7]
Queue = []
```

**Output:**

```text
[[3],[9,20],[15,7]]
```

## Complexity
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`