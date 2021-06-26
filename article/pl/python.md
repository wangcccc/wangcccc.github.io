**Function parameters**
```python
def f(positional_argument, /, positional_or_keyword_argument, *, keyword_argument):
    pass
```
### String methods
**Strings are imuutable. None of these methods change the original string.**
```python
capitalize()                        # capitalize first character and lowercase the rest
title()                             # uppercase first character in words
lower()
upper()
swapcase()
casefold()                          # enhanced version of lower()

center(width[, fillchar])
ljust(width[, fillchar])
rjust(width[, fillchar])
zfill(width)                        # filled with '0'

split(sep=None, maxsplit=-1)
rsplit(sep=None, maxsplit=-1)
splitlines([keepends])
partition(sep)
rpartition(sep)

strip([chars])
lstrip([chars])
rstrip([chars])

removeprefix(prefix, /)
removesuffix(suffix, /)

replace(old, new[, count])

join(iterable)                      # sperator is the caller string
expandtabs(tabsize=8)               # convert tabs to spaces

format(*args, **kwargs)

find(sub[, start[, end]])           # return index
rfind(sub[, stasrt[, end]])
index(sub[, start[, end]])          # like find(), but raise ValueError when not found
rindex(sub[, start[, end]])

count(sub[, start[, end]])
startswith(prefix[, start[, end]])
endswith(suffix[, start[, end]])

isalnum()
isalpha()
isdigit()

islower()
isupper()

isspace()
istitle()
```
