
# 📚 Binary Search Tree (BST) Notes for Placements (Python Version)

## 1. What is a Binary Search Tree (BST)?
A Binary Search Tree is a special binary tree where:

- Left child < Parent Node
- Right child > Parent Node

All nodes follow this ordering property.

## 2. Why BST?
- Efficient search, insertion, and deletion (O(log n) time for balanced BSTs).
- Useful in building faster search-based applications.

## 3. Basic Terms

| Term          | Meaning                         |
|---------------|----------------------------------|
| Root          | Top node                         |
| Leaf          | Node with no children             |
| Height        | Longest path from root to a leaf  |
| Balanced BST  | Left and right subtrees differ in height by at most 1 |

## 4. Node Structure (Python Class)
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
```
## 5. Basic Operations on BST
### a) Insertion
```python
def insert(root, key):
    if root is None:
        return Node(key)
    if key < root.data:
        root.left = insert(root.left, key)
    else:
        root.right = insert(root.right, key)
    return root
```

### b) Search
```python
def search(root, key):
    if root is None or root.data == key:
        return root
    if key < root.data:
        return search(root.left, key)
    return search(root.right, key)
```

### c) Deletion
3 cases:
- Node has no child → remove directly
- Node has one child → connect child to parent
- Node has two children → replace with inorder successor (smallest node in right subtree)

```python
def delete(root, key):
    if root is None:
        return root
    if key < root.data:
        root.left = delete(root.left, key)
    elif key > root.data:
        root.right = delete(root.right, key)
    else:
        if root.left is None:
            return root.right
        elif root.right is None:
            return root.left
        
        temp = find_min(root.right)
        root.data = temp.data
        root.right = delete(root.right, temp.data)
    return root

def find_min(node):
    current = node
    while current.left:
        current = current.left
    return current
```

## 6. Traversals (Same as Binary Tree)
**Inorder Traversal of BST gives sorted order of elements.**
```python
def inorder(root):
    if root is None:
        return
    inorder(root.left)
    print(root.data, end=" ")
    inorder(root.right)
```

## 7. Properties of BST
| Property       | Explanation                         |
|----------------|--------------------------------------|
| Search Time    | O(log n) for balanced BST            |
| Insert Time    | O(log n) for balanced BST            |
| Delete Time    | O(log n) for balanced BST            |
| Worst Case     | O(n) for skewed trees (like a linked list) |

## 8. Important BST Problems
| Problem                   | Idea                               |
|----------------------------|------------------------------------|
| Validate BST               | Check left < root < right recursively |
| Lowest Common Ancestor     | Based on node values              |
| Kth Smallest Element       | Inorder traversal                 |
| Floor and Ceil in BST      | Adjust search depending on value  |
| BST to Sorted Linked List  | Inorder traversal                 |

### a) Validate if a Tree is BST
```python
def is_valid_bst(root, left=None, right=None):
    if root is None:
        return True
    if left and root.data <= left.data:
        return False
    if right and root.data >= right.data:
        return False
    return is_valid_bst(root.left, left, root) and is_valid_bst(root.right, root, right)
```

### b) Lowest Common Ancestor (LCA) in BST
```python
def lca_bst(root, n1, n2):
    if root is None:
        return None
    if root.data > n1 and root.data > n2:
        return lca_bst(root.left, n1, n2)
    if root.data < n1 and root.data < n2:
        return lca_bst(root.right, n1, n2)
    return root
```

### c) Kth Smallest Element
```python
def kth_smallest(root, k):
    stack = []
    while True:
        while root:
            stack.append(root)
            root = root.left
        root = stack.pop()
        k -= 1
        if k == 0:
            return root.data
        root = root.right
```

### d) Find Floor and Ceil in BST
```python
def find_floor(root, key):
    floor = None
    while root:
        if root.data == key:
            return root.data
        if key > root.data:
            floor = root.data
            root = root.right
        else:
            root = root.left
    return floor

def find_ceil(root, key):
    ceil = None
    while root:
        if root.data == key:
            return root.data
        if key < root.data:
            ceil = root.data
            root = root.left
        else:
            root = root.right
    return ceil
```

## 9. Self-Balancing BSTs (Advanced)
| Tree Type        | Feature                    |
|------------------|-----------------------------|
| AVL Tree         | Height balanced BST         |
| Red-Black Tree   | Balanced using colors       |
*(You only need to know basics for most placements.)*

## 10. How to Master BSTs for Placements
- ✅ Be strong in insert, search, delete.
- ✅ Practice Inorder Traversal (very important).
- ✅ Solve problems on validate BST, LCA, floor/ceil.
- ✅ Know when BST can become skewed (important in interviews).

## 🌟 Quick Tip
Whenever you are stuck, draw tree diagrams manually to visualize recursion.

Focus on "divide into subproblems" approach.

## ✨ Conclusion
Binary Search Trees form the base for a lot of efficient algorithms.

Mastering BST will help you easily move on to advanced trees like AVL, Segment Trees, etc.
