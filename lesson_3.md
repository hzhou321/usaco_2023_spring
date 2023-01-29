Lesson 3 - 1/29/2023 - USACO 2022 Jan

ASCII code
"Hello World" -> char[100] -> 'H', 'e', ..., ' ', 'W', ..., 'd', '\0'
                           -> 0x48, 0x65, ............,           0 --> '0' is NOT 0, '0' is 0x30
                           
'^A' == '^a' == '^1' == 1
'9' - '0', say `char c = '8'` -> 
```
if (c >= '0' && c <= '9') {  // isdigit(c)
    int val = c - '0';
} 
```

```
int counts[26];
for i = 0:26
    counts[i] = 0;
```    
```
// to increment the count
counts[c - '0']++
```

```
char A[6][4]
for i=0:6
    scan("%s", A[i])
char *Correct[4], *Guess[4]
Correct = counts[0]   // right1 === Correct[0], guess3 === Guess[2]
Guess = count[3]
    ...
```

## Prob 2
A, B, to find C so that: A > B, B > C, C > A
                    or : A < B, B < C, C < A
                    
```
// declare
bool beat(int *A, int *B);

main:
if (A == B) --> return -1
elif (A > B)
     foreach possible C
          if beat(B, C) && beat(C, A)
              return yes
elif (A < B)
     foreach ...
         ...
return -1

// -----------------------------------------
bool beat(int *A, int *B):
    .... 
    return 

// ----- 
int string_to_number(char *s)    
```

## Prob 3
* T *idependent* subquestions
*  O(T * N) --> O(N)
```
// --- INPUT
A[]
for i=0:T
    A 
    input > A
    solve (...)
```

* h0, h1, h2, ....
* r,  r,  r,  ....
* h0 = r + a, h1 = r + a + b, h2 = r + b + c, ... 
* n = 1: r == h0
* n = 2; b==0, h0 == h1, r == h0
* n = 3; h0 = r + a, h1 = r + a + b, h2 = r + b -> r = h0 + h2 - h1 -> r = h0 - h1 + h2 -h3 + h4. 

# prob 1 - silver
* a, b -> a' == b'
*  31 - 13
*  a > b: 
  * 2, 1 --> 2/2, 1+1
  * 3, 1 --> (3-1)/2,  
  * 4, 1 --> 4/2
  * keep divide, until a < b --> then solve a<b
  
*  a < b: 
   * multiply or plus 1

* bronze may be O(3^N)
* exploring the cases and you can narrowdown the space


    
    
solve: 
```
