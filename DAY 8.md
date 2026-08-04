## Graph
# BFS uses queue and adjlist
```python
def dfs(graph, start, visited=None):
    if visited is None:
        visited=set()
    visited.add(start)
    print(start)
    for next in graph[start] - visited:
        dfs(graph, next, visited)
    return visited
start=input("Enter the starting vertex: ")
graph={'0': set(['1','2']),
        '1': set(['0','3','4']),
        '2': set(['0']),
        '3': set(['1']),
        '4': set(['2','3'])}
dfs(graph, start, None)
```
Enter the starting vertex: 1
1
3
0
2
4

#DFS uses stack and adjlist
```python
import collections
def bfs(graph, root):
    visited, queue=set(), collections.deque([root])
    visited.add(root)
    while queue:
        vertex=queue.popleft()
        print(str(vertex)+" ", end=" ")
        for i in graph[vertex]:
            if i not in visited:
                visited.add(i)
                queue.append(i)
if __name__ =="__main__":
    graph={0: [1,2], 1: [2], 2: [3], 3: [1,2]}
    print("Following is breadth first traversal: ")
    bfs(graph, 0)
```
Following is breadth first traversal: 
0  1  2  3  

