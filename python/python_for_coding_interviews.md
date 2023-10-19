# [Python for Coding Interviews](https://neetcode.io/courses/lessons/python-for-coding-interviews)

## Variables
```python
# variables are dynamicly typed
n = 0
print('n =', n)
>>> n = 0

n = "abc"
print('n =', n)
>>> n = abc

# multiple assignments
n, m = 0, "abc"
n, m, z = 0.125, "abc", False

# increment
n = n + 1     # good
n += 1        # good
n++           # bad

# none is null (absence of value)
n = 4
n = None
print("n =", n)
>>> n = None
```

## Math
```python
# division is decimal by default
print(5 / 2)
>>> 2.5

# double slash (aka floor division) rounds down
print(5 // 2)
>>> 2

# CAREFUL: most languages round toward 0 by default
# Python floor division round away from 0
print(-3 // 2)
>>> -2

# workaround for rounding toward 0 is to use decimal division and then convert to int
print(int(-3 / 2))
>>> -1

# modding is similar to most languages
print(10 % 3)
>>> 1

# except for negative values
print(-10 % 3)
>>> 2

# to be consistent with other languages modulo
import math
print(math.fmod(-10, 3))
>>> -1.0

# more math helpers
print(math.floor(3 / 2))
>>> 1

print(math.ceil(3 / 2))
>>> 2

print(math.sqrt(2))
>>> 1.4142135623730951

print(math.pow(2, 3))
>>> 8.0

# max and min int
float("inf")
float("-inf")

# python numbers are infinite so they never overflow
print(math.pow(2, 200))
>>> 1.6069380442589903e+60

# but still less than infinity
print(math.pow(2, 200) < float("inf"))
>>> True
```

## Array (List)
```python
# arrays (called lists in python)
arr = [1, 2, 3]
print(arr)

# can be used as a stack
arr.append(4)
arr.append(5)
print(arr)

arr.pop()
print(arr)

arr.insert(1, 7)
print(arr)

arr[0] = 0
arr[3] = 0
print(arr)

# initialize arr of size n with default value of 1
n = 5
arr = [1] * n
print(arr)
print(len(arr))

# careful: -1 is not out of bounds, it's the last value
arr = [1, 2, 3]
print(arr[-1])

# indexing -2 is the second to last value, etc.
print(arr[-2])

# sublists (aka slicing)
arr = [1, 2, 3, 4]
print(arr[1:3])

# similar to for-loop ranges, last index is non-inclusive
print(arr[0:4])

# but no out of bounds error
print(arr[0:10])

# unpacking
a, b, c = [1, 2, 3]
print(a, b, c)

# be careful though
# a, b = [1, 2, 3]

# loop through arrays
nums = [1, 2, 3]

# using index
for i in range(len(nums)):
    print(nums[i])

# without index
for n in nums:
    print(n)

# with index and value
for i, n in enumerate(nums):
    print(i, n)

# loop through multiple arrays simultaneously with unpacking
nums1 = [1, 3, 5]
nums2 = [2, 4, 6]
for n1, n2 in zip(nums1, nums2):
    print(n1, n2)

# reverse
nums = [1, 2, 3]
nums.reverse()
print(nums)

# sorting
arr = [5, 4, 7, 3, 8]
arr.sort()
print(arr)

arr.sort(reverse=True)
print(arr)

arr = ["bob", "alice", "jane", "doe"]
arr.sort()
print(arr)

# custom sort (by length of string)
arr.sort(key=lambda x: len(x))
print(arr)

# list comprehension
arr = [i for i in range(5)]
print(arr)

# 2-D lists
arr = [[0] * 4 for i in range(4)]
print(arr)
print(arr[0][0], arr[3][3])

# this won't work
# arr = [[0] * 4] * 4
```

