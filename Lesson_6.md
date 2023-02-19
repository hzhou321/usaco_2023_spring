# Lession 6 - 2012

## 2012 - Bronze 1 
 Sort the 7 number, got A, B and A+B+C, then solve C
 
## Bronze 2
Enumerate all the ranges -- (i, j) pairs -- Always inclusive/exclusive
```
for i=0:N
   for j=i+1:N+1
       // check
```

## Bronze 3
```
// simulate the time step, works for 1-5
while true
   foreach i
       # check if the cow will be stopped
           for each j, check if j will interject
           spit the infinite if not going to be stopped
       # move cow i one step, put the rut (last position) into a set, update grass[i]
       # if cow stopped (hit a rut in the set), skip the cow on
   if all cow are stopped or infinite, break    
```

```
// N cows, N lines - N * N intersections - stops
// --> elliminate all the pseudo stops, 
    each stop has time (the larger distance of the track)
    sort the time, we know the smallest time stop is real, say cow i, then ellimiate all other stops from cow i
       fine the smallest time stop in the remainning, and loop
// --> each remaining stop gives grass[i]
```

## Silver 1
* N nodes, N-1 edges, all connected --> A Tree
* root -- any node of a tree can serve as a root
* asking for depth
```
int depth[N] = {-1}
int adj[N][N-1]
stack.push_back(0)
depth[0]=0
while !stack.empty()
    i = stack.pop()  // last backtracking point
    for each adj[i]
        if (depth[i] != -1)
           stack.push_back(j)
           depth[j] = depth[i] + 1
```

## 2212 -- Bronze 1
x x x x x
     |->
* O(N) - linear enumeration     

## Bronze 2
     x x x
   P  
     |<- P ->|
 * iterate cow from left to right
 *    if the cow !covered by existing patch
 *        place a new patch to as right as it can (i + K)

## Bronze 3
B[N] of 0 or 1
O(2^N)

M cases, O(M^2)
```
for i=0:M
   for j=i+1:M
       foreach digit k
          if (s[i][k] == s[j][k] && A[i] == A[j]) or (s[i][k] == s[j][k] && A[i] != A[j])
              // potential key input
           else
              -> k is masked by other digits -> write the mask
    
```
```
if B[1]
   return 1
elif B[2]
    return 1
```
* A[i] == A[j], set_agree, set_diff
   * set_agree have to have 1 common
* A[i] != A[j], set_agree, set_diff 
                  
