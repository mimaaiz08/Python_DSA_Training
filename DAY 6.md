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
Index: 3
# Binary Search
```python
arr = [1,2,3,4,5,6,7]
key=4 
def binary(arr, key):
    low=0
    high=len(arr)-1
    while low<=high:
        mid=(low+high)//2
        if arr[mid]==key:
            return mid
        elif arr[mid]<key:
            low=mid+1
        else:
            high=mid-1
    return -1
result=binary(arr, key)
if result!=-1:
    print("Index: ",result)
else:
    print("Not Found")
```
Index: 3