## Strings
```python
# strings are similar to arrays
s = "abc"
print(s[0:2])

# but they are immutable
# s[0] = "A"

# so this creates a new string
s += "def"
print(s)

# valid numeric strings can be converted
print(int("123") + int("123"))

# and numbers can be converted to strings
print(str(123) + str(123))

# in rare cases you may need the ASCII value of a char
print(ord("a"))
print(ord("b"))

# combine a list of strings (with an empty string delimitor)
strings = ["ab", "cd", "ef"]
print("".join(strings))
```

## Queues
```python
# queues (double ended queue)
from collections import deque

queue = deque()
queue.append(1)
queue.append(2)
print(queue)

queue.popleft()
print(queue)

queue.appendleft(1)
print(queue)

queue.pop()
print(queue)
```

## HashSet (Set)
```python
# HashSet
mySet = set()

mySet.add(1)
mySet.add(2)
print(mySet)
print(len(mySet))

print(1 in mySet)
print(2 in mySet)
print(3 in mySet)

mySet.remove(2)
print(2 in mySet)

# list to set
print(set([1, 2, 3]))

# set comprehension
mySet = { i for i in range(5) }
print(mySet)
```

## HashMap (Dictionary)
```python
# HashMap
myMap = {}
myMap["alice"] = 88
myMap["bob"] = 77
print(myMap)
print(len(myMap))

myMap["alice"] = 80
print(myMap["alice"])

print("alice" in myMap)
myMap.pop("alice")
print("alice" in myMap)

myMap = { "alice": 90, "bob": 70 }
print(myMap)

# dict comprehension
myMap = { i: 2*i for i in range(3) }
print(myMap)

# looping through maps
myMap = { "alice": 90, "bob": 70 }
for key in myMap:
    print(key, myMap[key])

for val in myMap.values():
    print(val)

for key, val in myMap.items():
    print(key, val)
```

## Tuples
```python
# tuples are like arrays but immutable
tup = (1, 2, 3)
print(tup)
print(tup[0])
print(tup[-1])

# can't modify
# tup[0] = 0

# can be used as key for hash map/set
myMap = { (1,2): 3 }
print(myMap[(1,2)])

mySet = set()
mySet.add((1, 2))
print((1, 2) in mySet)

# Lists can't be keys
# myMap[[3, 4]] = 5
```

## Heaps
```python
import heapq

# under the hood are arrays
minHeap = []
heapq.heappush(minHeap, 3)
heapq.heappush(minHeap, 2)
heapq.heappush(minHeap, 4)

# min is always at index 0
print(minHeap[0])

while len(minHeap):
    print(heapq.heappop(minHeap))

# no max heaps by default, work around is
# to use min heap and multiply by -1 when push & pop.
maxHeap = []
heapq.heappush(maxHeap, -3)
heapq.heappush(maxHeap, -2)
heapq.heappush(maxHeap, -4)

# max is always at index 0
print(-1 * maxHeap[0])

while len(maxHeap):
    print(-1 * heapq.heappop(maxHeap))

# build heap from initial values
arr = [2, 1, 8, 4, 5]
heapq.heapify(arr)
while arr:
    print(heapq.heappop(arr))
```

## Functions
```python
def myFunc(n, m):
    return n * m

print(myFunc(3, 4))

# nested functions have access to outer variables
def outer(a, b):
    c = "c"

    def inner():
        return a + b + c
    return inner()

print(outer("a", "b"))

# can modify objects but not reassign
# unless using nonlocal keyword
def double(arr, val):
    def helper():
        # Modifying array works
        for i, n in enumerate(arr):
            arr[i] *= 2
        
        # will only modify val in the helper scope
        # val *= 2

        # this will modify val outside helper scope
        nonlocal val
        val *= 2
    helper()
    print(arr, val)

nums = [1, 2]
val = 3
double(nums, val)
```

## Classes
```python
class MyClass:
    # Constructor
    def __init__(self, nums):
        # Create member variables
        self.nums = nums
        self.size = len(nums)
    
    # self key word required as param
    def getLength(self):
        return self.size

    def getDoubleLength(self):
        return 2 * self.getLength()

myObj = MyClass([1, 2, 3])
print(myObj.getLength())
print(myObj.getDoubleLength())
```
