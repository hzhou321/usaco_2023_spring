Lesson 9 - 3/12/2023 - 21 Open

## Bronze 1

* H-index 
```
bool has_h_index(h) {
    foreach i in paper
        if c[i] > h
            count++
    return count>h         
}
```
```
foreach L possibilities
   for h = 1:N
       if !has_h_index(h)
           break
   max := h   
ans = max
```

...h h h ....
    [- h -]
...l+1>=h+1, g>=h+1    

if (l==g)
   for (i=[l]:N)
       if (c[i]==h) L-- if (L<0) break otherwise return h+1
       
## Bronze 2      
* traslate names into index 0..N-1
* E M D
* rank by effort first, senior always have lesser effort -> senior always behind unless equal effort and alphabeticall prior
* If not alphabetically in order  then it must be due to seniority

```
foreach paper list
    foreach pair
        if not alpha..., -> relationship
```

# Bronze 3
CGCGC
 C
* Trying to match cows
* each G can be used once at most
* top-down and left-right -- as long as you have a policy that prevent double counting pairs, it should work the same 
 
# Silver 1 - Tic tac toe
* Backtracking 
```
stack.push_back(initial_state)
cache.insert(initial_state)
while (stack.size()>0)
    i = stack.back()
    stack.pop_back()
    if (is_winning_state(i)) 
       ans++
       continue
    foreach edge -> j
        if !cache.count(new_state)
            stack.push_back(new_state)
            cache.insert(initial_state)
        
print ans
```
* what is a state here -- it needs represent all different situations
* maze position + tic-tac-toe-board
    * N*N -> position; 3x3 -> board; N <=25; 1 byte for x, 1 byte for y, 18 bits for the board, 2 bit for each M, O, .

```
struct state {
   int x;
   int y;
   int board[3][3];
};  
```
