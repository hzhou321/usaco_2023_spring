# 2102

## prob2 - bronze

* Grid 
* Method 1 - use 2-D array
```
int grid[N][N] -- N is a variable -- variable length array 
int grid[1000][1000]
int **grid
grid = malloc
for i=0:N
     grid[i] = malloc
```
Pro:
* explicit two dimension, Grid[x][y]
Con:
* You have to deal with 2 index
```
x, y
x+1, y
x-1, y
x, y+1
x, y-1
```
* You need 2 hash map to store cache
* You need struct stack to backtrack

* Method 2 - use 1-D array
```
int grid[N*N]
int *grid
grid = calloc(N*N*sizeof(int))
```
Pro:
* 1 index
Cons:
* k = i*N+j
* i = k/N
* j = k%N

```
grid[0*N+1] = id
update cow[id]
update cow[grid[k-1]] if there is k-1
update cow[grid[k+1]] if there is k+1
update cow[grid[k-N]] if there is k-N
update cow[grid[k+N]] if there is k+N

## prob 3 - bronze
* straight description to code problem
* Challenge: need see the angle


## prob 1 - silver -- comfortable cows
   x            x
 x x x  ->    x x x x x x x x x
                o o o o o o o
                  o o o o o
                
```
while there is cow with 3 neighbors
    i <-- 
    add a new cow
    update stats
```
* Estimate that the worst case we need add cow 1000 to left, 1000 to the right, 1000 to the top, 1000 to bottom --> N2 = 3000, grid[N2*N2] -> X0 = 1000, Y0 = 1000
* (x, y) -> (j, i) ->  k = (i+Y0) * N2 + (j+X0) -> similar to i*N+j
* insight: if a cow is added to make uncomfortable, it will always be needed (but potentially be replaced by the actual cows)
* bit mask -- 4 slots either on or off -- use 4-bits to store - 1, 2, 4, 8 --> a number 0-0xf

## prob 2 - silver - year of the cow
x       x       x        x         X
  .  .     .         .

* K=1, jump to the erliest segment
* K=2, 

* Merge the neighboring groups --> a list of anscestor groups
* there is potentially a jump back, so it is beneficial to tream year 0 as a group as well
* If n_groups <= K, K jumps, just count the years in each group
* If n_groups > K, you can't jump to every group, you have to spend the gap, we need merge groups until you have K groups
* Strategy to merge? Merge the smallest gap, then next smallest gap, unitl there K group
* 
