Lesson 12 - 4/9/2023 - USACO 2302

# prob1 - bronze
```
// d_list[N], b_list[N]
cur_start = d_list[0]
cur_end = d_list[0] + b_list[0] 
count = 0
for i=1:N
    if d_list[i] < cur_end
       cur_end += b_list[i]
       if (cur_end > T) {
           ...
           break
       }    
    else
       count += cur_end-cur_start
       cur_start = d_list[i]
       cur_end = d_list[i] + b_list[i]
       if (cur_end > T)
           ...
           break
// count += cur_end - cur_start
print count
```

# prob2 - bronze
```
int A[N][N+1]
int B[N][N+1]
int C[N][N+1]
// input -> N, K, A, B

// init
for i=0:N
    for j=0:N
        C[i][j] = '.'

for i0=0:N-K+1
    for j0=0:N-K+1
        for dir=0:4
            if can_stamp(i0,j0,dir)
               stamp(i0,j0,dir)
if match(A, C)
    print YES
else
    print NO

bool can_stamp(i0, j0, dir) {
   for ii=0:K
       for jj=0:K
           i = i0+ii
           j = j0+jj
           switch dir {
               case 0: 
                   if A[i][j]=='.' && B[ii][jj] == '*'
                       return false
                   break;
               case 1:
                   ...
                   break;
               case 2:
                   ...
                   break;
               case 3:
                   ...
                   break
   return true;
}
void stamp(i0, j0, dir) {
   for ii=0:K
       for jj=0:K
           i = i0+ii
           j = j0+jj
           switch dir {
               case 0: 
                   C[i][j] = B[ii][jj]; 
                   break;
               case 1:
                   C[i][j] = B[K-1-jj][ii]
                   break;
               case 2:
                   C[i][j] = B[K-1-ii][K-1-jj]
                   break;
               case 3:
                   C[i][j] = B[jj][K-1-ii]
                   break
}
```

# prob3 - bronze
```
cost = K+1
cur_end = d[0]
for i=1:N
    if d[i] - cur_end <K
       cost+=d[i]-cur_end
    else
       cost+=K+1
```

# prob1 - silver
```
input: A, B, C  and Tc Tm
for every order:
     A*Tc+B*Tm need be < C
output: M=a+b
for every order:
    Aa + Bb > A*Tc+B*Tm - C
    
 for every possible a    // ~ 10^9
     for every possible b    // ~ 10^9
         test every order       // ~100
         if yes -> update minimum M=a+b
```
* binary search
    * for problems that search minimum/maximum over a big linear range, turns O(N) -> O(lgN) ~ O(1)
    * if binary search M, find 1st M that works
```
if check(0)
    ans=0
else
    M1 = 0
    M2 = Tc+Tm-2
    while M1<=M2
        M3 = (M1+M2)/2
        if check(M3)
            M2 = M3-1
        else
            M1 = M3+1
   // M2, M1 
   ans = M1
```
```
bool check(M) {
    for a=0:M (or Tc-1)
        b = M-a
           for each order
               if fail return fase
   rerturn true            
}
```
```
foreach order
   Aa+B(M-a) > (ATc+BTm-C)
   (A-B)a > (ATc+BTm-C)-BM
   if A>B
        a > (...)/(A-B)  -> gets a_min, b_max --> fails if a_min>a_max or b_min>b_max
   if B>A
        b > (...)/(B-A)  -> gets b_min, a_max 
   if A==B
        Aa+Ab > ...
        AM>...
```
# prob2 - silver
* p0 -> p1 -> p2 -> ... -> p(n-1)
*          q

* -> only need maximum of 2 comparisons

# prob3 - silver
* backtracking
* nodes -- airport 
* edges -- flights
* start at airport 0
* output: arrive_time[N]
```
arrive[0]=0
stack.push(0)
while stack.size()>0
    i = stack.back()
    stack.pop_back()
    foreach j in edges[i]  // j is a flight (edge) // optimization, iterate from back
        if can_fly // arrive[i]+layover < r
            // means you can arrive at d by s
            if arrive[d]==-1 || arrive[d] > s
               arrive[d] = s
            // optimization -> remove this flight   --> edges[i].pop_back
for i=0:N
    print arrive[d]
```
* it will timeout because the same airport gets puhed on to the stack again again
* Insight: we only need check the flight we haven't taken
*       -> need remove the flights that been taken
*       -> maximally, we will only visit M flights -> O(M+N)
