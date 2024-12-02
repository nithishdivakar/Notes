---
categories: null
date: 2024-01-01 00:00:00 +0000
index: 06c01
layout: post
status: doing
title: 06c01 In a Binary Tree
---

## LCA In Binary Tree

```python
class Node:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

def lowest_common_ancestor(root: "Node", p: "Node", q: "Node") -> "Node":
    def search(node):
        if node in [p, q, None]:
            return node
        left = search(node.left)
        right = search(node.right)
        if left and right:
            return node
        return left if left else right
    return search(root)
```