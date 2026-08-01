# Searching & Sort Algorithms
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

# Bubble Sort
```python
arr = [4,2,3,6,5,1,7]
n=len(arr)
def bubble(arr):
    for i in range(n):
        for j in range(i+1, n):
            if arr[i]>arr[j]:
                arr[i],arr[j]=arr[j],arr[i]
bubble(arr)
print(arr)
```
[1, 2, 3, 4, 5, 6, 7]

# Insertion Sort
```python
def insertion(arr):
    n=len(arr)
    for i in range(1,n):
        key=arr[i]
        j=i-1
        while j>=0 and arr[j]>key:
            arr[j+1]=arr[j]
            j=j-1
        arr[j+1]=key
arr = [4,2,3,6,5,1,7]
insertion(arr)
print(arr)
```

# Selection Sort
```python
