## Trees & Graphs
# BST 
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
        
class BST:
    def __init__(self):
        self.root = None
        
    def insert(self, node, data):
        if node is None:
            return Node(data)
        
        if data < node.data:
            node.left = self.insert(node.left, data)
        else:
            node.right = self.insert(node.right, data)
        return node
            
    def inorder(self, node):
        if node:
            self.inorder(node.left)
            print(node.data, end=" ")
            self.inorder(node.right)

    def preorder(self, node):
        if node:
            print(node.data, end=" ")
            self.preorder(node.left)
            self.preorder(node.right)

    def postorder(self, node):
        if node:
            self.postorder(node.left)
            self.postorder(node.right)
            print(node.data, end=" ")

    def search(self, node, key):
        if node is None:
            return False
        if node.data == key:
            return True
        if key < node.data:
            return self.search(node.left, key)
        else:
            return self.search(node.right, key)
    def height(self, node):
        if node is None:
            return 0
        left=self.height(node.left)
        right=self.height(node.right)
        return max(left, right)+1
bst = BST()
root = None
root = bst.insert(root, 8)
root = bst.insert(root, 3)
root = bst.insert(root, 1)
root = bst.insert(root, 6)
root = bst.insert(root, 7)
root = bst.insert(root, 10)
root = bst.insert(root, 14)
root = bst.insert(root, 4)
print("Inorder Traversal:")
bst.inorder(root)
print("\n\nPreorder Traversal:")
bst.preorder(root)
print("\n\nPostorder Traversal:")
bst.postorder(root)
print("\n\nSearch 6:")
print(bst.search(root, 6))
print("\n\nHeigth of Tree:")
print(bst.height(root))

```
Inorder Traversal:
1 3 5 6 9 

Preorder Traversal:
5 1 3 6 9 

Postorder Traversal:
3 1 9 6 5 

Search 6:
True
