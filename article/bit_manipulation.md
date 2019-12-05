---
title: Bit manipulation
---

# Common operations

> Set the nth bit

```c++
y = x | (1 << n);
```

> Unset the nth bit

```c++
y = x & ~(1 << n);
```

> Toggle the nth bit

```c++
y = x ^ (1 << n);
```

> Turn off the rightmost 1-bit

```c++
y = x & (x - 1);
```

> Turn on the rightmost 0-bit

```c++
y = x | (x + 1);
```

> Isolate the rightmost 1-bit

```c++
y = x & -x;
```

> Isolate the rightmost 0-bit

```c++
y = ~x & (x + 1);
```

# Problems

> #### Power of Two
> Given an integer, write a function to determine if it is a power of two.
```c++
bool isPowerOfTwo(int n) {
    return n > 0 && (n & n - 1) == 0;
}
```
