# Lession 14 - 2023-04-23

## Graphs

### Basic terms

Tree
* All connected nodes
* No cycles
* N-1 edges
* any node can traverse to any other node
* Any node can be a root

How to represent a graph
* nodes -> array/**vector**/map/set - a collection of data points
* edges -> edges[N][N] -> {0, 1}, matrix representation edges[i][j] -> whether node i is connected to node j -> O(N^2) storage -> takes O(N^2) to initialize
*       -> sparse connections like a tree. E.g edges array, Edges[M]
*       ->                                     Adj[N] -> vector

The classical tree traversal is via backtracking
```
vector<int> stack
stack.push_back(0)
while stack.size() > 0
    i = stack.pop
    for each j in adj[i]
        if j not in cache
           stack.push_back(j)
```

Binary tree - every node can have at most 2 children - left and right
each node can use struct node {left, right}

# tree traversal
* Depth-first search - DFS
* Bredth-first search - BFS
* Level search


