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
[1, 2, 3, 4, 5, 6, 7]

# Selection Sort
```python
def selection_sort(arr):
    n=len(arr)
    for i in range(n):
        min_index=-1
        for j in range(i+1, n):
            if arr[j]<arr[min_index]:
                min_index=j
        arr[i], arr[min_index]=arr[min_index], arr[i]
arr=[64, 25, 12, 22, 11]
selection_sort(arr)
print(arr)
```
[11, 12, 22, 25, 64]

# Quick Sort
```python
def quick_sort(arr):
    if len(arr)<=1:
        return arr
    pivot=arr[-1]
    left=[]
    right=[]
    for x in arr[:-1]:
        if x<=pivot:
            left.append(x)
        else:
            right.append(x)
    return quick_sort(left) + [pivot] + quick_sort(right)
arr=[2,7,4,6,5,1]
sorted_arr=quick_sort(arr)
print(sorted_arr)
```
[1, 2, 4, 5, 6, 7]

# Merge Sort
```python
def merge_sort(arr):
    if len(arr)>1:
        mid=len(arr)//2
        left=arr[:mid]
        right=arr[mid:]
        merge_sort(left)
        merge_sort(right)
        i=j=k=0
        while i<len(left) and j<len(right):
            if left[i]<right[j]:
                arr[k]=left[i]
                i+=1
            else:
                arr[k]=right[j]
                j+=1
            k+=1
        while i<len(left):
            arr[k]=left[i]
            i+=1
            k+=1
        while j<len(right):
            arr[k]=right[j]
            j+=1
            k+=1
            
arr=[38, 27, 43, 3, 9, 82, 10]
merge_sort(arr)
print(arr)
```
[3, 9, 10, 27, 38, 43, 82]

# Solved leetcode problem 20
