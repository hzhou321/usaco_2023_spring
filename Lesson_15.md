Lesson 15 - 2023-04-30
# Dynamic Programming

## Key idea
* Recursive induction

## Example Fibonacci 
* 1 1 2 3 5 8 ...
* Fib(N) = Fib(N-2) + Fib(N-1) -- a recursive relationship

```
int Fib(int N) {
   if (N == 0) return 1;
   if (N == 1) return 1;
   return Fib(N-2) + Fib(N-1);
}
```
* It is O(N!) if we directly solve it 
* Notice that where the repetitve part is 
* Cache the repetitive computation, and note that the cache if finite (or *bounded*)
* --> Fib complexity is O(N) if we cache all the Fib(i)

```
int cache[N_MAX];  // you always can use finite array to cache all of them

int Fib(int N) {
   if (N == 0) return 1;
   if (N == 1) return 1;
   if (cache[N] > 0) return cache[N];
   int ans = Fib(N-2) + Fib(N-1);  // This is the expensive part that we want to optimise --> skip as much as we can
   cache[N] = ans;
   return ans;   
}
```

### Coin problem
* Sol(N) = MIN (Sol(N-C[i])+1, ...)

### Leetcode problems
* 322, 518, 62, 300, 5, 32, 53, 64, 416, 790
