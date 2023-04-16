# Lesson 13 - 2023-04-16 - 23 Open

## prob1 bronze - FEB

* base_count --- BB EE
```
last_char = 0;
for i=0:N
    if S[i] == last_char
        base_count++
    elif S[i]==F    
```
* BBEEF -> BEF
* if even number of F , if BFF..FFB -
*                          BFF..FFE
* if odd number of F,   if BFF.. FB -   -> base_count+=1, BFF..FFB, 
*                          BFF...FE - 

```
#- Range math
#- {0,..n} + {0,..,m} = {0,...,n+m}
#- {0,2,4,...,n} + {0,2,4,...,m} -> {0,2,4,...,n+m}
#- {0,1,2,...,n} + {0,2,4,...,m} -> {0,1,2,...,n+m}

#- residue
#- n=0, is_same ? 1 : 0
#- n=1, is_same ? {0,2} : 1

# F(n, is_same) -> {0, 2} + F(n-2, is_same) 
#                  {1}    + F(n-2, !is_same)
# --
# {0,1,2}+{0,1,2} -> {0,1,2,3,4}

#- n=2k,   is_same ? {1,1, 3,3,..,2k+1} : {0,2, 2,4, ..,2k}
#                    {1,3,5,..,2k+1}    : {0,2,4,..,2k}
#                    1+{0,2,4,..,n}    : {0,2,4,..,n}
#- n=2k+1, is_same ? {0,2,2, 2,4,4, ..} : {1,1,3, 3,3,5,..}
#                    {0,2,4,..,2k+2}    : {1,3,5,..,2k+1}
#                    {0,2,4,..,n+1}      : 1+{0,2,4,..,n-1}

```

## prob2 - bronze
* maximum # of sentences (SV, SVO), limited by v1+v2
   * if nouns < (v1 + 2 * v2)  # strategy is to prefer S+V1
       * v2 = (nouns - v1) / 2 --> what if nouns < v1 -> v1=nouns, v2=0
       *                       --> what if (nouns -v1) is odd
       * 2 noun, 1 V1, 1 V2 -> V2                      
       
* maximum nouns you can you
   * v1+v2 * 2 + C       

* limit conj by P
* restrict v1 + v2 < P+conjs

ans = nouns + v1 + v2 + conjs
foreach v1
    output noun + v1
    add conj or period
foreach v2
    output noun + v2 + noun
    if is last v2
        output remaining nouns with , noun
    add conj or period
That's it

## prob3 - bronze
It is hard
