# Lesson 7 - 02/26/23 - 2101

## prob1 bronze
* Straight simulate
```
s_all[26]
str[N] -- ~1000
count = 0
j = 0
while (1) 
   count++
   for i=0:26
       if s_all[i] == str[j]
           j++
           if j==N
               goto ans
ans:
    print count
```
* The Big O notation -- worst case analysis
* O(N)

## prob2 bronze
* 1 1 2 2 2 2 -> 2 1 2 1 [2 2] -> 5

## prob3 bronze
A[N]
B[N]
A[i] <= B[i]
* O(N!) - permutaion
* Idea of permutaion: how many ways you can select first number -> N, ...2nd number N-1, ... -> N!
* How many ways you can select first stall for the tallest cow, count[B[i] > A[i]]-> C * C[n-1], C[

## prob1 Silver
* what is a permutation: A[N] {0, 1, 2, ..., N-1} - { 2, 4, ...5, ..}
* N!
* P is called *permutation array*: A[N], P[N]: A->B, A[i]=A[P[i]], P[2] = 5, means, position 2 -> position 5,  A[P[2]] = A[2]
* e.g. 0 2 -> position 0 goes to position 2, position 2 goes to position 0, P[0]=2, P[2]=0, P[1]=1 --> swap is a special permutation, where only two elements swaps
* Permutation can multiply, is not commutative, P1 * P2 -> P3
* Same idea as, in bronze, 1 + 1 + 1 + 1, K+K
```
for j=0:K
   A[b[j]] = A[a[j]]
-> P[]
while 1
    for i=0:N
        A[P[i]] = A[i]
```
* tell unique positions each cow will occupy
* If the shuffle is the same, then the same pos k -> the same pos l
* p1->p2->p3->p1->p2  -> a *cycle* -> inside the cycle, they just stay in the cycle -> [p1, p2, p3]
