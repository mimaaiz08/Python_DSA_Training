## Trees
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
        left = self.height(node.left)
        right = self.height(node.right)
        return max(left, right) + 1

    def inordersucessor(self, node):
        curr = node.right
        while curr and curr.left:
            curr = curr.left
        return curr

    def delete(self, node, key):
        if node is None:
            return None
        if key < node.data:
            node.left = self.delete(node.left, key)
        elif key > node.data:
            node.right = self.delete(node.right, key)
        else:
            if node.left is None:
                return node.right
            elif node.right is None:
                return node.left

            temp = self.inordersucessor(node)
            node.data = temp.data
            node.right = self.delete(node.right, temp.data)
        return node

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

print("\n\nInorder Sucessor of Root (8):")
succ_node = bst.inordersucessor(root)
print(succ_node.data if succ_node else "None")

print("\nInorder Traversal after deleting 6:")
root = bst.delete(root, 6)
bst.inorder(root)
print()

```
Inorder Traversal:
1 3 4 6 7 8 10 14 

Preorder Traversal:
8 3 1 6 4 7 10 14 

Postorder Traversal:
1 4 7 6 3 14 10 8 

Search 6:
True

Heigth of Tree:
4


Inorder Sucessor of Root (8):
10

Delete: 

Inorder Traversal after deleting 6:
1 3 4 7 8 10 14 
