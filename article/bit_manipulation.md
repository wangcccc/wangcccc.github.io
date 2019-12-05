---
title: Bit manipulation
---

# Common operations

### 1. Set the nth bit
```c++
y = x | (1 << n);
```

### 2. Unset the nth bit
```c++
y = x & ~(1 << n);
```

### 3. Toggle the nth bit
```c++
y = x ^ (1 << n);
```

### 4. Turn off the rightmost 1-bit
```c++
y = x & (x - 1);
```

### 5. Turn on the rightmost 0-bit
```c++
y = x | (x + 1);
```

### 6. Isolate the rightmost 1-bit
```c++
y = x & -x;
```

### 7. Isolate the rightmost 0-bit
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

### 2. Power of Four
Given an integer (signed 32 bits), write a function to check whether it is a power of 4.
```c++
bool isPowerOfFour(int num) {
    if (num <= 0) return false;
    if (num & num - 1) return false;
    return num & 0x55555555 == num;
}
```

### 3. Lowercase & Uppercase
Implement function toLowerCase(), toUpperCase() and toggleCase().
```c++
char toLowerCase(char c) {
    return c |= 32;
}
char toUpperCase(char c) {
    return c &= -33;
}
char toggleCase(char c) {
    return c ^= 32;
}
```
