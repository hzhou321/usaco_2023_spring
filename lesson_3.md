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

