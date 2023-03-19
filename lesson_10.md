# Lesson 10 - 2212 - 3/19/2023

## prob1 - bronze
skipped

## prob2 - bronze
K is given

5 2
GHHGG

i=0, G, no seed yet, plant one, cur_G = 2, cnt++
...
i=3, G, cur_G covers, 

One iteration, O(N)


## prob3 -- Reverse Engineer
```
2 4
00 0
01 1
10 1
11 1
```
if b[0]==1 -> 1
   elif b[1] == 0 return 0
       else return 1

* 2^N -> O(2^N * M) - 2^100 * 10 
* N! permutations -> 100!
* same input should give same output
* if answer is different, controlled by one of the different bits
* if bit[0] == 0 -> return             -> 0* will always give the same answer  -> if one bit does not give consistent answer, then that bit can not be at pos[0]
* if bit[0] == 1 && bit[1] == 0 return -> 10 will always give the same answer

```
for i=0:N
   check if b[i]==0 gives the same ans if yes, add (i, 0) to the possibles
       for j=0:M
           if b[i]==0 and ans != prev ans, then break
   check if b[i]==1 gives the same ans ...
ans = (whetehr possiblles.size() > 0)   
```   

## sivler 1 - Barn Tree
* N, N-1, all connected -> tree
* root-> {subtree, subtree, ...}
* get sum / N -> avg -> goal is h_list[i]==avg
* optimally, any pair only pass once -> maximum ans is N-1

```
 1
 2
3 4
```
* avg = 3
* (1,2) - h_list[0] is 2, so need 1, move: 2->1 - 1
* (2,3) - if subtree has exesss, move subtree -> 2 - exess
*         else if deficiency, move 2-> subtree - deficiency

-> move_list
2, 1, 1
3, 2, 1
4, 2, 2
n = move_list.size() = 3 

* need sort move_list by dependency
* TOPOLOGICAL SORT
```
// build dependency tree 
// dependency_list[n], dependency_list[i] = {j1, j2, j3...}
std::vector<int> stack
std::set<int> cache

stack.push_back(0)
cache.insert(0)

while stack.size()>0
    i = stack.back()

    has_dependency = false
    foreach j in dependency_list[i]
        if cache.count(j) == 0
              stack.push_back(j)
              cache.insert(j)
              has_dependency = true
    if !has_dependency
       output move_list[i], add to cache
       stack.pop_back()
```       
* getting subtree sums
```
get_sum(0, -1)

sums[N], cnts[N]
void get_sum(i, parent)
    parents[i] = parent
    sums[i] = h_list[i]
    cnts[i] = 1
    foreach j in adj[i]
        if j!= parent
            get_sum(j, i)
            sums[i] += sums[j]
        cnts[i] += cnts[j]
```
* Summary
1. get sums, cnts, parents
2. get move_list foreach edge
3. topological sort the move_list -> sorted_list
4. for each sorted_list, output

# Circular Barns
* Range(i, j), max-min between i..j
* if a0 is max, a1 min
* r(0, 1) == a0 - a1
* r(0, 2) == a0 - a1
* r(1, 2) == a2 - a1
