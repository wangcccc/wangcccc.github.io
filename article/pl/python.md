# Python

## Create a virtual environment

```shell
python3 -m venv my_venv
source my_venv/bin/activate
```

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
* b, binary

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

## Exception

```python
try:
    result = a / b
except ZeroDivisionError:
    print('Divide by 0!')
else:
    print(answer)
```

## Libraries

### JSON

```python
import json

data = [1, 2, 3]
with open('data.csv', 'w') as data_file:
    json.dump(data, data_file)

with open('data.csv') as data_file:
    data = json.load(data_file)
```

### pygal

```python
import pygal
import time
import numpy as np
from collections import Counter


start = time.time()
# roll two dices 10000000 times each
rands1 = np.random.randint(1, 7, 10000000)
rands2 = np.random.randint(1, 7, 10000000)
# sum the result of each roll
rands3 = np.add(rands1, rands2)
# count frequencies
frequencies = Counter(rands3)
frequencies = [cnt for (_, cnt) in sorted(frequencies.items())]

# config pygal drawing settings
hist = pygal.Bar()
hist.title = 'Result of rolling two D6 10000000 times'
hist.x_labels = list(range(2, 13))
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'
hist.add('D6', frequencies)
svg_bytes = hist.render()

# write to file
with open('roll_result.svg', 'wb') as file:
    file.write(svg_bytes)

# print time costed
end = time.time()
print('Total time: {}'.format(end - start))
```

### matplotlib

```python
from random import choice
import matplotlib.pyplot as plt


class RandomWalk:
    def __init__(self, num_points=500):
        self.num_points = num_points

        self.x_values = [0]
        self.y_values = [0]

    def fill_walk(self):
        while len(self.x_values) < self.num_points:
            x_direction = choice([1, -1])
            x_distance = choice(range(0, 5))
            x_step = x_direction * x_distance

            y_direction = choice([1, -1])
            y_distance = choice(range(0, 5))
            y_step = y_direction * y_distance

            if x_step == 0 and y_step == 0:
                continue

            next_x = self.x_values[-1] + x_step
            next_y = self.y_values[-1] + y_step

            self.x_values.append(next_x)
            self.y_values.append(next_y)


if __name__ == '__main__':
    while True:
        rw = RandomWalk(50000)
        rw.fill_walk()
        plt.figure(figsize=(10, 6))
        point_numbers = list(range(rw.num_points))
        plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues,
                    edgecolor='none', s=1)
        plt.scatter(0, 0, c='green', edgecolors='none', s=100)
        plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none', s=100)
        plt.show()

        keep_running = input('Make another walk? (y/n): \n')
        if keep_running == 'n':
            break

```

### requests

```python
import requests

url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print('Status code:', r.status_code)
r_dict = r.json()
```

### Django

Create a new project.

```shell
$ django-admin startproject my_web_project .

$ ls
my_web_project manage.py

$ ls my_web_project
__init__.py agsi.py settings.py urls.py wsgi.py
# wsgi stands for web server gateway interface.

# create migrate db
$ python manage.py migrate

$ ls
db.sqlite3 my_web_project manage.py

# run server
$ python manage.py runserver

# create app
$ python manage.py startapp my_app

# create migrations
$ python manage.py makemigrations my_app


```
