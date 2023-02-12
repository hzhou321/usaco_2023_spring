# Lesson 4 - 22open - 230212

* Next week, do 2012

## prob 1 - photoshoot
GGGHGHHGHHHGHG
Goal: put G in even position

```
i_head = 0
i_tail = N-2
for i=N-1 downto 0 by 2  -> for (i = N-1; i>=0; i-=2)   --> (O(N))
   // TRY 1  
     // simulate the flip
     for i=0:i_tail
         tmp = A[i]
         A[i] = A[i_tail -i]
         A[i_tail-i] = A[i]
   // TRY 2
    check tail pair  --> A[i_tail], A[i_tail+1]  or  A[i_head], A[i_head+1]
    if need flip
        flip++
    else
        cut the tail --> i_tail-=2, i_head+=2
```

** Review is more effective then homework
   * preview or struggle to identify where you need work -- longest time
   * Lesson or coaching to find answer -- FOCUS  -- fixed 
   * review to digest and grow -- least time

## prob 2 - counting liars
.....]..........................
     L L    L 
...........[....................
       G  G  
 -> L > G -- > eliminate where L_i <= G_j     
 
 * Enumerate all (num_L, num_J) --> O(N^2)
 
## Prob 3 - Alchemy
```
5
2 0 0 1 0
---
3
5 2 3 4 -> 4 2 2 3
2 1 1   -> 1 1 0
3 1 2   -> 2 1 1

A[4] = A[2]+A[3]
A[1] = A[0]
A[2] = A[1]
 
Try make A[4] --> A[2] + A[3]
      Do I have A[3] -> yes -> A[3]--
      Do I have A[2] -> no -> Try make A[2] -> A[1]
                                  Do I have A[2] -> No -> Try make A[2]
                                                             ...
``` 
* Make sure you understand recursive function
* All recursive functions can be re-written into a while loop with a stack (backtracking)
```
bool try_make(int i)
    if (has_recepi[i])
        foreach j in recepi[i] // in reverse order
            if (A[j])
                A[j]--
            else
                ret = try_make(A[j])
                if ret == true
                    A[j]--
                else
                    return false
                    
int main()
   ...
   while (true)
       ret = try_make(N-1)
       if (ret == false)
           break
   ans = A[N-1]
```   

## Prob 1 silver - visits
```
4
1 10
2 20
3 30
0 40
```
A0 -> A1 -> A2  --> Ax
* Chain works, A tree always work
* Cycle need break one chain (at any link) --> of course we want to break the smallest value link
* A
B   C 
B1 B2 

Knowledge about tree
* A tree is a connected group, All n nodes are connected
* A tree does not have cycles
* A tree has N-1 connection 
* If a connected group has N nodes and N connections --> There will only be 1 cycle in the graph 
```
// find all connected groups, for each group there must be one cycle, and we need break it
int visited[N]
while true
    find i_next to be the first node we haven't visited
    i = i_next
    start an empty set
    while i is not visited
        visited[i] = true
        ans += V[i]
        i = A[i]
    // i is visited
    if i is in this set
        you found a cycle, traverse the cycle, find the weakest link, cut it
        ans -= V[link]
    else    
        no need to cut anything
        
        
$print ans        
```



