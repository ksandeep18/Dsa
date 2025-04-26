📚 Binary Tree Notes for Placements (Python Version)
1. What is a Binary Tree?
A tree is a hierarchical data structure (parent-child relationship).

A binary tree is a tree where each node has at most 2 children:
Left child
Right child

2. 
Basic Terms
Term	Meaning
Node	An element containing data and links to children
Root	Topmost node
Leaf Node	Node with no children
Parent	Node with child nodes
Child	Node coming from a parent node
Height of Tree	Number of edges in longest path from root to a leaf
Depth of Node	Distance from root to that node

3. Structure of a Node (Python Class)
python
Copy code
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
4. Types of Binary Trees
Type	Meaning
Full Binary Tree	Every node has 0 or 2 children
Complete Binary Tree	All levels completely filled except maybe last level (filled from left)
Perfect Binary Tree	All levels completely filled, all leaves at same level
Balanced Binary Tree	Height ≈ log(N); difference of left & right subtree heights is at most 1
Degenerate/Skewed Tree	Tree behaves like a linked list (only left or only right children)

5. Basic Tree Traversals (Very Important)
Traversal = Visiting all nodes.

a) Preorder Traversal (Root → Left → Right)
python
Copy code
def preorder(root):
    if root is None:
        return
    print(root.data, end=" ")
    preorder(root.left)
    preorder(root.right)
b) Inorder Traversal (Left → Root → Right)
python
Copy code
def inorder(root):
    if root is None:
        return
    inorder(root.left)
    print(root.data, end=" ")
    inorder(root.right)
c) Postorder Traversal (Left → Right → Root)
python
Copy code
def postorder(root):
    if root is None:
        return
    postorder(root.left)
    postorder(root.right)
    print(root.data, end=" ")
d) Level Order Traversal (Breadth First Search - BFS)
Using queue.

python
Copy code
from collections import deque

def level_order(root):
    if root is None:
        return
    q = deque()
    q.append(root)
    while q:
        node = q.popleft()
        print(node.data, end=" ")
        if node.left:
            q.append(node.left)
        if node.right:
            q.append(node.right)
6. Important Properties
Property	Formula
Maximum nodes at level l	2<sup>l</sup>
Maximum nodes in tree of height h	2<sup>h+1</sup> - 1
Minimum height for n nodes	log₂(n+1) - 1
7. Important Binary Tree Problems (Simple Ideas)
Problem	Idea
Height of tree	Recursively find height of left & right subtree and take max
Count total nodes	Recursively count left + right + 1
Count leaf nodes	If node is leaf, count 1
Diameter of tree	Longest path between any two nodes
Mirror tree	Swap left and right for all nodes
Check if two trees are identical	Recursively check root values and left & right subtrees
8. Advanced Binary Tree Problems (Frequently Asked)
a) Height of a Binary Tree
python
Copy code
def height(root):
    if root is None:
        return 0
    return 1 + max(height(root.left), height(root.right))
b) Count Total Nodes
python
Copy code
def count_nodes(root):
    if root is None:
        return 0
    return 1 + count_nodes(root.left) + count_nodes(root.right)
c) Diameter of Binary Tree
Idea: At each node, diameter = left height + right height.

python
Copy code
def diameter_of_binary_tree(root):
    diameter = [0]

    def height(node):
        if node is None:
            return 0
        lh = height(node.left)
        rh = height(node.right)
        diameter[0] = max(diameter[0], lh + rh)
        return 1 + max(lh, rh)

    height(root)
    return diameter[0]
d) Check if Two Trees are Identical
python
Copy code
def is_identical(root1, root2):
    if root1 is None and root2 is None:
        return True
    if root1 is None or root2 is None:
        return False
    return (root1.data == root2.data and
            is_identical(root1.left, root2.left) and
            is_identical(root1.right, root2.right))
e) Mirror of Binary Tree
python
Copy code
def mirror(root):
    if root is None:
        return None
    root.left, root.right = mirror(root.right), mirror(root.left)
    return root
f) Lowest Common Ancestor (LCA)
python
Copy code
def lca(root, n1, n2):
    if root is None:
        return None
    if root.data == n1 or root.data == n2:
        return root

    left = lca(root.left, n1, n2)
    right = lca(root.right, n1, n2)

    if left and right:
        return root
    return left if left else right
g) Check if Tree is Balanced
python
Copy code
def is_balanced(root):
    def check(node):
        if node is None:
            return 0
        lh = check(node.left)
        if lh == -1:
            return -1
        rh = check(node.right)
        if rh == -1:
            return -1
        if abs(lh - rh) > 1:
            return -1
        return 1 + max(lh, rh)

    return check(root) != -1
h) Serialize and Deserialize a Binary Tree
python
Copy code
# Serialize
def serialize(root):
    arr = []

    def helper(node):
        if node is None:
            arr.append(None)
            return
        arr.append(node.data)
        helper(node.left)
        helper(node.right)

    helper(root)
    return arr

# Deserialize
def deserialize(arr):
    def helper(index):
        if index[0] >= len(arr) or arr[index[0]] is None:
            index[0] += 1
            return None
        root = Node(arr[index[0]])
        index[0] += 1
        root.left = helper(index)
        root.right = helper(index)
        return root

    return helper([0])
9. Advanced Tree Variations
Tree Type	Meaning
Binary Search Tree (BST)	Left child < Root < Right child
AVL Tree	Self-balancing BST (height balance)
Segment Tree	Used for range queries like min, max, sum
Binary Indexed Tree (Fenwick Tree)	Used for efficient prefix sum queries
10. How to Master Trees for Placements
✅ Understand all 4 Traversals (Inorder, Preorder, Postorder, Level Order)

✅ Practice Problems like Height, Nodes Count, Leaf Count

✅ Solve Intermediate Problems like Diameter, Mirror, LCA

✅ Attempt some Serialization, Deserialization problems

✅ Learn Binary Search Trees (BST) separately (important for interviews)

🎯 Conclusion
Binary Trees are crucial for DSA interviews.
They check:

Recursion skills

Understanding of depth-first search (DFS) and breadth-first search (BFS)

Handling corner cases (null nodes, single node trees, etc.)

Master the basics first → Then move to intermediate and advanced topics.
With 20–30 good problems, you'll be very strong in Trees!

🌟 Quick Tip
If you find recursion confusing, draw tree diagrams manually — it helps A LOT!


