# Searching Algorithm
# Linear Search
```python
arr = [1,2,3,4,5,6,7]
key=4 
def linear(arr, key):
    for i in range (len(arr)):
        if arr[i]==key:
            return i
    return -1
result=linear(arr, key)
if result!=-1:
    print("Index: ",result)
else:
    print("Not Found")
```

# Binary Search
