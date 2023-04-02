Lesson 11 - 2023-04-02

USACO 2023 January

* know all her breed -> has to be the 1st of 'G' or 'H'
* know the other leader -> one of them has to be the 1st of 'G' or 'H'

Enumeration
case 1 - 1st 'G' + (every possible 'H')
case 2 - 1st 'H' + (every possible 'G')
potential double count: 1st 'G' + 1st 'H'

step 1 - collect min_G, max_G, min_H, max_H
```
// get min_G
for i=0:N
    if s[i]=='G'
        min_G=i
        break
// get min_H
for i=0:N
    if s[i]=='H'
        min_H=i
        break      
// get max_G
for i=N-1 downto 0
    if s[i]=='G'
        max_G=i
        break;
// get max_H
...
```
Algorithm
```
// case 'G'
if E[min_G] >= max_G
    for i=0:min_G
        if s[i]=='H' && E[i]>=min_G
            ans++
// case 'H'
...
// check double counting -- there is no way, skip
```

### Wilson's algorith
* one leader of 'G' knows the other 'H' which is the first 'H'
* --> GG...GH....
* --> HH...HG....
* Exception The first G can cover to first H or first H-1 and there on other G afterwards


## prob2 - bronze
| -------------- [100] |
 [1   ]   [2  ]     --- cow_list
 ----------
     -------------  --- air_list
 * cow require c  -- simple
 * air drops p    -- additive

* Brute force -- enumerate all
* cow are fixed -> target[100] -> how many degree is required to drop
* possibilities of turning on M=10 -> 2^M -> <= 1024 
* --> Algorithm: try every possible configuration, cummulate the min cost
```
// enumerate all 2^M configurations, 2^0: 1<<0;   2^1: 1<<1; ... 2^M === 1<<M
min_cost=VERYHIGH
for n=0:(1<<M)
    // test this configuration
    for i=0:M
        if (n>>i) & 1
           cost += air[i].m
           for j=air[i].a:air[i].b  // adjust at input time to make [a,b)
               stall[j]+=air[i].p
    // check whether target[i]<=stall[i]
    if ok
        if min_cost > cost
           min_cost = cost             
```
## prob 3 - bronze
* if < 3 --> -1
* if > 3 --> need reduce to 3 --> n-3
* case ==3
    * MOO -- works, 0 needed
    * xMx -- won't work
    * xOx -- works, 1 or 2 more ops

* case substr 
* MOO --> n-3
* MOM --> n-3 + 1
* OOO --> n-3 + 1
* OOM --> n-3 + 2
* else -1
*
`strstr(whole_str, substr), if true --> ans`

## prob 1 - silver

* Each letter is a group of positions
* Smaller input group can merge into bigger output group, not vice versa
    * multiple input letters can become a single output letter, not vice versa
* If n smaller letters map to 1 output letter --> merge input groups into a single group --> n - 1
* Now you should have a one to one mapping from input to output, positions are irrelevant, it's just permuation
    * if input set != output set --> num_set ops
    * what if input set == output set --> num_set+1
* 
