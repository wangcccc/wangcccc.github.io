# Python

## String

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
expandtabs(tabsize=8)               # convert tabs to spaces

join(iterable)                      # sperator is the caller string
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

## List

```python
colors = ['red', 'green', 'blue']

colors[0] = 'yellow'

colors.append('yellow')
colors.insert(0, 'yellow')

del colors[0]
colors.pop()
colors.pop(1)
colors.remove('blue')

colors.sort(reverse=True)   # sort in-place
sorted(colors)              # return a new sorted list

colors.reverse()            # reverse in-place

'red' in colors             # check existence

len(colors)

nums = list(range(1, 6))    # make a list
min(nums)
max(nums)
sum(nums)

nums[1:4]
nums[2:]
nums[-3:]
copy_nums = nums[:]
```

## Dictionary

```python
worker = {'name': 'wang', 'age': 18}
worker['salary'] = 5000
del worker['salary']

worker.items()
worker.keys()
worker.values()

for k, v in worker.items():
    print('%s: %s' % (k, v))
    
sorted(worker.keys())
set(worker.values())
```

## IO & file

```python
# get user input
age = input('How old are you?')
age = int(age)
```

file open mode:

* r, read mode
* w, write mode
* a, append mode
* r+, read write mode

```python
# read all
with open('data.csv') as data_file:
    data = data_file.read()

# read by line
with open('data.csv') as data_file:
    for line in data_file:
        print(line.rstrip())

# read all lines
with open('data.csv') as data_file:
    liens = data_file.readlines()
for line in lines:
    print(line.rstrip())

# write file
with open('data.csv', 'w') as data_file:
    data_file.write('zhao, 18, 1000\n')
```

## Function & moudle

```python
# accept a variable number of arguments as tuple
def print_names(*names):
    print(names)
print_names('zhao')
print_names('zhao', 'qian', 'sun', 'li')

# accept a variable number of arguments as dictionary
def build_profile(name, age, **other_info):
    profile = {}
    profile['name'] = name
    profile['age'] = age
    for key, value in other_info():
        profile[key] = value
    return profile

def f(positional_argument, /, positional_or_keyword_argument, *, keyword_argument):
    pass
    
# import function from module
from module_name import function_name
from module_name import function_0, function_1
from module_name import *
from module_name import function_name as my_func
import module_name as my_module
```
