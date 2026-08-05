# 404. Sum of Left Leaves

**Problem Link:** https://leetcode.com/problems/sum-of-left-leaves/

## Problem
Given the `root` of a binary tree, return the sum of all **left leaves**.

A **left leaf** is a node that:
- Is the **left child** of its parent.
- Has **no left child** and **no right child**.

## Approach (BFS - Queue)

- Use a queue to perform **Level Order Traversal**.
- Traverse each node in the tree.
- If a node has a left child:
  - Check whether it is a **leaf**.
  - If it is a leaf, add its value to the sum.
  - Otherwise, push it into the queue.
- If a node has a right child, push it into the queue.
- Return the final sum.

## Solution

```python
from collections import deque

class Solution:
    def sumOfLeftLeaves(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0

        summ = 0
        q = deque([root])

        while q:
            node = q.popleft()

            if node.left:
                if not node.left.left and not node.left.right:
                    summ += node.left.val
                else:
                    q.append(node.left)

            if node.right:
                q.append(node.right)

        return summ
```

## Example 1

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
9  → Left leaf  → Add 9
15 → Left leaf  → Add 15
7  → Right leaf → Ignore

Sum = 9 + 15 = 24
```

**Output:**

```text
24
```

---

## Example 2

**Input:**

```text
    1
```

**Process:**

```text
Only one node.

No left leaf exists.
```

**Output:**

```text
0
```

## Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`