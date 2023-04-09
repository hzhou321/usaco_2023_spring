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
