Lesson3 - 2/5/23 - 2201

# Prob1 bronze
* enumerate all end result
```
min= INT_MAX
$for sum=0:N
    int cnt
    if works(sum, &cnt)
        if min > cnt
           min = cnt
bool works(int sum, int *cnt)  
   tsum = 0
   for i=0:N
       if tsum < sum          
          if tsum > 0
              (*cnt)++
          tsum += val[i]    
          if tsum > sum
             return false
          elif tsum == sum
             tsum = 0
   return (tsum == 0)         
```
* enumerate all combinations
   a1  a2 a3 --> 2 joins --> 2^2=4
   
# Prob2 bronze

* Sorting algorithm
** Insertion sort
1. pick a card
2. find a position
3. put it in

** Selection sort
1. find a minimum card
2. put to the right

5 1 3 2 4
4 5 2 1 3
-> 5 1 3 2 4
-> 4 5 1 3 2
-> 4 5 2 1 3

# Prob3 
Permuation of 4 -> 4! = 24
```
foreach permutation -> O(24)
   -> DICE[4]
   foreach word  --> O(N)
       foreach letter   -> O(4)
           check if letter in dice
```
# Prob1 Silver
```
foreach i, j
    if Vi(Gi) < Vi(Gj) && Vj(Gj) < Vj(Gi)
        exchange
--> Insufficient because 
```

* What is cow 0 best gift?
* Cow 0 try exchange gift with any other
*     and other need exchange with any other
*     until no exchange happens

## Classical backtracking algorithm
* think about a general graph
* N nodes, each node connected to a list of other nodes
* Start with a single node, add all connected nodes to your bag, add all further connected nodes to your bag while prevent repeat
* A **stack** is the most simplest container, LIFO, A B -> B A; A B C -> A B -> A B D
* std::vector<int> stack;
* stack.push_back(A)
* val = stack.back(); stack.pop_back();
```
std::unordered_set<int> cache;
std::vector<int> stack;
stack.push_back(0);
cache.insert(0);
while !stack.empty()
    idx = stack.back()
    stack.pop_back()
    foreach a in adj[idx]
        if !cache.count(a)
            stack.push_back(a)
            cache.insert(a)
```  
  
Ref: Recursive fill -> floodfill 
```


```

