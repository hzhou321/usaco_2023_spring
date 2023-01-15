Lesson 2 - 1/15/2023 - 2112

# Lonely Photos

GHGHG 
* G, H
* GHG, GH, GGGGH

Casework - 2 cases, single H or single G 
```
is_lonely {
   for i=0:n
       if L[i] == 'H'
           n_H++
   if (n_H) == 1
       return true
   return false    
}
```

```
for i=0:N
    for j=i+1:N
        if (is_lonely(i, j))
            cnt++
```
G, GH, GHG -> do a single scan

* Estimate time-complexity
    * O(N^x) -- the time in worst case
    * O(N^3) for above
* in USACO, to pass <2sec ~ 10^9, O(1)  ~ 1us -> O(N) -> N ~< 10^6; for O(N2)N~10^3

So above algorithm only passes 4 tests, modify the algorithm to O(N2), then pass 10 tests


# Walking Home
N -> 2N -> 2^N
Case work K = 1, 2, 3 
K=1: H(orizontal) have to turn at N-1  --> O(1)
     V(ertical) ...
K=2: H: for i=1:N (iterate first turn point) --> O(N)
K=3: O(N2)
* foreach starting i, scan the whole range
* for last test, we need O(N)

GGG --> HGGGGGG -> HG -> if you preprocess, detect the groups ahead of time 

# Air ...
5
1 5 3 3 4
1 2 2 2 1
# preprocess 
-> 0 3 1 1 3

# Siver - Closest Cow Wins
x    x     x    x    x     x
        jj              j     j
       p             p
       
 M, N -> M!/N!   
 
 2 ps can clain t2+t3+t4 -> T
 What is max 1p can claim
     `for each position, calculate T, -> max 
     max + (T - max)
 T1, .., max, ..., (T-max), ...    
       
       
       
