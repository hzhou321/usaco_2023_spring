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
