# Linked List

```python
class Node:
    def __init__(self,d):
        self.d = d
        self.next=None

class LinkedList:
    def __init__(self):
        self.head=None
    def insertBeg(self,d):
        node = Node(d)
        if self.head==None:
            self.head = node
        else:
            node.next=self.head
            self.head = node
    
    def insertEnd(self,d):
        node = Node(d)
        if self.head==None:
            self.head = node
        else:
            cur=self.head
            while(cur.next!=None):
                cur=cur.next
            cur.next=node
            
    def insertAny(self,d,pos):
        node = Node(d)
        if self.head==None:
            self.head = node
        else:
            cur = self.head
            for i in range(0,pos-1):
                cur=cur.next
            node.next=cur.next
            cur.next=node
            
    def middle(self):
        slow = self.head
        fast = self.head
        while fast and fast.next:
            slow=slow.next
            fast= fast.next.next
        print(slow.data)
        
    def traverse(self):
        cur = self.head
        while(cur!=None):
            print(cur.d,end="->")
            cur=cur.next

lis = LinkedList()
lis.insertBeg(100)
lis.insertEnd(200)
lis.insertEnd(300)
lis.insertEnd(400)
lis.insertAny(500,3)
lis.delete 
lis.traverse()
```
