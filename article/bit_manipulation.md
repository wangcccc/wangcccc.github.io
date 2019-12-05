---
title: Bit manipulation
---

# Common operations

1. Set the nth bit
```c++
y = x | (1 << n);
```

2. Unset the nth bit
```c++
y = x & ~(1 << n);
```

3. Toggle the nth bit
```c++
y = x ^ (1 << n);
```

4. Turn off the rightmost 1-bit
```c++
y = x & (x - 1);
```

5. Turn on the rightmost 0-bit
```c++
y = x | (x + 1);
```

6. Isolate the rightmost 1-bit
```c++
y = x & -x;
```

7. Isolate the rightmost 0-bit
```c++
y = ~x & (x + 1);
```

# Problems

### 1. Power of Two
Given an integer, write a function to determine if it is a power of two.
```c++
bool isPowerOfTwo(int n) {
    return n > 0 && (n & n - 1) == 0;
}
```
